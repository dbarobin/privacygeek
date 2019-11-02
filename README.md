# 隐私极客

**隐私极客，Privacy Geek。**

关于隐私，「[黑客伦理与信息时代精神](https://book.douban.com/subject/1071093)」写到：「言论自由和隐私权一直是很重要的黑客理想，网络的发展也一直与此一致。隐私不只是一个伦理问题，它还是一个技术问题」。

希望从今以后，隐私不会再只是茶余饭后一笑而过的谈资。

## 系列文章
***

### 开篇
***

酝酿了一段时间，新专栏「**隐私极客**」终于和大家见面了。

关于隐私，「[黑客伦理与信息时代精神](https://book.douban.com/subject/1071093)」写到：「言论自由和隐私权一直是很重要的黑客理想，网络的发展也一直与此一致。隐私不只是一个伦理问题，它还是一个技术问题」。

![](https://cdn.dbarobin.com/fp4a4zm.jpeg)

> 题图来自: © Consumer Reports / 66 Ways to Protect Your Privacy Right Now / consumerreports.org

2018 年 5 月欧盟出台了《通用数据保护条例》（General Data Protection Regulation，简称 GDPR），强调了个人数据的权力申明。国外知名的产品支持用户永久注销账号，甚至下载个人产生的数据。然而在某国，国民是没有隐私的，甚至没有选择的权利，为了完成万恶的 KPI，不惜牺牲用户体验，甚至违反相关条例。

如何在互联网世界保护个人隐私，有非常多的最佳实践，然而对于绝大多数的人来说，并没有这方面的知识储备。更关键的是，很多人并没有保护隐私的意识，很大一个原因是我们获取客观信息的成本相当高。

大环境虽如此，但除了自己，[没有人能保护你的隐私](https://typeblog.net/nobody-can-protect-your-privacy-except-yourself)。选择是有成本的，但并不代表所有的人都会屈服。商业利益会放大人性的恶，小恩小惠也会造成隐私的泄漏。保护隐私，你需要的不仅仅是意识，更多的是行动。

这个专栏会给读者带来哪些内容呢？一个软件、一个技巧、一则资讯、一篇感悟……主题只有一个，那就是「**隐私**」。至于更新频率，笔者向来比较随性，但笔者可以保证的是，这个专栏会持续写下去，因为隐私是个亘古不变的话题，而且这也是笔者感兴趣的一个方向。

借用 [PeterCxy](https://github.com/PeterCxy) 的一句话：**希望从今以后，隐私不会再只是茶余饭后一笑而过的谈资**。

### PGP
***

4 月份这个专栏开了个头，这算是「**隐私极客**」的第一篇文章。想了许久，第一篇文章写什么主题呢？列了很多大纲，最后还是选定 PGP。

PGP 是什么呢？不少从事互联网行业的可能也未必知道，这个技术不断地从我们的视野中消失，然而这却是一个相当有用的技术。可能读者会好奇独立博客博主为什么会在自己的博客上留 PGP 公钥，也在某些电影看到 PGP 用于发送邮件。诚然，虽然普通网民越来越少地使用 PGP，但 PGP 用到的非对称加密是加密学领域非常重要的技术。

OK，言归正传，可能部分读者对 PGP 比较陌生，容笔者简单介绍下。

> PGP 是 [Pretty Good Privacy](https://en.wikipedia.org/wiki/Pretty_Good_Privacy) 的缩写，由 [Philip R. Zimmermann](http://philzimmermann.com/EN/background/index.html) 于 1991 年编写并上传到 USENET 而在全球流行，被广泛用于文本、电子邮件、文件甚至整个磁盘分区的签名、加密和解密。上传行为因涉嫌违反美国的加密软件出口限制而使 Zimmermann 陷入长达三年的犯罪调查。政府的调查终止之后，Zimmermann 创立了 PGP 公司，PGP 由此成为商业软件（PGP 公司在辗转多次之后最终被 Symantec 收购）。[1]

[OpenPGP](https://www.openpgp.org) 是由 PGP 衍生出的开源规范，而 [GnuPG](https://gnupg.org)（简称 GPG）就是遵循 OpenPGP 规范的 GNU 实现。在不需要特别说明差异的情况下，三者统称为 PGP。

![](https://cdn.dbarobin.com/eWAUxsB.jpg)

> 题图来自: © DARKNETMARKETS / Have an Anonymous Chat / darknetmarkets.co

PGP 使用的是非对称加密算法，关于 PGP 的更多知识，可以去阅读 [维基百科](https://zh.wikipedia.org/wiki/PGP) 或者 Google 搜索「PGP」。对于普通网民来说，PGP 有什么用呢？在此简单描述下使用方法。A 生成公私钥对，B 也生成公私钥对，A 将自己的公钥给 B，B 也将自己的公钥给 A，也就是 A 和 B 互相交换自己的公钥。然后 A 使用 B 的公钥并且用自己的私钥加密文本，将加密后的文本发给 B，B 用自己的私钥解密文本，反之亦然。当然了，PGP 加密解密文件也是类似的。加密解密过程示意图如下：

![](https://cdn.dbarobin.com/cJVocVj.png)

> 图片来自: © GO ANYWHERE / Open PGP Encryption / goanywhere.com

PGP 的工作原理是端对端加密，[Telegram](https://telegram.org) Secret Chat、[Singal](https://signal.org)、[Wire](https://wire.com) 等 IM 也提供端对端加密聊天功能。但为什么要用 PGP 呢？因为 PGP 是相当靠谱的加密工具，其安全性得到了充分的验证。

PGP 适用于大多数加密传输的场景。有了 PGP，读者甚至可以在接近裸奔的微信里愉快地聊天，也不怕隔空拦截或者和谐封号。文本、文件、邮件……任何涉及到加密传输的场景都有用武之地。以区块链行业为例，可能不少用户平时会在不同设备之间传输助记词、密码甚至私钥，根据笔者的观察，不少团队使用了微信、钉钉、云笔记、网盘等工具，然而这是相当危险的。更稳妥的办法，读者需要 PGP。简单讲一下使用方法，读者自行注册两个 Gmail 邮箱（当然也可以是其他非国内的邮箱，具体的以后再讲），使用这两个邮箱生成公私钥对，在自己的这两个公私钥对之间进行加密解密即可。

可能读者又有疑惑了，PGP 讲解了这么多，具体怎么用？读者感兴趣可以参考 OpenPGP 网站提供的 [软件](https://www.openpgp.org/software) 页面，针对不同的终端选择不同的软件。根据笔者的经验，不同终端推荐使用如下的软件：

* macOS：[GPG Suite](https://gpgtools.org)
* Windows：[Gpg4win](https://www.gpg4win.org)
* iOS：[PGP Everywhere](https://itunes.apple.com/us/app/pgp-everywhere/id1011677987?mt=8)，付费软件，美区 $4.99
* Android：[OpenKeychain: Easy PGP](https://play.google.com/store/apps/details?id=org.sufficientlysecure.keychain&hl=en)
* Chrome：[Mailvelope](https://chrome.google.com/webstore/detail/mailvelope/kajibbejlbohfaggdiogboambcijhkke)
* Firefox：[Mailvelope](https://addons.mozilla.org/firefox/downloads/latest/mailvelope)

至于操作教程，没那么难，Google 下即可，当然也可以使用 DuckDuckGo 搜索。不过笔者在此列一些注意事项供读者参考，同时以下注意事项会不定期更新。

* 公私钥对创建之后，不要将公钥上传到公共的的服务器。建议保存在本地，有需要的时候才将自己的公钥发给别人；
* macOS 部分编辑器或者软件无法调用系统的 OpenGPG 服务，所以可以配合浏览器插件 Mailvelope 使用；
* 可以将 PGP Everywhere 设置成键盘，输入文字、选择文本的时候就可以进行加密、解密操作，非常方便；
* Mailvelope 插件注意不要勾选「Remember password temporarily」，建议每一次解密都输入密码；
* 重要邮件使用 PGP 发送，是一个很好的习惯；
* 部分 Cryptocurrency Exchange 支持添加 PGP 公钥，这样 Exchange 发给你的邮件需要读者解密才能查看；
* 隐私是无价的，PGP 的学习成本和使用成本没有想象中那么高；
* 务必保存好私钥、密码。

只要自己的私钥安全、密码安全，可以说只有信息交互的双方才能解密，再顶级的黑客也无能为力。保护隐私非常重要，PGP 就是一个非常实用的利器，希望本文能给注重隐私的读者带来一些帮助。

### Telegram
***

上一篇文章向大家介绍了隐私利器 [PGP](https://dbarobin.com/2019/05/02/privacy-geek-pgp)，好奇的是，读者有去实践吗？如果遇到有任何疑惑，欢迎交流。在博客的 [关于](https://dbarobin.com/about) 页面可以找到联系方式。

隐私极客第 2 篇文章给大家介绍什么呢？读者打开每天必用的软件想了想，选中了 Telegram。关于 Telegram 最好的文章出自霍炬，点击 [此处](https://www.tmtpost.com/1443098.html) 阅读。

![](https://cdn.dbarobin.com/Mo07Awi.jpg)

> 题图来自: © DAN GOODIN / “Privacy is not for sale,” Telegram founder says after being banned in Russia / arstechnica.com

Telegram 作为笔者每天常用的软件，使用频率甚至还超过了微信。Telegram 为什么有如此大的吸引力？笔者认为 Telegram 在即时通讯这事上，足够牛逼。

第一，只需要输入用户名即可发起会话，无需添加好友。当然因为某些不可控因素（如币圈滥用），+86 注册的 Telegram 账户没法和非好友发起会话。

第二，Secret Chat 端对端加密使用的是团队自己设计的加密协议 [MTProto](https://core.telegram.org/api/end-to-end)，曾以 30 万美金的高价 [奖赏](https://telegram.org/blog/cryptocontest) 漏洞的提交者。

第三，普通聊天、群聊、Channel、Bot 多端无缝无时间间隔同步，什么意思呢，每个设备都可以看到这些信息，还不会出现某信那种时不时图裂的情况。自动定位阅读消息记录功能，意思就是上次读到哪里，再次点开还是到哪里，不会出现某信到底部的问题。

第四，支持 Channel、Bot，可以做很多功能扩展。Telegram 上有相当多的有意思的 Channel 和 Bot，读者可以自行挖掘下。

第五，群聊最多 20 万人，然而某信最多 500 人。群聊可以开启置顶群公告，点击直达。配合 Bot，群管理也有新玩法。

第六，可以删除任何单向聊天的任何时间点的信息，包含普通聊天和 Secret Chat，这一点想必足够牛逼了吧。

第七，把某信的撤回修改整合为编辑发送，笔者觉得这个体验相当好。

第八，客户端支持多账号，这一点要秒杀某信了吧，拿着设备想方设法双开也是醉了。

第九，这里没有 Monitor，某信存在隔空拦截的嫌疑，注意笔者说是嫌疑，因为笔者在不确定的事情上不敢妄下结论，不过某些某信用户被封还是常有的事，原因就不得而知了。可能正常使用某信的用户是完全没法理解一个使用了多年的账号被封禁，完全没法登录那种失落感，仿佛整个世界都与你隔绝一般。

第十，不会针对链接做封禁，笔者讨厌 404。还有不会对内容做任何重新排版，这一点笔者也很讨厌。

十一，对大部分网页链接做 Preview 优化（这个功能叫做 Instant View），意思就是不用打开链接就可以预览内容。

好了，实在是太多，笔者编不下去。

如果读者还在说某信体验多好，那是因为没用过 Telegram 吧，too young, too simple, sometimes naive。如果这些理由都不能说服读者使用 Telegram，那还是继续愉快地使用某信吧，反正正常使用 Telegram 也麻烦。

如何优雅地使用 Telegram，这里笔者整理了一些技巧。

第一，在使用 Telegram 之前，阅读 [FAQ](https://telegram.org/faq/en)。

第二，建议使用非大陆手机号注册 Telegram，可以享受完整功能。怎么样获得长期稳定的国外手机号，自行 Google。

第三，Telegram 的普通聊天并不安全，谨慎使用此功能传输敏感信息。如果非用使用普通聊天传输，建议先 PGP 加密。

第四，针对群聊做静音处理，减少消息推送，避免错过重要信息。

第五，善用删除聊天记录功能，避免因为某些言论带来的不必要的烦恼。

第六，学会使用小号，多备几张海外手机号注册账户，应对不时之需。

第七，使用 Telegram 务必注意安全，链接不要乱点，不少骗子通过 Telegram 骗取钱财，如果读者从事区块链行业，相信明白我的意思。

第八，合理使用 Report Spam 功能，防骚扰好习惯。

第九，因为不可抗力，使用 Telegram 需要梯子，谨慎选择梯子，安全最重要。

第十，隐私设置可以调整不少东西。比如可以 Block User、设置谁可见我的上次登录信息，谁可以拉我进群、谁可以给我打语音电话、谁可以看我头像、转发信息设置。安全部分可以设置密码，开启二次验证（建议开启）、管理活跃会话（不活跃的设备可以移除），如果多久没活跃删除账号、是否建议频繁联系人。这些设置强烈建议读者根据需求设置。

Telegram 作为一款注重隐私和安全的及时通讯工具，比同类产品如 Signal、Wire 等有更好的用户群体，对于区块链从业者，依然是最好的及时通信工具。

好了，写到这里吧，希望对读者有所帮助。

### DuckDuckGo
***

上一篇文章给大家介绍了 [Telegram](https://dbarobin.com/2019/05/14/privacy-geek-telegram) 以及值得注意的一些技巧。本文给大家讲讲搜索引擎 DuckDuckGo。

谈到搜索引擎，不得不提到 Google（注意，某度不在讨论范围）。笔者每天使用 Google 的频率相当高，但 DuckDuckGo 依然是 Google 之外的有力补充。关于 DuckDuckGo 的故事，可以阅读 [@virushuo](https://twitter.com/virushuo) 的文章，[穿越寒冬的独行者](https://jhuo.ca/post/ddg)。

![](https://cdn.dbarobin.com/v9mT70u.jpg)

> 题图来自: © DuckDuckGo / DuckDuckGo Privacy Browser / play.google.com

Google 每秒 4 万～8 万次搜索量，强大的计算能力和数据采集能力，可以产生巨大的商业价值。不幸的事，Google track you. DuckDuckGo 主推隐私功能，Yes, [Google tracks you. We don’t.](https://donttrack.us)。此外，读者还可以订阅 DuckDuckGo 的 [博客](https://spreadprivacy.com)。

本文想给读者介绍的，DuckDuckGo 的使用技巧（参考了 [少数派](https://sspai.com/post/40117) 的文章）。

第一，高级搜索技巧。DuckDuckGo 最基础的搜索功能与其他主流产品别无二致，对常见的 OR、-、site:、filetype: 等语法也有良好支持，搜索结果页亦支持通过语言、更新时间等参数进一步过滤结果，不会给从其他搜索引擎切换来的用户施加额外的学习成本。对于进阶用户，DuckDuckGo 也支持通过在 URL 上附加参数（parameter）的方式进行高级搜索。关于支持的参数，参考 [URL 参数](https://duckduckgo.com/params) 页面。

第二，隐私保护中的细节。首先，DuckDuckGo 既不会记录你的 User Agent（用户识别符，用于识别你所用的浏览器）、IP 地址、搜索关键词等被动传来的信息，也不会主动通过 Cookies（网页存储在本地的缓存）等机制识别你的身份。其次，DuckDuckGo 在转发你的访问时，会对请求进行处理，使得第三方网站无法知道你是从其搜索结果页跳转而来。再次，DuckDuckGo 还会自动修改一些主要站点索引的 URL，在你点击访问时指向它们的 HTTPS 地址，以进一步提高安全性。然后，它允许用户通过 POST 方法而非 GET 方法发送搜索请求。启用该选项后，从浏览器地址栏的 URL 中将无法看出你的搜索关键词，因而搜索历史也不会呈现在历史记录中，实现了类似于「隐身模式」的效果。最后，DuckDuckGo 提供 Tor 站点，域名 [3g2upl4pq6kufc4m.onion](https://3g2upl4pq6kufc4m.onion)。如果可以自由地访问 Tor 网络，DuckDuckGo 将是最佳的搜索引擎。

第三，DuckDuckGo 提供 Instant Answers 搜索，极大地减少用户的搜索时间。目前，Instant Answers 支持的各类功能已经有 [1200](https://duck.co/ia) 多个，而且还在不断增加。

第四，DuckDuckGo 有数个自定义配置，除了外观外，还有以下有用的设置：

* General > Safe Search：即其他搜索引擎中的结果过滤，默认为 Moderate（适中），可按需调为严格或关闭。
* General > Advertisements：尽管 DuckDuckGo 上的广告已经非常克制，你仍可在此将其全部关闭。
* General > New Window：开启后，在搜索结果页面点击链接会在新窗口中打开，如果你习惯一口气打开多个结果链接再慢慢筛选，该选项非常实用。
* Privacy > HTTPS：默认为开启。如果关闭，可能会访问到部分网站的非 HTTPS 版本。
* Privacy > GET requests：默认为开启。如果关闭，DuckDuckGo 将使用 HTTP 中的 POST 方法而非 GET 方法来发送你的搜索请求。

第五，设置的同步。如果想将自己的偏好设置在多个设备上使用，就需要同步机制的帮助。对此，几乎所有网站采取的都是账号机制。但多一个账号就多一分隐私外泄的风险，以保护隐私为己任的 DuckDuckGo 显然不会放过这个漏洞。在 DuckDuckGo 设置页面的 「Cloud Save」（云端保存）部分点击 「Save Settings」 按钮，网页会要求你输入一段密码，或者直接点击「Suggest a pass phrase」自动生成一个，然后点击「Save」保存。这样，你的偏好设置就被保存在了 DuckDuckGo 的服务器中；其他设备上，只要在同一页面上点击「Load Settings」并输入密码，即可载入设置，而新的更改也会在设备间同步。

第六，支持 Bangs 功能。Bang 的运行机制很简单，只要在你的搜索关键词之前（或结尾）加上一个以半角感叹号！开头的标识符（称为 bang），DuckDuckGo 就会替你调用这个 bang 所指向的搜索引擎或网站进行搜索。这个功能有意思的是，DuckDuckGo 里使用其他搜索引擎进行搜索，并且 Bangs 转发的搜索是完全匿名的。

第七，短域名 [dgg.gg](https://dgg.gg) 可以跳转到 DuckDuckGo 搜索引擎。

第八，可以直接搜索 Twitter 用户，比如输入「**@vrwio**」可以在 DuckDuckGo 展示笔者的 Profile。

第九，可以直接生成随机密码，关键词 password 或 random password。比如输入「**password 20**」或者「**random password 20**」，将会生成一个长度 20 的随机密码。在某些一次性注册的网站上，这个功能比较好使。

第十，支持为链接生成二维码，关键词 QR。比如输入「QR https://dbarobin.com」将会生成笔者博客链接的二维码。

十一，快速改变大小写，关键词 lowercase 和 uppercase。比如「**lowercase ROBIN**」将会把 ROBIN 改为小写，「**uppercase robin**」将会把 robin 改为大写。

十二，快速展示日历，关键词 calendar。比如输入「**calendar 20190607**」将会展示今天的日历。

十三，支持缩短 URL，关键词 shorten，比如输入「shorten https://dbarobin.com」将会获得短域名。

十四，快速查找 HTML 代码，关键词 html，比如输入「**html >**」将会获得大于符号的 HTML 代码。

最后，DuckDuckGo 配合 Firefox，可以打造最佳隐私搜索利器。下一篇文章将为大家讲件 Firefox。

当然，更多的技巧需要读者去探索，DuckDuckGo 可以作为 Google 有力的补充或者替代。不过不幸的是，DuckDuckGo 像 Google 一样无法摆脱被墙的命运。

DuckDuckGo 不过滤结果，不追踪你的搜索记录，把搜索引擎隐私发挥到了极致，帮助你在 Cyberspace 中自由流荡。

### Firefox
***

上一篇文章讲解了 [DuckDuckGo](https://dbarobin.com/2019/06/07/privacy-geek-duckduckgo)，提到 DuckDuckGo 适合 Firefox 配合使用，本篇文章就为大家讲解 Firefox。

![](https://cdn.dbarobin.com/kkqHnTR.jpg)

> 题图来自: © Tim Murray / Firefox: The Evolution Of A Brand / blog.mozilla.org

Firefox 可以说是黑客利器，连 Tor Browser 都是基于 Firefox ESR 的。Firefox 相比其他浏览器有什么优势呢（国内毫无操守的浏览器就不再此讨论范围）？

第一，开发 Firefox 的 Mozilla 是一个「非营利组织」；而开发 Chrome 的 Google 是一家「商业公司」。商业公司想要的是从用户的数据获取更多的利益，而非赢利组织可以坚持操守。Google 的利润，90% 以上是来自于广告收入。广告讲究「精准投放」，Google 必须要采集海量数据才能做到，因为，对于追求隐私的用户而言，Chrome 并不是什么好的选择。

第二，2017 年 11 月 14 日，Firefox Quantum 的第一个通用版本发布，意味着 Firefox 更快了。Firefox Quantum 引入了 Servo 引擎，该引擎由 Rust 开发。在之前的版本，Firefox 使用的引擎叫做 Gecko，由 C++ 开发。 Rust 作为一门新的编程语言，它一方面可以达到与 C/C++ 相同的性能，另一方面又避免 C/C++ 在内存和多线程方面的弊端。

第三，Firefox 使用自带 CA 证书，而 Chrome 使用了操作系统提供的 CA 证书。这样有什么好处呢？自带的 CA 证书不会受到操作系统及其厂商的影响。

第四，Firefox 定制化比 Chrome 强，读者可以按照自己的需求定制强大无比的浏览器。

讲解完 Firefox 的优势，接下来为大家说说使用 Firefox 都活哪些技巧。

第一，将默认引擎设置为 [DuckDuckGo](https://duckduckgo.com)，原因不再赘述。

第二，将 Firefox 打造为隐私浏览器，设置方法如下：

* Firefox 打开 about:preferences#privacy，Content Blocking 选择 Custom，然后勾选「Trackers」，接着选择「In all windows」；
* Send websites a “Do Not Track” signal that you don’t want to be tracked 选择 「Always」；
* Cookies and Site Data，如果是永久的隐身模式，「Delete cookies and site data when Firefox is closed」会默认勾选；
* History 勾选「Never remember history」；
* Permissions 勾选：「Block websites from automatically playing sound」、「Block pop-up windows」、「Warn you when websites try to install add-ons」、「Prevent accessibility services from accessing your browser」；
* Firefox Data Collection and Use，所有的选型都不勾选，不允许采集数据；
* Security，Deceptive Content and Dangerous Software Protection 都勾选；
* Certificates，When a server requests your personal certificate 选择「Ask you every time」，「Query OCSP responder servers to confirm the current validity of certificates」勾选。

做完上述的设置，让 Firefox 浏览器成为真正的无痕浏览。

第三，安装必备插件，如 DuckDuckGo Privacy Essentials、Mailvelope、Greasemonkey、NoScript、HTTPS Everywhere，安装完之后，大部分的插件，Run in Private Windows 需要勾选「Allow」。其他插件感兴趣可以 DuckDuckGo 搜索下。

第四，Firefox 有 Firefox Monitor 服务，可用来查询使用者的电子邮件地址是否曾经出现在外泄的数据库中。该服务由 Mozilla 和 HaveIBeenPwned.com 合作推出，当用户在 [https://monitor.firefox.com](https://monitor.firefox.com) 网站上输入自己的邮箱地址时，系统就会比对由 Have I Been Pwned 所搜集的外泄资料库（包含来自中国网站和服务泄漏的数据），倘若查询到符合的资料，会具体显示该电子邮件曾出现在哪些外泄事件中，用户则应该立即去修改密码。此外，从 Firefox 70 开始，如果浏览器保存的登录信息出现在已暴露数据库内 Mozilla 将会发出警告。

注重隐私未来是大势所趋，Firefox 浏览器将成为这部分用户的首选。Chrome 和 Google 的服务绑定太深，抛开 Chrome，选择还有很多。

### Google Voice
***

上一篇文章讲解了 [Firefox](https://dbarobin.com/2019/07/21/privacy-geek-firefox)，提到 Firefox 的使用技巧。本篇文章为大家讲解 [Google Voice](https://voice.google.com)。

可能读者不太清楚 Google Voice 是啥，笔者简单介绍下。

> Google Voice 是由 Google 推出的 VOIP 服务，能够将个人所用的众多 电话号码集中成为一个号码，同时提供许多加值服务，它在美加地区提供的免费语音通话和短信服务。该服务由 Google 于 2009 年 3 月 11 日收购 GrandCentral 后推出，并且从 2009 年 6 月开始邀请一些志愿者参与实验。[1]

![](https://cdn.dbarobin.com/obnPQWM.jpg)

> 题图来自: © Abhiman Biswas / Google Voice VoIP starts rolling out: will be available to everyone within a week / 91mobiles.com

Google Voice 有啥用处呢？简单讲就是可以快速拥有一个美国手机号，注册一些没那么重要或者大陆手机号没法注册的服务。在某个丝毫不注重隐私的国度，保护自己的手机号隐私居然会被嘲笑。Google Voice 可以做到半匿名，在一些没那么重要或者敏感的服务注册上可以派上用场。

当然，N 年之前还可以自行注册，被某国羊毛党发现套利机会之后，自行注册的成本已经相当高，普通用户完全没法实现。N 年前，大陆手机号还可以注册 Google 账号，现在已经不行了，Fuck。如果读者确实需要，可以去某宝搜索「Google Voice」，不是特别贵。当然，买来的 Google Voice 绑定在一个特定的 Google 账号，强烈建议更改此账户密码，把之前登录过此账户的设备删掉，并且开启二次验证。

Google Voice 可以用来接收短信、打电话，前提是要科学上网。除此之外，Google Voice 对于一个区块链从业者而言，实在是太有必要，读者可以自行琢磨。

如果读者有朋友在美国或者有自己去美国的计划，可以代购或者购买 [Google Fi](https://fi.google.com)，这东西除了资费贵之外，几乎是最完美的全球网络解决方案。Google Fi 可以绑定之前的 Google Voice 号码，也可以申请新的，相当方便。

隐私应该是个人坚决捍卫的权利，Google Voice 是每个注重隐私保护的读者必备利器。

### 国内手机号
***

上一篇文章讲解了 [Google Voice](https://dbarobin.com/2019/08/10/privacy-geek-google-voice)，提到 Google Voice 的使用技巧。本篇文章为大家讲讲国内手机号。

只要读者使用国内手机号，或多或少会收到各种各样的骚扰电话、短信。不用质疑，各种渠道买卖数据的渠道很多。此时此刻，有可能读者的数据就被打包交易着。

然而，在国内不可能不使用手机号。手机号的重要性等同于身份证，各种应用、会员、政务等都需要，没有手机号可能什么都做不了。

在不得不用的前提下，还是有些保护手机号隐私的技巧，且听笔者娓娓道来。

![](https://cdn.dbarobin.com/u7c3Emz.png)

> 题图来自: © Brian Donohue / The Nine Most Secure and Private Internet and Mobile Messaging Services / kaspersky.co.in

第一，区分手机号的使用场景，也就是要用好主力号、小号、工作号、一次性号。针对银行等重要的业务，使用主力号；工作相关的场景，使用工作号；外卖、快递等需要暴露手机号的场景，使用小号；只是为了试用或者某些特殊场景，使用 Google Voice 或者一次性号，这些平台可以 Google 或者 DuckDuckGo 搜索。

第二，备份。备份有个前提就是不要使用国内任何通讯录软件备份。建议自行导出为 vcf 文件备份。如果要使用在线备份，可以考虑 Google 或者美区 Apple ID。

第三，关闭 iMessage。如果读者开启了 iMessage，恭喜你，会不定期收到澳门性感荷官在线发牌等骚扰短信。

第四，防骚扰。这部分包含电话、短信。Android 手机使用系统自带的即可，国产手机基本上都有定制，比如一加在「通讯录，设置，陌生号码识别」，可以精准地标识骚扰号码。iOS 没有多少选择，腾讯手机管家可以考虑。如果是短信防骚扰的话，还有一个「熊猫吃短信」可以试试。

第五，特殊场景电话录音。iOS 实现录音很困难，可能还需要借助硬件设备。Android 就比较方便，比如一加就自带了电话录音功能。为什么要录音呢？如果读者从事律师或者某些敏感的职业，这个还是比较重要的。

第六，应用权限。联系人、通话记录这个权限要谨慎授予。iOS 可以比较自如地控制权限，Android 相对会糟糕很多，据说 Android Q 会借鉴 iOS 的设计。此时此刻，建议读者放下手机，认真检查下手机里的应用，不需要授予联系人、通话记录权限的应用，建议第一时间取消。

第七，开启匿名号码。类似美团、神舟专车这样的服务，下单可以选择匿名小号，这样的话，外卖小哥或者司机只能通过匿名小号拨打过来，读者自己的手机号不会直接泄漏给外卖小哥或者司机。这个的实现原理就是平台给注册手机号分配一个和外卖小哥/司机关联的虚拟号，只有这个订单涉及的双方才能通话，出现纠纷平台再介入协商处理。

第八，不要随意对外派发带手机号的名片，即使需要派发名片，建议放一个工作小号。

第九，微信、支付宝不要开启手机号搜索，即使开启，也不要绑定对外暴露的手机号，这样会少很多麻烦。

第十，千万不要在公开的渠道、博客暴露自己的手机号。笔者平时阅读博客，经常会看到不少作者在关于页面留下个人手机号，这样是相当不妥的，互联网有无数的爬虫没日没夜地抓取数据。

笔者将平时在践行的以及了解到的技巧分享给大家，希望大家少收到些骚扰电话或者短信。也期待 iOS 和 Android 系统在手机号这个隐私上多下功夫。

### Gmail
***

上一篇文章讲解了 [国内手机号](https://dbarobin.com/2019/08/18/privacy-geek-mobile)，提到国内手机号的一些使用技巧。本篇文章为大家讲讲 Gmail。

目前国内网民使用最多的邮箱：QQ 邮箱、163 邮箱，然而这两家在安全上做的功夫显然不足。因为众所周知的原因，Google 服务几乎不可访问，也包括本文提到的 Gmail。可能读者好奇，现在微信、QQ 等社交软件这么方便，为什么还要使用邮箱呢？笔者认为，邮箱的沟通效率并不见得低，当你准备给他人发送邮件的时候，自动开启详细描述模式。如果读者使用较多的境外服务，获取帮助最佳的渠道也是给客服发送邮件。邮箱并不仅仅是接收一个验证码。

笔者先为大家介绍下 Gmail。

> Gmail 是 Google 公司在 2004 年 4 月 1 日发布的一个免费电子邮件服务。Gmail 在最初推出时，新用户需要现有用户的电子邮件邀请。2007 年 2 月 7 日 Google 宣布将 Gmail 的注册完全开放。2009 年 7 月 7 日正式取消 Beta 标志，在推出 5 年多后终于转为正式版本。[1]

![](https://cdn.dbarobin.com/F6rwzBy.jpg)

> 题图来自: © MATTHEW HUGHES / Hang on, you can @ people in Gmail? / thenextweb.com

目前靠正常的渠道基本上无法注册 Gmail，因为大陆手机号无法接收验证码。读者可以自行想点办法，本文不赘述。

接下来笔者给大家讲讲 Gmail 的使用技巧。

第一，高级搜索和过滤器。Gmail 支持多种维度搜索，非常强大。过滤器简单来说就是分组或者保存搜索视图，我们可以设定不同的搜索条件，然后把这些搜索条件保存过滤器，对所有邮件批量处理，包括统一加标签，统一删除，统一存档等等。Gmail 的过滤器功能应该是邮箱服务最强，对于邮件重度用户来说，非常实用。

第二，取消「已经发送」的邮件。因为失误可能收件人填写错误或者不全，又或者内容有错误或需要补充，此时需要的就是邮件撤回功能。在 Gmail 的常规设置，「Undo Send」选项，可以设置最多 30 秒的撤回时间。

第三，离线使用 Gmail。在设置里有离线「Offline」选项，用户开启之后可以在没有网络的情况下阅读、搜索、归档邮件。

第四，取消订阅各种推广邮件。如果读者注册了较多的服务，邮箱经常会收到推广邮件，此时读者可以使用 [Unroll.me](https://unroll.me) 服务取消订阅。

第五，安全措施，设置强密码，务必开启两步验证。Gmail 也是非常重要的账号，强烈建议开启二次验证，软件叫做 Google Authenticator。

第六，自定义标签。读者可以为邮件标记各种各样的标签，方便后续搜索。

第七，正确使用星标、归档、删除等功能。Gmail 是目前所有邮件系统中蕴含 GTD 理念中最好的，强烈建议读者区分星标、归档、删除邮件功能，不错过任何事项，也更佳高效地管理事务。

第八，快捷键功能。Gmail 支持相当多的快捷键，对于键盘党来说，真是福音。

第九，设置中的高级列表（以前叫做实验室），可以开启一些新的功能，比如「Auto-advance」这个自动打开下一封邮件的功能，笔者就相当喜欢。

第十，Gmail 可以做到一个账号多用。Gmail 在处理邮箱地址上，有两个特殊的字符（ + . ），而我们通过嵌入两个特殊字符到 Gmail 地址上，日后如果因为一些应用网站暴露安全问题，被黑客取得了自己的邮箱，那我们至少可以知道是哪一个应用网站泄漏了自己的邮箱。比如读者的邮箱是：userexample@gmail.com，那 userexample+xyz@gmail.com、user.example+x.y.z@gmail.com 都是新的地址，而且可以关联到原有邮箱。这样组合的话，就可以产生无数的邮箱地址了。

Gmail 是笔者最为常用的邮箱服务。据笔者所知，Gmail 足够安全，Google 本身提供的漏洞奖金计划也特别良心。笔者不建议使用国内的任何邮箱服务，有条件还是要使用 Gmail 的。希望本文提供的技巧对读者有所帮助。

### ProtonMail
***

上一篇文章讲解了 [Gmail](https://dbarobin.com/2019/10/01/privacy-geek-gmail)，提到注册 Gmail 的必要性以及一些使用技巧。本篇文章为大家讲讲另一个邮箱服务 ProtonMail。

早在 2017 年，余弦在「懒人在思考」中推荐了 ProtonMail。余弦列举了 13 条 ProtonMail 的优势，诸如开源、点对点加密、注册不需要个人隐私、服务器在瑞士、安全、支持 Tor 等等。[1]

可能读者对 ProtonMail 比较陌生，笔者先为大家介绍下 ProtonMail。

> ProtonMail（在中国被非正式地称为「质子邮箱」）是一个加密的 Webmail 服务，于 2013 年由欧洲核子研究组织（CERN）成员 Jason Stockman、Andy Yen 和 Wei Sun 创建。ProtonMail 现由总部设在瑞士日内瓦州的 Proton Technologies AG 经营。据 Andy Yen 称，他和公司一半的人都来自麻省理工学院（MIT），ProtonMail 的两个服务器分别设在瑞士的 Lausanne 和 Attinghausen。[2]

![](https://cdn.dbarobin.com/LKQtQIZ.jpg)

> 题图来自: © ProtonMail / Secure email: ProtonMail is free encrypted email. / protonmail.com

接下来笔者为大家讲解下 ProtonMail 使用技巧。

第一，ProtonMail 注册无需绑定手机号，甚至无需提供手机号之外的任何隐私。不过值得注意的是，ProtonMail 也有防刷策略，一个登录 IP 不允许注册过多的账号。如果被 ProtonMail 风控了，需要提供辅助邮箱或者手机号以验证人工操作。

第二，注册好 ProtonMail 之后，强烈建议开启二次验证。二次验证之外，还有 Mailbox 密码，也建议设置。也就是说，这些都开启之后，正常登录 ProtonMail，需要邮箱名 + 登录密码 + 二次验证 + Mailbox 密码。

第三，ProtonMail 有「Automatically save contacts」功能，也就是自动保存联系人，根据需求启用。

第四，ProtonMail 的 Tor 服务网址：[https://protonirockerxow.onion/](https://protonirockerxow.onion/)，打开速度取决于梯子质量。如果 Tor 浏览器启用了 NoScript，记得信任此网址。最新的 Tor 地址，点击 [此处](https://protonmail.com/tor)。

第五，ProtonMail 免费账号支持有限，PLUS 支持自定义域名等更多服务，当然还有 PROFESSIONAL 和更高级别的 VISIONARY 套餐。PLUS 支持自定义域名，也就是说读者可以拥有一个自定义域名的邮箱。此外，支持 BTC 订阅，对于将隐私发挥到极致的 Geek 们，这个特性相当给力。

第六，支持关闭登录日志，这个功能是默认开启的，也就是说默认 ProtonMail 不会记录你的登录 IP。

第七，支持将邮件内容签名并以附件的形式发给联系人。开启后，每封发给对方的邮件，都会将签名后的附件附加到邮件。

第八，支持自动附加 PGP 公钥。开启后，每封发给对方的邮件，都会将 PGP 公钥附件附加到邮件。

第九，支持邮件地址验证，详情参考 [https://mail.protonmail.com/security](https://mail.protonmail.com/security)「Address Verification」功能。

第十，ProtonMail 提供 ProtonVPN 服务，支持 Windows、Mac、GNU/Linux、iOS、Android，有需求可以订阅。

十一，ProtonMail 支持自定义主题。感兴趣关注以下几个主题来源：

* [ProtonMail Themes](https://protonmail.tumblr.com/)，官方维护的主题列表
* [Easy Themes for ProtonMail](https://github.com/amdelamar/pm-theme)，[amdelamar](https://github.com/amdelamar) 维护的 GitHub 项目，支持多个主题
* [ProtonMail theme creator](https://scastiel.gitlab.io/protonmail-theme-creator/)，主题生成器

在 Gmail 之外，ProtonMail 是一个相当不错的邮箱补充服务。ProtonMail 在安全和隐私方面做到了极致，强烈建议读者用起来。

### Apple ID
***

上一篇文章讲解了 [ProtonMail](https://dbarobin.com/2019/10/13/privacy-geek-protonmail/)，提到 ProtonMail 的一些使用技巧。本篇文章为大家讲讲大家习以为常的 Apple ID。

![](https://cdn.dbarobin.com/r4WF9jd.jpg)

> 题图来自: © Apple / Education Pricing and Student Discounts / apple.com

笔者之前的文章，[你至少需要一个美区 Apple ID](https://dbarobin.com/2019/03/02/us-apple-id/) 一文中解释了美区 Apple ID 的重要性。Android 生态有很多机型可以选择，但 iOS 系设备依然无可替代。主要原因有以下几点：第一，消息推送，iOS 的消息通知是真优秀，Android 相比就会弱很多，程序一旦进入后台就有可能收不到消息推送了；第二，权限管理。iOS 奉行「权限最小化」原则，只有当 App 需要相关权限才会向用户索取，用户完全可以选择接受或拒绝。而 Android 设备催生了无数的权限滥用案例。不过 Android 10 对 [权限管理](https://sspai.com/post/56538) 做了相当多的优化，Android 用户倒是可以期待下。第三，优质应用。iOS 上的优质应用，总体上是多于 Android 的。用户在 iOS 平台购买付费应用也相对方便，然而 Android 下的 Google Play 购买软件就没那么方便了。有个说法，一台不能科学上网的 Android 手机，就等于残废。我觉得就这 3 点，iPhone 作为主力机还是相当靠谱的。

因为 Apple 对中国政府的妥协，Apple 生态才得以在中国稳健发展，但与之带来的就是对于隐私的担心。比如国区 Apple ID 的 iCloud 功能，目前已由云上贵州托管。笔者在得知这个消息之后，果断注销了果区 Apple ID 的 iCloud。目前完全迁移到美区 Apple ID，App Store、iCloud 用起来也相当顺手。作为区块链从业者，拥有一个美区 Apple ID 也相当重要，毕竟很多行业应用都没法在国区上架。

说了这么多，接下来笔者为大家讲解下 Apple ID 的使用技巧。

第一，不建议在淘宝购买 Apple ID，这个账号读者要长期使用的，怎么能把如此重要的账号让他人代为注册。

第二，注册美区 Apple ID 相当简单，有一个美国的 IP 即可。

第三，如果是币圈用户，千万不要登录交易所或者钱包提供的 Apple ID 来下载软件。有鲜活的例子证明，部分用户习惯将助记词截图存到手机，登录他人提供的 Apple ID，如果 iCloud 开启了同步图片，稍不注意就会把本地的图片上传，然后这个 Apple ID 又是公共的，读者的敏感信息就被他人轻而易举地获取了。再者，将助记词截图存到手机这样的傻逼行为，还是不要做了吧。

第四，使用 iCloud 也奉行最小同步原则，不必要的就不要同步。

第五，强烈建议为 Apple ID 开启二次验证。Apple ID 的密码也尽可能复杂，建议用 1Password 管理。

第六，手机上的 Find My iPhone 功能强烈建议开启，万一手机丢失，还可以远程抹掉手机的数据，尽可能减少损失。

第七，美区 Apple ID 搞定支付也不难，思路如下：准备一张单标的信用卡，然后注册美区 PayPal，接着将美区 Apple ID 和美区 PayPal 绑定即可。

第八，如果读者还在使用国区 Apple ID，强烈建议不要将敏感信息同步到 iCloud，也建议将备份放到 Mac。

以上建议和技巧希望能够给读者带来帮助，Apple ID 的安全和隐私非常重要，读者千万不能掉以轻心。

## 如何订阅
***

为了安全起见，读者只有四个渠道订阅本专栏，第一是本博客，RSS 订阅点击 [此处](https://dbarobin.com/feed.xml)。第二是在线小册，[https://privacy.dbarobin.com](https://privacy.dbarobin.com)。第三是 Telegram Channel，名叫 [隐私极客](https://t.me/privacygeek)。第四是 Mixin Channel，下载安装 [Mixin Messenger](https://mixin.one/messenger) 之后，访问 [mixin://users/b8f7e6e4-9ac2-4a85-9b17-257faac2d8d6](mixin://users/b8f7e6e4-9ac2-4a85-9b17-257faac2d8d6) 订阅。博客以文章为主，Telegram Channel 内容多样化且碎片化（图片、音频、视频、文字、链接等），Mixin Channel 作为同步渠道。归档页面点击 [此处](https://dbarobin.com/privacy/)。

## 关于作者
***

Robin，博主，区块链创业者。[https://dbarobin.com](https://dbarobin.com) · [dbarobin@github](https://github.com/dbarobin)

## 关于小册
***

> 本小册持续更新中。

这是一个写了半年的专栏，归档页点击 [此处](https://dbarobin.com/privacy/)。

为了方便阅读检索，特制作在线小册，以飨读者。

## 关于版权
***

采用「[创意共享 4.0 许可证](https://creativecommons.org/licenses/by-nc-nd/4.0/deed.zh)」，非商用，非衍生，保持署名。