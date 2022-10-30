# 如何利用 Kali Linux 入侵您自己的网络并增强其安全性

> 原文:[https://life hacker . com/how-to-hack-your-own-network-and-beef-up-its-security-w-1649785071](https://lifehacker.com/how-to-hack-your-own-network-and-beef-up-its-security-w-1649785071)

[Kali Linux](http://www.kali.org/) 是一个安全的操作系统，你可以在任何地方从 CD 或 USB 驱动器上运行。通过它的安全工具包，你可以破解 Wi-Fi 密码，创建假网络，并测试其他漏洞。以下是如何使用它给你自己的网络进行安全检查。

Watch

*这篇文章是我们 Lifehacker 的* [*邪恶周*](https://lifehacker.com/welcome-to-lifehackers-fifth-annual-evil-week-1647621043) *系列的一部分，在这里我们看到了做事的阴暗面。知道邪恶意味着知道如何打败它，所以你可以用你的邪恶力量做好事。想要更多吗？查看我们的* [*恶周标签页*](http://lifehacker.com/tag/evilweek) *。*

Kali Linux 包含大量软件，用于测试网络中的安全漏洞。这里有太多的工具可以列出来，但是我们对它如此着迷，以至于我们决定挑选几个我们最喜欢的工具来展示它们是如何工作的:Aircrack、Airbase 和 ARPspoof。我们将向您展示如何用暴力破解 Wi-Fi 密码，创建一个假路由器来欺骗机器登录，并执行中间人攻击来窃听网络通信。记住:用这些能力做好事，不要做坏事。知道如何做这些事情可以让你摆脱困境，或者帮助你学会保护自己的网络，但是我们不建议对别人做这些事情。

### 用 Aircrack 破解 WPA Wi-Fi 密码

Kali Linux 附带了一整套用于破解 Wi-Fi 网络的应用，包括 Aircrack 和 Reaver——这两个应用我们之前都分别提到过 [破解 WEP](https://lifehacker.com/how-to-crack-a-wi-fi-networks-wep-password-with-backtra-5305094) 和 [WPA 密码](http://lifehacker.com/how-to-crack-a-wi-fi-networks-wpa-password-with-reaver-5873407) 。

然而，WEP 密码已经不那么流行了(因为它们很容易被破解)，而且 Reaver 只有在网络启用了 WPS 的情况下才有效。所以今天，我们要再看看 Aircrack，用它来强行进入 WPA 网络(借助密码列表)。

#### 第一步:配置您的无线网卡

首先:断开所有无线网络。然后打开终端。为了使用 Aircrack，您需要一个支持注射的无线网卡。在终端中键入以下内容，以确保您的卡支持它:

```
airmon-ng
```

这列出了所有支持此破解的无线网卡。如果你的卡不支持注射，它不会显示在这里。您的接口可能列为 wlan0，但这可能取决于您的机器。

接下来，键入:

```
airmon-ng start wlan0
```

用您卡的接口地址替换`wlan0`。您应该会收到一条消息，说明 monitor 模式已启用。

#### 第二步:监控你的网络

接下来，您将获得您所在区域的所有网络列表，并监控您的网络。

键入:

```
airodump-ng mon0
```

您将看到您所在区域的所有网络。从列表中找到您的网络，复制 BSSID，同时记下它所在的频道。点击 Ctrl+C 停止该过程。

接下来，键入以下内容，用上面收集的信息替换括号中的信息:

```
airodump-ng -c (channel) --bssid (bssid) -w /root/Desktop/ (monitor interface)
```

它应该是这样的:

```
airodump-ng -c 6 --bssid 04:1E:64:98:96:AB -w /root/Desktop/ mon0
```

现在，你将监控你的网络。您应该会看到桌面上弹出了四个文件。现在不用担心那些；你以后会需要它们中的一个。下一步有点像等待游戏，因为您将坐着等待设备连接到网络。在这种情况下，只需打开您拥有的设备并连接到您的 Wi-Fi。你应该看到它作为一个新的电台弹出。记下站号，因为在下一步中会用到它。

#### 第三步:捕捉握手

现在，您将强制重新连接，以便捕捉计算机和路由器之间的握手。让 Airodump 保持运行，并在“终端”中打开一个新标签。然后键入:

```
aireplay-ng -0 2 -a (router bssid) -c (client station number) mon0
```

它应该看起来像这样:

```
aireplay-ng -0 2 -a 04:1E:64:98:96:AB -c 54:4E:85:46:78:EA mon0
```

现在，您将看到 Aireplay 向您的计算机发送数据包以强制重新连接。跳回到 Airodump 标签，你会看到一个新的号码列在 WPA 握手之后。如果有，你已经成功地抓住了握手，你可以开始破解密码。

#### 第四步:破解密码

您现在已经有了加密形式的路由器密码，但是您仍然需要弄清楚它到底是什么。为此，您将使用一个密码列表来尝试强行进入网络。您可以在网上找到这些列表，但是 Kali Linux 在/usr/share/wordlists 目录中包含了一些小列表来帮助您入门，所以我们将只使用其中的一个。要开始破解密码，请键入以下内容:

```
aircrack-ng -a2 -b (router bssid) -w (path to wordlist) /Root/Desktop/*.cap
```

所以，继续我们上面的例子，使用一个内置的单词表，它应该是这样的:

```
aircrack-ng -a2 -b 04:1E:64:98:96:AB -w /usr/share/wordlists/fern-wifi/common.txt /Root/Desktop/*.cap
```

现在，Aircrack 将尝试所有这些密码，看看是否有一个合适的。如果是这样，您会收到一条消息，说找到了带有密码的密钥。如果没有，尝试另一个密码列表，直到找到一个有效的。密码列表越大，这个过程需要的时间就越长，但是你成功的机会就越大。

#### 如何使用这些信息来保持安全

所以，你就强行进入了你自己的网络。取决于你的密码有多好，它要么花了你五分钟，要么花了你五个小时。如果你的密码很简单，比如“password123”，那么很有可能是一个较小的单词列表能够很快破解它。如果它更复杂，它可能需要很长时间或者根本没有出现密码(如果是这样:对你有好处！).

这里最好的保护是在你的路由器上有一个 [好，强密码](https://lifehacker.com/four-methods-to-create-a-secure-password-youll-actually-1601854240) 。越长、越古怪、越复杂越好。同样，确保您使用的是 WPA2 安全协议，并且没有启用 WPS。

### 用空军基地创建一个假网络

接下来，让我们来看看如何伪造网络地址来欺骗人们登录到错误的网络，这样您就可以看到他们在做什么。黑客可能会这样做，所以你登录到假网络，认为这是你的真实网络，然后执行中间人攻击(下一节将详细介绍)，从你的流量中收集关于你的信息。使用 Kali Linux 中的一个叫做 Airbase 的工具，这非常容易做到。

本质上，您将把 Kali Linux 上的 Wi-Fi 适配器变成与另一个网络同名的接入点。为了做到这一点，你将遵循和上面一样的研究路线，但是结局有点不同。

#### 第一步:配置您的无线网卡

就像上次一样，您需要设置您的无线网卡来监控流量。打开终端并键入:

```
airmon-ng
```

这列出了所有支持此破解的无线网卡。您的接口可能列为 wlan0。

接下来，键入:

```
airmon-ng start wlan0
```

现在你处于监控模式。是时候找到你要恶搞的网络了。

#### 第二步:找一个 Wi-Fi 网络来恶搞

为了欺骗路由器，你需要一些关于它的信息。所以，输入:

```
airodump-ng mon0
```

您将看到您所在区域的所有网络。从列表中找到您的网络并复制 BSSID，同时记下其名称和所在的频道。这就是你要恶搞的路由器。点击 Ctrl+C 停止该过程。

#### 第三步:创建一个虚假的网络

现在，你要用空军基地创建一个假网络。键入以下内容，替换您在上一步中为括号收集的信息:

```
airbase-ng -a (router BSSID) --essid "(network name)" -c (channel) mon0
```

例如，它应该是这样的:

```
airbase-ng -a 04:1E:64:98:96:AB --essid "MyNetwork" -c 11 mon0
```

就是这样。现在，您已经欺骗了路由器，并创建了一个具有相同名称、通道和 SSID 号的克隆，因此它与原始路由器无法区分。不幸的是，该网络上的计算机将总是自动连接到具有该名称的最强大的路由器，因此您需要打开您的假网络的电源。键入:

```
iwconfig wlan0 txpower 27
```

这将你的假网络的能量提升到最大接受极限，所以希望下次他们登录时，他们能自动连接到你。只要你不超过 27，它应该不会对卡造成任何损害。一旦他们这么做了，就好像你们都在同一个网络上。这意味着你可以很容易地访问他们正在做的任何事情。

#### 如何使用这些信息来保持安全

欺骗网络是很难发现的，但是当网络流量很慢，或者突然不需要密码验证时，您通常可以发现它。如果你真的怀疑有人在欺骗路由器，你可以关闭自动连接 Wi-Fi 的功能，这样你至少有时间看看你正在登录的路由器。

### 利用 ARP 欺骗的中间人攻击窥探另一台设备的流量

中间人攻击本质上是在窃听你的网络。在这里，您将在计算机没有意识到的情况下拦截计算机和路由器之间的网络信号。我们已经向您展示了如何进行 [数据包嗅探](https://lifehacker.com/how-to-tap-your-network-and-see-everything-that-happens-1649292940) ，今天我们将使用 ARP 欺骗来收集这些信息。这两种嗅探欺骗都是关于监听对话，但它们的工作方式略有不同。嗅探通过监控网络来捕获流量，欺骗伪装成该网络。这些类型的攻击通常被用来获取密码、图像以及你通过网络发送的几乎任何东西。

#### 第一步:打开数据包转发

首先，您需要让您的 Kali Linux 机器转发它收到的任何流量，以便目标计算机仍然可以访问互联网。在命令行中键入以下内容:

```
echo 1 > /proc/sys/net/ipv4/ip_forward
```

这将确保所有信息在被拦截后都被转发。这样，路由器和目标计算机之间的互联网和任何其他通信将继续工作。

#### 第二步:打开 ARP 欺骗

现在你需要打开 ARP 欺骗。这会欺骗计算机和路由器，让它们认为你的 Wi-Fi 适配器是一个网桥。成功欺骗后，您可以监控设备之间的所有流量。您将这样做两次，以便能够捕获从路由器到您的计算机的流量，以及从您的计算机到路由器的流量。

要从您的路由器捕获流量，请键入以下内容，并用您的网络信息替换括号:

```
arpspoof -i wlan0 -t (router address) (target computer address)
```

你会看到一串数字输出，显示它正在运行。让它保持运行，然后在“终端”中打开另一个标签，执行相反的操作:

```
arpspoof -i wlan -t (target computer address) (router address)
```

两行应该看起来像这样:

```
arpspoof -i wlan0 -t 192.168.1.1 192.168.1.105
```

```
arpspoof -i wlan0 -t 192.168.1.105 192.168.1.1
```

现在，这两台机器之间的所有流量都被收集在 Kali Linux 中。有很多工具可以捕捉这些信息，但是让我们来看看其中的几个。

要跟踪电脑访问的任何 URL，请打开另一个终端标签并键入:

```
urlsnarf -i wlan0
```

这将显示计算机访问的所有网站。

如果您对图像更感兴趣，您也可以捕捉任何图像流量。键入:

```
driftnet -i wlan0
```

将弹出一个窗口，显示他们通过网络加载和传输的任何图像。基本上，如果有任何未加密的信息在路由器和计算机之间发送，你会看到它发生。

#### 如何使用这些信息来保持安全

防止人们利用 ARP 欺骗您的网络的最好方法是用强密码保护您的网络，并确保他们不在那里。也就是说，在你的电脑 上打开一个 [防火墙也会有所帮助。此外，确保你总是使用可用的](https://lifehacker.com/how-to-turn-your-computers-firewall-on-and-off-for-begi-5805326)[HTTPS](http://lifehacker.com/https-everywhere-keeps-your-personal-information-safe-o-5889087)。当 HTTPS 开启时，ARP 欺骗不会捕捉到你正在做的任何事情。当您使用公共 Wi-Fi 并且无法控制网络安全时，这一点尤为重要。