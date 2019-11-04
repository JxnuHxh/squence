# Computer-Network
#### 计算机网络学习的核心内容就是网络协议的学习，计算机网络协议同我们生活中的语言一样，多种多样。  

 　　为了使不同计算机厂家生产的计算机能够相互通信，以便在更大的范围内建立计 算机网络，<br>
 国际标准化组织（ISO）在1978年提出了“开放系统互联参考模型”，即OSI七层模型，<br>
 除了标准的OSI七层模型以外，常见的网络层次划分还有TCP/IP四层协议 和  TCP/IP五层协议。<br>
 它们之间的对应关系如下图所示：<br><br>
<img src="image/层.jpg"><br>

## OSI七层模型
![封装过程](image/封装过程.png)
 TCP/IP协议是互联网的基础协议,每一层中都要自己的专属协议，完成自己相应的工作以及与上下层级之间进行沟通。   
 简要来讲各层作用：  


物理层：通过媒介传输比特,确定机械及电气规范（比特Bit）  

数据链路层：将比特组装成帧和点到点的传递（帧Frame）  

网络层：负责数据包从源到宿的传递和网际互连（包PackeT）  

传输层：提供端到端的可靠报文传递和错误恢复（段Segment）  

会话层：建立、管理和终止会话（会话协议数据单元SPDU）  

表示层：对数据进行翻译、加密和压缩（表示协议数据单元PPDU）  

应用层：允许访问OSI环境的手段（应用协议数据单元APDU）  


#### 1.物理层（Physical Layer）<br>
　　激活、维持、关闭通信端点之间的机械特性、电气特性、功能特性以及过程特性。<br>
该层为上层协议提供了一个传输数据的可靠的物理媒体。简单的说，物理层确保<br>
原始的数据可在各种物理媒体上传输。物理层记住两个重要的设备名称，<br>
中继器（Repeater，也叫放大器）和集线器<br>
#### 2.数据链路层（Data Link Layer）<br>
　　将源自网络层来的数据可靠地传输到相邻节点的目标机网络层。为达到这一目的，<br>
数据链路必须具备一系列相应的功能，主要有：如何将数据组合成数据块，<br>
在数据链路层中称这种数据块为帧（frame），帧是数据链路层的传送单位；<br>
如何控制帧在物理信道上的传输，包括如何处理传输差错，如何调节发送速率以使与接收方相匹配；<br>
以及在两个网络实体之间提供数据链路通路的建立、维持和释放的管理。<br>
数据链路层在不可靠的物理介质上提供可靠的传输。<br>
该层的作用包括：物理地址寻址、数据的成帧、流量控制、数据的检错、重发等。<br>
有关数据链路层的重要知识点：<br>
　　1. 数据链路层为网络层提供可靠的数据传输；<br>

　　2. 基本数据单位为帧；<br>

　　3. 主要的协议：以太网协议；<br>

　　4. 两个重要设备名称：网桥和交换机。<br>
#### 3.网络层（Network Layer）<br>
　　网络层的目的是实现两个端系统之间的数据透明传送，具体功能包括寻址<br>
和路由选择、连接的建立、保持和终止等。它提供的服务使传输层不需<br>
要了解网络中的数据传输和交换技术。如果您想用尽量少的词来记住网络<br>
层，那就是“路径选择、路由及逻辑寻址”。<br>

　　网络层中涉及众多的协议，其中包括最重要的协议，也是TCP/IP的核心协议——IP协议。<br>
IP协议非常简单，仅仅提供不可靠、无连接的传送服务。<br>
IP协议的主要功能有：无连接数据报传输、数据报路由选择和差错控制。<br>
与IP协议配套使用实现其功能的还有地址解析协议ARP、逆地址解析协议RARP、<br>
因特网报文协议ICMP、因特网组管理协议IGMP。具体的协议我们会在接下来的部分进行总结。<br>
有关网络层的重点为：<br>

　1. 网络层负责对子网间的数据包进行路由选择。此外，网络层还可以实现拥塞控制、网际互连等功能；<br>

　2. 基本数据单位为IP数据报；<br>

　3. 包含的主要协议：<br>

　　IP协议（Internet Protocol，因特网互联协议）;<br>

　　ICMP协议（Internet Control Message Protocol，因特网控制报文协议）;<br>

　　ARP协议（Address Resolution Protocol，地址解析协议）;<br>

　　RARP协议（Reverse Address Resolution Protocol，逆地址解析协议）。<br>

　4. 重要的设备：路由器。<br><br>
#### 4.传输层（Transport Layer）<br>
　传输层的任务是根据通信子网的特性，最佳的利用网络资源，为两个端系<br>
统的会话层之间，提供建立、维护和取消传输连接的功能，负责端到端的<br>
可靠数据传输。在这一层，信息传送的协议数据单元称为段或报文。<br>
　　网络层只是根据网络地址将源结点发出的数据包传送到目的结点，而<br>
传输层则负责将数据可靠地传送到相应的端口。<br>
有关网络层的重点：<br>
　1. 传输层负责将上层数据分段并提供端到端的、可靠的或不可靠的传<br>
输以及端到端的差错控制和流量控制问题；<br>
　2. 包含的主要协议：<br>
TCP协议（Transmission ControlProtocol，传输控制协议）<br>
UDP协议（User Datagram Protocol，用户数据报协议）<br>
　3. 重要设备：网关。<br>
#### 5.会话层  <br>
会话层管理主机之间的会话进程，即负责建立、管理、终止进程之间的会话。<br>
会话层还利用在数据中插入校验点来实现数据的同步。 <br> 
#### 6.表示层 <br>
表示层对上层数据或信息进行变换以保证一个主机应用层信息可以被另一个主机的应用程序理解。<br>
表示层的数据转换包括数据的加密、压缩、格式转换等。<br>
#### 7.应用层<br>
是最靠近用户的OSI层，为用户的应用程序提供网络服务的接口。将用户的操作通过应用程序转换成为服务，<br>
并匹配一个相应的服务协议发送给传输层。<br>
会话层、表示层和应用层重点：<br>

1. 数据传输基本单位为报文；<br>
2. 包含的主要协议：FTP（文件传送协议）、Telnet（远程登录协议）<br>
DNS（域名解析协议）、SMTP（邮件传送协议），POP3协议（邮局协议）<br>
HTTP协议（Hyper Text Transfer Protocol）。   

## IP地址分类    
    IP地址是32位的二进制数值，用于在TCP/IP通讯协议中标记每台计算机的地址。    
通常我们使用点式十进制来表示，如192.168.0.5等等。   
 
　　每个IP地址又可分为两部分。即网络号部分和主机号部分：网络号表示其所属的网络段编号，   
主机号则表示该网段中该主机的地址编号。按照网络规模的大小，IP地址可以分为A、B、C、D、E五类。   

A类地址：以0开头，      第一个字节范围：0~127（1.0.0.0 - 126.255.255.255）；  

B类地址：以10开头，    第一个字节范围：128~191（128.0.0.0 - 191.255.255.255）；  

C类地址：以110开头，  第一个字节范围：192~223（192.0.0.0 - 223.255.255.255）；  

 
|类别|       网络号                          |占位数| 主机号                |占位数| 用途   |  

   
|A  |（以0开头） 1～126                      | 8    |0～255 .0～255 .1～254 | 24  |国家级   |  

|B  |（以10开头） 128～191 .0～255           | 16   |0～255 .1～254         |16   |跨国组织 |  
 
|C  |（以110开头）192～223 . 0～255. 0～255 .| 24   |1～254                 | 8   |企业组织 |  


注意：

1）以下是留用的内部私有地址，Internet上没使用的地址  

A类 10.0.0.0--10.255.255.255  

B类 172.16.0.0--172.31.255.255  

C类 192.168.0.0--192.168.255.255  

2）IP地址与子网掩码相与得到网络号  

3）主机号，全为0的是网络号（例如：192.168.2.0），主机号全为1的为广播地址（192.168.2.255）   

## ARP地址解析协议的原理  
地址解析协议，即ARP（Address Resolution Protocol），是根据IP地址获取物理地址的一个TCP/IP协议。   

1：首先，每个主机都会在自己的ARP缓冲区中建立一个ARP列表，以表示IP地址和MAC地址之间的对应关系。  

2：当源主机要发送数据时，首先检查ARP列表中是否有对应IP地址的目的主机的MAC地址，如果有，  
则直接发送数据，如果没有，就向本网段的所有主机发送ARP数据包，  
该数据包包括的内容有：源主机 IP地址，源主机MAC地址，目的主机的IP 地址  

3：当本网络的所有主机收到该ARP数据包时，首先检查数据包中的IP地址是否是自己的IP地址，  
如果不是，则忽略该数据包，如果是，则首先从数据包中取出源主机的IP和MAC地址写入到ARP列表中  
，如果已经存在，则覆盖，然后将自己的MAC地址写入ARP响应包中，告诉源主机自己是它想要找的MAC地址。  

4：源主机收到ARP响应包后。将目的主机的IP和MAC地址写入ARP列表，并利用此信息发送数据。  
如果源主机一直没有收到ARP响应数据包，表示ARP查询失败。  
  广播（255.255.255.255）发送ARP请求，单播发送ARP响应
## 在浏览器中输入www.baidu.com后执行的全部过程     

1、客户端浏览器通过DNS解析到www.baidu.com的IP地址220.181.27.48  ，通过这个IP地址找到客户端到服务器的路径。客户端浏览器发起一个HTTP会话到220.161.27.48  
然后通过TCP进行封装数据包，输入到网络层。  

2、在客户端的传输层(添加TCP头)，把HTTP会话请求分成报文段，添加源和目的端口，  
如服务器使用80端口监听客户端的请求，客户端由系统随机选择一个端口如5000，  
与服务器进行交换，服务器把相应的请求返回给客户端的5000端口。然后使用IP层的IP地址查找目的端。  
 
 3、客户端的网络层（添加IP头）不用关系应用层或者传输层的东西，主要做的是通过查找路由表确定如何到达服务器，   
 期间可能经过多个路由器，这些都是由路由器来完成的工作，我不作过多的描述，无非就是通过查找路由表决定通过那个路径到达服务器。  

 4、客户端的链路层（添加MAC头），包通过链路层发送到路由器，通过邻居协议查找给定IP地址的MAC地址，  
 然后发送ARP请求查找目的地址，如果得到回应后就可以使用ARP的请求应答交换的IP数据包现在就可以传输了，  
 然后发送IP数据包到达服务器的地址。  
## TCP和UDP的区别   

这是传输层的两个协议，先说一下传输层的两大功能：  

    复用：在发送端，多个应用进程公用一个传输层；  
    分用：在接收端，传输层会根据端口号将数据分给不同的应用进程。   

传输层和网络层的区别：  

    网络层为不同的主机提供通信服务，传输层为不同应用进程提供通信服务。  
    网络层只对报文头部进行差错检测，而传输层对整个报文进行差错检测。  

UDP（User Data Protocol）用户数据报协议  

    无连接  
    不可靠（不能保证都送达）  
    面向报文（UDP数据传输单位是报文，不会对数据进行拆分和拼接操作，只是给上层传来的数据加个UDP头或者给下层来的数据去掉UDP头）  
    没有拥塞控制，始终以恒定速率发送数据  
    支持一对一、一对多、多对多、多对一  
    首部开销小，只有8字节  

TCP（Transmission Control Protocol）传输控制协议  

    有连接  
    可靠的  
    面向字节流  
    全双工通信，TCP两端既可以作为发送端也可以作为接收端  
    连接的两端只能是两个端点，即一对一，不能一对多  
    至少20个字节，比UDP大的多  

什么是TCP连接  

TCP连接是一种抽象的概念，表示一条可以通信的链路。  
每个TCP连接有且仅有两个端点，表示通信的双方，且双方在任意时刻都可以作为发送者和接受者。  

什么是套接字  

一条TCP连接的两端就是两个套接字。  
套接字 = IP地址 ：端口号  
因此，TCP连接 = （套接字1，套接字2）= （IP1：端口号1，IP2：端口号2）  
[计算机网络基础知识](https://www.cnblogs.com/maybe2030/p/4781555.html#_label3)