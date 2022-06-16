Hey everyone!

I just wanted to give an update on LBG (Laid Back Gaming) as of June 12th, 2022. I also want to start doing these type of blog posts and updates a lot more often in the future. I love writing about what we're doing and what my view on LBG's future is.

## Off To A Great Start!
Ever since I purchased LBG's first game server machine, with a combination of our Anycast network, LBG has already had a lot of success! 

Here are the specs of our first game server machine.

* AMD Ryzen 9-5900X, 12 cores & 24 threads @ 3.7 GHz.
* 32 GBs of DDR4 RAM.
* Unlimited Bandwidth @ 1 gbps.
* 2 x 512 GBs NVMe in RAID 1.
* $167.63/m.
* Located in Montreal, CA
* [From OVH](https://www.ovhcloud.com/en/bare-metal/advance/adv-3/).

So far, we've setup the following new servers.

* CS:GO Surf Timer Beginner.
* CS:GO Zombie Escape.
* CS:S 24/7 Dust2.
* CS:S Bunny Hop.
* GMod Lawless DarkRP.
* GMod Sandbox.
* GMod Zombie Survival.
* Rust 10x.
* TF2 24/7 2Fort #1.
* TF2 24/7 2Fort #2.
* TF2 24/7 Hightower #1.

A majority of these servers has shown success already! Here is a list of accomplishments I've seen so far personally (I apologize if I miss any!).

* GMod Sandbox has been averaging within the 20 - 30 player range.
* GMod Prop Hunt is slowly taking off and has filled to the maxplayers a few times already.
* Rust 10x reached 35 - 40 players at one point. The server is still slowly taking off, but I do have a good feeling about this server and division in general this Summer!
* Both TF2 2Fort server consistently fill on a daily basis to 32 - 33 players. They sometimes even stay filled throughout the night!
* CS:GO Surf Timer Beginner reached 60 players at one point, but quickly calmed down afterwards. The server still needs work, but we'll get it there.

As you can see, we've had a lot of accomplishments already. However, I do believe this is only the beginning and we have some big plans in-store.

## Getting Temporary Donations Going
I've decided to purchase a system called [Prometheus](https://www.gmodstore.com/market/view/prometheus). This system will be able to manage subscription-based packages. We're going to be setting up a $4.99/m package (with custom amounts supported) that'll be called "VIP". This package will come with benefits in the Discord server and all game servers.

While the VIP rank itself will stay permanently, we likely be migrating to a custom system we make which will be explained below.

* At our current stage, everything will be considered donations and go back into the community. However, charge-backs will result in a permanent ban.

*We may change our income layout in the future and allow staff to get paid. This will result an entire business restructure and we will make sure to be as transparent as possible.*

## Website/Web Back-End
This has been a topic we've been thinking about for a while. Initially, LBG had a forum using [Discourse's forum software](https://www.discourse.org/). I did put quite a bit of work into it, but I do feel Discourse felt more restricted compared to other forum softwares I've used like [IPS 4](https://invisionpower.com/) and [vBulletin](https://www.vbulletin.com/). Therefore, I didn't enjoy using it as much on the admin-side personally.

Both IPS 4 and vBulletin are options we cannot afford at the moment though. This is because Synk and I are both spending already hundreds of dollars a month on LBG expenses. With that said, in an old community I used to manage (GFL), the forums were dying towards the end. I think it'd be best not having a community forum and focus everything on Discord. This would us hardware expenses as well. However, one thing that is being considered is using a forum software (most likely Discourse) temporarily for MOTDs, important threads, etc.

Instead of using/extending forum software (because, well I personally don't like IPs 4 or vBulletin's APIs much anyways), I was planning to make a LBG "core" Web Application in Go for the back-end. This would include a highly-optimized database we'd use to store important things from LBG such as a game server list, staff information, etc. We could also extend this and implement the server list into the Anycast network so we can add servers easier. We could then implement a Discord authentication system and allow Server Managers+ to make their own MOTD windows with HTML/BB-Code support along with making their own Loading Screens. I think this is a huge opportunity to make something custom for ourselves. We should utilize Go's template system for the back-end. We could also use this to display ranks for play/idle time on our servers There is so much we could do if we made our own core application that added as the website while extending it into our game server use. I'm going to save the in-depth details for another time, but this is something I'm going to be researching and once I build the base, I'll also implement a future Idle Bot that will help our servers grow.

This is essentially a project I wanted to do in my old community and I used to write a lot about it. But it never happened due to motivation and time restrictions. This is also a project that will give us a lot of knowledge in Go and also will allow us to add so many cooler things to our Discord and game servers.

I will be giving more details on this as time goes on and I make progress on everything :)

## The Anycast Network
Synk has done a great job with our Anycast network. I created the base of everything, including the XDP program (Kilimanjaro) and the program that communicates from the edge PoPs to the web back-bone which is called Killtrocity. However, Synk has helped create filters (I cannot legally do this at this moment due to writing filter code for other companies) and fix issues with the software. We're going to be looking to replace Killfrenzy (our Python back-end using Django) because it wasn't meant to handle so much information from our PoPs in the back-end. So Synk is looking to replace that permanently in the future. 

Synk has also done a great job finding new hosting providers outside of Vultr and then setting up more PoPs for LBG's network. He has been making sure each hosting provider has the upstreams we need which narrow down the choices a lot.

Synk is also looking to implement filters for FiveM and Squad soon! This way, we can start expanding into those games.

The more PoPs we have with better hosting providers equals better control over routing and more (D)DoS protection. With that said, the A2S_INFO caching system I've implemented is a lot more stable and running in raw XDP/AF_XDP. This also helps with populating our servers!

## What Will The Summer Behold For Us?
This Summer will be interesting for LBG. We're already off to a good start, but there are some worries I do have. I'm not sure how many more servers we'll be able to handle on our current machine due to disk space and RAM limitations, especially since Rust and FiveM are both big targets we're aiming for. Our goal is to get LBG in a state where we can easily expand without worrying about growth. This requires the back-end above to be completed along with a custom bans and donations system that is implemented into our website I feel. With that said, we'll need to make sure our servers have the same LBG-specific plugins. We haven't even received a donation yet and I'm putting out my max for LBG at this moment which is around $400/m. I will make another article at some point on how much we're spending currently and how much we'll need to make. Another more advanced technical thing to do is use a file system for compression or hard-linking base game files to save disk space.

Assuming we have a lot of donations though so we can buy more machines and maintain/expand our Anycast network, we plan on making many expansions. 

For one, I feel there is a hot market in TF2 right now and with TF2 getting a lot of community attention due to Valve's lack of interest for the game, I do feel like TF2 has spiked in numbers. Depending on how many more machines we can have and if we can get them all synchronized with plugins/configs. We could get up to 10 - 20+ TF2 servers (most servers being vanilla). However, again, this depends on how much resources we'll have and if we can deploy/maintain them easily on a technical-side.

For two, I feel Rust will be the next biggest market. I really think we should have some Rust Vanilla servers up just to get people into the Discord. I'm not sure on what VIP perks we could give on vanilla, but I hope they allow for a chat tag or reserved slot at least. I could see us getting 5 - 10 Rust servers if they're all populating consistently between automated wipes.

Next, I believe Garry's Mod will have a lot of potential too. Whether it's from multiple TTT servers to a couple high-count RP servers. I also wouldn't count a Cinema server out as well if we can get the dev work along with a Cloneswar RP server. Garry's Mod will depend on how many staff resources we can get and once we get the idle bot finished. The idle bot we're planning to make will really help our Garry's Mod servers at the least.

Apart from those games, we're going to continue to expand into CS:GO and also consider FiveM as soon as we have the resources to. We may also try some other games like CoD 4, Battlefield (3 or 4), Arma 3, etc. However, all of these depends if we can get the resources/donations to have them.

## EU/UK Expansion
One last thing I also want to mention is we'll likely expand into EU/UK at some point as well. This will require first, enough donations to afford the machine. However, if we can't divide our IP range for population geo-location databases such as [IP2Location](http://ip2location.com/) and [Maxmind](http://maxmind.com/), we may have to use a separate /24 IP block for Europe only which would be a big waste of resources unfortunately.

## Help Wanted!
I also want to make it known we are looking for help within the community itself. We are looking for developers who have experience in the Lua, Go, C, and many other languages. With that said, if you have any ideas for the community, please let us know in #suggestions! The community is still nowhere close to complete and I'm hoping tackling the things above will help a lot. Lastly, please feel free invite anybody to our Discord server. We are growing in size and almost at 1000+ users!

Well that's it for now! I would write more, but I feel for a first article, this is big enough.

Thank you for reading!
