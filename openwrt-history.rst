openwrt\ 历史
#########################

:date: 2013-10-16 22:20
:tags: openwrt 
:category: tech
:slug: openwrt-history

2002年底，Linksys公司推出了一款非常经典的路由器WRT54G。当时乃802.11a/b\ `ft_80211g_std_release`_\ 当道，然而Linksys公司却坚定地使用了802.11g，理论速度高达54M。更快的速度、cisco的品质\ `ft_cisco_qa`_\ ，加上相对低廉的价格，Linksys WRT54G在无线路由器市场上刮起了一阵旋风。然而这些尚不足以称之为经典，何谓经典？经典指的是经过多年之后还能被世人所传诵，而Linksys WRT54G一直以来所被津津乐道的是它开创了刷机的先河。只要有一点DIY的精神，通过刷机，就可以将几百块钱的家用无线路由器，改造成一台成千甚至上万的企业级设备，这是一件多么有成就感，多么有吸引力的事情！

那为何市面上的无线路由器那么多，单就Linksys WRT54G就可以刷机呢？原因是Linux \ `ft_linux_kernel`_\ 。当WRT54G发布后，Andrew Miklas在\ `Linux kernel mailing list`_\
宣称他发现WRT54G的firmware用了一些经过修改的linux的代码，但无法确定是哪部分。大家知道，linux是遵循gpl协议发布的软件，凡是在linux基础上进行修改的源代码都必须开源。虽然大家都不确定Linksy到底修改了哪部分linux，总之到了2003年7月，Linksys迫于公众的压力开源了WRT54G的firmware。这下子炸开了锅，一些hacker尝试着修改源代码，改善稳定性，甚至增加新的功能。第三方firmware如雨后春笋般冒了出来，从此，无线路由器进入了一个逢人必问：“你今天刷了吗？”的时代。

到现在为止还没openwrt什么事，还请各位看官请稍安勿躁，这一段历史还是很有趣的，值得一提。当时比较有影响力的第三方firmware是一家叫做sveasoft公司所开发的Alchemy，然而这家公司也不地道，为了赚钱，它要求用户必须每年花20美元加入他们的社区后才能获取最新的源代码，于是又跟linux拥护者杠上了。2005年初，一个叫BrainSlayer的家伙fork Alchemy，加入一些新的功能特性，发布了一个新的发行版：DD-WRT。它不仅功能丰富，而且拥有友好的GUI，加上免费这个午餐吸引了大量用户，慢慢的sveasoft就没落了，就没有然后了。

下面终于轮到openwrt出场了。openwrt也是同一时间出现的，但他的出场有些特别，按理说都是微创新\ `ft_openwrt_early_version`_\ ，至少要在原有基础上做一些修改工作，svealsoft和dd-wrt，hyperwrt和tomato均如此，但openwrt另辟蹊径，推出第一版之后，推倒重来，采用buildroot重新打造一个全新的firmware，这需要很大的勇气，好在大家都是义务帮忙，大不了就废了，不成想，这一决定成就了openwrt，不破不立，古人诚不欺我。

相对于其它firmware，openwrt有以下优势：

* cli
* package
* 

当然，并不是说openwrt就没有缺点，至少对于一般用户来说，dd-wrt更易于使用，但对于一个有理想、有追求的宅男来说，openwrt才是最终的归宿。


在当时引发了要知道802.11g直至2003年的6月份才成为正式的标准，它的经典不仅体现在支持802.11g，理论上速率可达54M，超越了当时市宅男来说，面上，更重要的是，aca发现这款路由器的firmware是一个嵌入式linux操作系统，于是在论坛上发起请愿，要求Linksys公司公布firmware的源代码，因为根据gpl，凡是利用linux kernel做的软件，都要无偿的反馈给开源社区。迫于公众压力，Linksys公开了源代码，这一下子就炸开了锅，因为很多hacker发现，不在于其出身，也不在于其性价比，而在于它的firmware，

Linksys于2003年底推出了一款优秀的无线路由器：WRT-54G。一开始的时候，它并不引人注意，人们仅仅把它当作一个无线接入点而已。不过选择了linux作为操作系统给它带来了一个意想不到的机会，那就是用户可以根据自己的需要，在上面自由的修改和发布新的firmware。随着一些功能丰富的第三方firmware的出现，它终于散发出了迷人的魅力，为广大玩家所追捧。

WRT-54G刚推出的时候，官方firmware的功能并不强大，不久后，一家叫做sveasoft公司看到的其中的契机，在其基础上开发了Alchemy，并按每份拷贝收取20美元，这就让开源社区的用户大为不满了，连官方的firmware都遵循GPL协议开源了，凭什么sveasoft这个第三方的firmware却要收费，于是，一些热心的发烧友重起炉灶，开发了其他的版本，目前比较流行的是HyperWRT，DD-WRT和OpenWRT。其中HyperWRT的理念是忠于官方版本，只增加小部分功能，追求高稳定性；OpenWRT的理念则是设计一个通用的最小内核，让该内核也可以运行在其他品牌的无线路由器上，然后由其他人在上面开发新的功能插件，不过它的易用性就比较差了，需要通过命令行来配置；而DD-WRT追求的则是最完善的功能和最佳的易用性，它的确做到了这一点，因而赢得了广大用户芳心。平心而论，OpenWRT的开发模式才是正确的方向，它的ipkg就很好用，一些高阶的用户更偏爱OpenWRT，相信OpenWRT日后必有大的作为。
目前DD-WRT是最流行的版本，为了照顾大部分读者，我选择了DD-WRT作为范例，现在让我们开始WRT-54G的神奇之旅吧。


2002年，Linksys公司推出了一款

openwrt逐渐成为各种新网络协议的试验田，从openflow到codal，无不如此。因为基于MIPS架构的无线路由器便宜量又足，人人都可以购买

2013年4月，openwrt 12.09发布了，linux kernel升级到3.3，二进制软件包的数量达到3xxx个，openwrt社区正健康而有序的发展着。

.. 80211g_std_release:: http://www.
.. ft_80211g_std_release:: http://www.cisco.com
.. ft_cisco_qa:: http://answers.yahoo.com/question/index?qid=20100829205617AAgMcYN
.. ft_openwrt_early_version:: 项目始于2004年1月，当时基于Linksys的firmware，同时采用了uclibc项目的buildroot，

参考

linksys wrt54g history
http://indowrt.blogspot.com/2008/01/history-of-wrt54g-open-source-firmware.html
