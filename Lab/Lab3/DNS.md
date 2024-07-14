# Lab_03_DNS
## PB21111686_赵卓
### Part 1
#### T1. Run *nslookup* to obtain the IP address of a Web server in Asia. What is the IP address of that server?

- 如图所示，Web server www.baidu.com 的IP地址为182.61.200.7和182.61.200.6
![](1.1.jpg)

#### T2. Run nslookup to determine the authoritative DNS servers for a university in Europe.
- 国内无法查询欧洲的大学，以清华大学为例，结果如下
![](1.2.jpg)

#### T3. Run nslookup so that one of the DNS servers obtained in Question 2 is queried for the mail servers for Yahoo! mail. What is its IP address?
- 在第二题中获得的两个服务器无法查询雅虎的邮件服务器，故换用科大服务器ns.ustc.edu.cn，结果如下：
大学，以清华大学为例，结果如下
![](1.3.jpg)

### Part 2
#### T4. Locate the DNS query and response messages. Are then sent over UDP or TCP?
- 如图所示，使用UDP协议
![](2.4.jpg)

#### T5. What is the destination port for the DNS query message? What is the source port of DNS response message?
- 如图所示，DNS query message的目标端口是53
![](2.5.1.jpg)
- 如图所示，DNS response message的源端口是53
![](2.5.2.jpg)

#### T6. To what IP address is the DNS query message sent? Use ipconfig to determine the IP address of your local DNS server. Are these two IP addresses the same?
- 如图所示，DNS query message发送的目标IP地址为202.141.180.1，这与ipconfig中查询到的本地DNS服务器相同
![](2.6.1.jpg)
![](2.6.2.jpg)

#### T7. Examine the DNS query message. What “Type” of DNS query is it? Does the query message contain any “answers”?
- 如图所示，DNS query的类型为A和AAAA，分别请求主机的ipv4和ipv6地址
![](2.7.1.jpg)
- query message不包含任何answer
![](2.7.2.jpg)

#### T8. Examine the DNS response message. How many “answers” are provided? What do each of these answers contain?
- 类型为A的request 收到的response包含两条answer，包含两条类型为A的dns记录，其中记录了请求的主机名对应的规范主机名和主机名对应的两条ip地址(ipv4)
![](2.8.1.jpg)
- 类型为AAAA的request 收到的response包含两条answer，两条类型为AAAA的dns记录，其中记录了请求的主机名对应的规范主机名和主机名对应的两条ip地址(ipv6)
![](2.8.2.jpg)

#### T9. Consider the subsequent TCP SYN packet sent by your host. Does the destination IP address of the SYN packet correspond to any of the IP addresses provided in the DNS response message?
- 如图所示，在后续我的主机发送的TCP SYN packet中含有目的IP地址与DNS response message中提供IP相同的package
![](2.9.jpg)

#### T10. This web page contains images. Before retrieving each image, does your host issue new DNS queries?
- 不会发送新的DNS query

### Part 3
#### T11. What is the destination port for the DNS query message? What is the source port of DNS response message?
- 如图所示，DNS query message的destination port与DNS response message的source port均为53
![](2.11.1.jpg)
![](2.11.2.jpg)

#### T12. To what IP address is the DNS query message sent? Is this the IP address of your default local DNS server?
- 如图所示，DNS query message发送的目标IP地址为202.141.180.1，这与默认本地DNS服务器相同
![](2.12.1.jpg)
![](2.12.2.jpg)

#### T13. Examine the DNS query message. What “Type” of DNS query is it? Does the query message contain any “answers”?
- DNS query message的类型分别为A和AAAA，分别查询目标主机的ipv4和ipv6地址，query message不包含任何answer
![](2.13.1.jpg)
![](2.13.2.jpg)
![](2.13.3.jpg)

#### T14. Examine the DNS response message. How many “answers” are provided? What do each of these answers contain?
- 类型为A的requset 收到的response包含三条answer，包含两条类型为CNAME的dns记录和一条类型为A的dns记录，其中记录了请求的主机名对应的两个规范主机名和主机名对应的ip地址(ipv4)
![](2.14.1.jpg)
- 类型为AAAA的requset 收到的response包含四条 answer，包含两条类型为CNAME的dns记录和两条类型为AAAA的dns记录，其中记录了请求的主机名对应的两个规范主机名和主机名对应的两个ip地址(ipv6)
![](2.14.2.jpg)

#### T15. Provide a screenshot.
- 如图所示
![](2.15.jpg)

### Part 4

#### T16. To what IP address is the DNS query message sent? Is this the IP address of your default local DNS server?
- 如图所示，DNS query message发送的目标IP地址为202.141.180.1，这与默认本地DNS服务器相同
![](2.16.1.jpg)
![](2.16.2.jpg)

#### T17. Examine the DNS query message. What “Type” of DNS query is it? Does the query message contain any “answers”?
- DNS query message的类型为NS，query message不包含任何answer
![](2.17.jpg)

#### T18. Examine the DNS response message. What MIT nameservers does the response message provide? Does this response message also provide the IP addresses of the MIT namesers?
- 在response message中得到了八个nameserver，同时提供了它们的IP地址
![](2.18.1.png)
![](2.18.2.png)

#### T19. Provide a screenshot.
- 如图所示
![](2.19.jpg)

### Part 5
#### 由于题给服务器连接超时，换用国内电信联通服务器
#### T20. To what IP address is the DNS query message sent? Is this the IP address of your default local DNS server? If not, what does the IP address correspond to?
- 如图所示，DNS query message发送的目标IP地址为114.114.114.114，这与默认本地DNS服务器不同，这是指定的服务器的地址
![](2.20.jpg)
#### T21. Examine the DNS query message. What “Type” of DNS query is it? Does the query message contain any “answers”?
- DNS query message的类型为A，query message不包含任何answer
![](2.21.1.jpg)
#### T22. Examine the DNS response message. How many “answers” are provided? What does each of these answers contain?
- 收到的response包含一条answer，为A类型，是主机www.aiit.or.kr对应的ip地址
![](2.22.1.jpg)
#### T23. Provide a screenshot.
- 如图所示
![](2.23.jpg)

