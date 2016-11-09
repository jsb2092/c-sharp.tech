---
title: "IPv6, Tunnels and Windows"
published: true
header:
  overlay_image: /assets/images/ipv6.png
  overlay_filter: 0.8
categories:
  - Networking
tags:
  - networking
  - tunnels
  - IPv6
date: 2016-11-09T14:15:00-04:00
---

How getting an IPv6 tunnel working turned into a project

In an interesting turn of events, it turns out I have a block of IPv6 addresses at home, thanks to Time Warner Cable of all companies.  My employer, however, does not offer IPv6 everywhere in the facility, which means I can't get an IPv6 address to demo to students in my networking class.  This is sad, but not an unsolvable problem.

[Hurricane Electric](http://he.net) offers many services to help the budding IPv6 guru, including certification, DNS, and free tunnels.  I decided it was time to setup a tunnel (encapsulating an IPv6 packet inside an IPv4 packet to get the IPv6 network) so that I could test several applications that I had written to demonstrate IPv6.

The problem with the tunnel is 2-fold.  First, it doesn't work through a NAT, which means that if you are behind a NAT (as most people 
on a home network are), it won't work unless you configure your router to be the endpoint of the tunnel, and then it's kind of magic.The second, and for me, more pressing problem is that the tunnel requires that you have a static IPv4 address.  Since the University uses DHCP, that means that every day that I come in, I get a new address, and have to update the endpoint on the [TunnelBroker](http://tunnelbroker.com) site.  Thankfully, they provide an API that actually allows you to update the endpoint remotely, so that problem was solved.

The bigger problem was the Windows side.  I am running Windows 10 on my laptop, and am quite pleased with it, but that's a story for another time.  There are several commands you need to execute in an elevated (admin) command prompt, and run a couple of netsh commands to setup the tunnel on the client side.  Of course, one of these commands sets up the bridge between the IPv4 address and IPv6 address on the client.  Netsh, being what it is, doesn't provide an easy mechanism to change these addresses.  I took it upon my self to make a app that would run in the background and would update the tunnel side and update my windows configuration at the same time.  This happens any time the local IP changes, usually within a couple of seconds.

I had a few problems with this app; namely I needed it to be a classic WPF app, because of the reliance on being able to run a command line program, and because I wanted it to live in the tray, with no interaction needed from the user.  After several hours, I got a working prototype and put it on [GitHub](https://github.com/jsb2092/TunnelBrokerUpdate).  As it stands, it has some issues with the notification icon, though that coule be my build of Windows that is causing that.  There is a hack in there that solves the problem (more or less).  I also don't have a proper icon yet, and the help text is non-existent, but it is functioning.  Ever time my local IPv4 address changes, the remote endpoint gets updates, and my Windows configuration gets updated as well (as long as I run the program as 'Administrator')

I also realize the architecture of the app is pretty terrible (as in there is none), but it does work in Windows 10 (64bit).  I hope to add more functionality to it in the next couple of days (at which point I'll update this), but my first hope would be that IPv6 gets deployed across campus in the near future.  Having a solid network stack at home and work would be quite the treat. 