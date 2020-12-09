# QUESTION:

Use shadowsocks  based on LNTU's Campus Network (It uses a SRUN's network)

### 1 There is a problem with wifi self-certification that cannot be recognized

>  When you turn on your computer, you won't automatically connect to WiFi, and you won't after !

### 2 Whether or not in pac mode, domestic websites are still slow to open, or even unable to open

> example [Bilibili](www.bilibili.com) ，[Tencent Video](https://v.qq.com)  ,[Ali Cloud](https://cn.aliyun.com/) etc.

# Explore the solution

### 1 Turn off the shadowsocks & Test

> The opening or not of shadowsocks does not affect speed  
>
> **it is still slowly !**

### 2 Cancel the agent in the ie settings To test whether a system agent is used

> **It doesn't work**

### 3 Test IP & DNS to resolve Net path judgment

> ###  Determines whether the current ip is a local ip(Use the command line)
>
> ``` ipconfig``` Determines whether the current ip is a local ip.
>
> ###  Consider the role of automatic DNS 
>
> ```ipconfig /all``` get DNS
>
> Here are two 
>
>  >211.137.32.178(Maybe yours is different)  
>  >1.1.1.1
>
> Replace the DNS server and find no problems for the common **114.114.114.114**

> We know that common DNS can be resolved, but getting DNS servers automatically can cause problems. So we can manually add the available DNS servers, and ensure that the correct connection to the major domestic websites

Tip : U will want to know [1.1.1.1](https://zh.wikipedia.org/wiki/1.1.1.1)

