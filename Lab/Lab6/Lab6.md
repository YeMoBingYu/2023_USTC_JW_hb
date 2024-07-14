# Lab_06_Ethernet_ARP
## PB21111686_赵卓
### T1. What is the 48-bit Ethernet address of your computer?
- $如图所示，我的计算机的48 bit 以太网地址为86:9d:fc:b0:83:f7$
![](1.jpg)
<br>

### T2. What is the 48-bit destination address in the Ethernet frame? Is this the Ethernet address of gaia.cs.umass.edu? (Hint: the answer is no). What device has this as its Ethernet address? [Note: this is an important question, and one that students sometimes get wrong. Re-read pages 468-469 in the text and make sure you understand the answer here.]
- $如图所示，48bit的目的地址为00:50:56:9f:00:7f，这不是gaia.cs.umass.edu的以太网地址，这是下一跳路由器的以太网地址。$
![](2.jpg)
<br>

### T3. Give the hexadecimal value for the two-byte Frame type field. What upper layer protocol does this correspond to?
- $如图所示，十六进制值为0x0800，它关联的上层协议是IPv4。$
![](3.jpg)
<br>

### T4. How many bytes from the very start of the Ethernet frame does the ASCII “G” in “GET” appear in the Ethernet frame?
- $如图所示，在'G'前面有0x0030+0x0006=0x0036=54个字节，'G'是第55个字节。$
![](4.jpg)
<br>

### T5. What is the value of the Ethernet source address? Is this the address of your computer, or of gaia.cs.umass.edu (Hint: the answer is no). What device has this as its Ethernet address?
- $如图所示，以太网源地址为ac:74:09:35:8a:e2，这不是我的电脑或者gaia.cs.umass.edu的以太网地址，这是从gaia.cs.umass.edu到我的电脑的最后一跳路由器的端口地址。$
![](5.jpg)
<br>

### T6. What is the destination address in the Ethernet frame? Is this the Ethernet address of your computer?
- $如上题所示，目的地址是86:9d:fc:b0:83:f7，这是我的电脑的以太网地址。$
<br>

### T7. Give the hexadecimal value for the two-byte Frame type field. What upper layer protocol does this correspond to?
- $如第五题图所示，十六进制值为0x0800，它关联的上层协议是IPv4。$
<br>

### T8. How many bytes from the very start of the Ethernet frame does the ASCII “O” in “OK” (i.e., the HTTP response code) appear in the Ethernet frame?
- $如图所示，在'O'前面有0x0040+0x0003=0x0043=67个字节，'O'是第68个字节。$
![](8.jpg)
<br>

### T9. Write down the contents of your computer’s ARP cache. What is the meaning of each column value?
- $如图所示，三列的值分别表示IP地址，物理地址与类型。类型分为动态和静态，动态类型在生存时间后会失效。$
![](9.jpg)
<br>

### T10. What are the hexadecimal values for the source and destination addresses in the Ethernet frame containing the ARP request message?
- $如图所示，源地址为86:9d:fc:b0:83:f7，目的地址为ff:ff:ff:ff:ff:ff(广播)。$
![](10.jpg)
<br>

### T11. Give the hexadecimal value for the two-byte Ethernet Frame type field. What upper layer protocol does this correspond to?
- $如上一题图所示，十六进制值为0x0806，对应的上层协议为ARP。$
<br>

### T12. Download the ARP specification fromftp://ftp.rfc-editor.org/in-notes/std/std37.txt. A readable, detailed discussion of ARP is also at http://www.erg.abdn.ac.uk/users/gorry/course/inet-pages/arp.html.
- #### How many bytes from the very beginning of the Ethernet frame does the ARP opcode field begin?
   - $如图所示，在opcode域前面有20个字节$
     ![](11.1.jpg)
<br>

- #### What is the value of the opcode field within the ARP-payload part of the Ethernet frame in which an ARP request is made?
   - $如上题图所示，opcode的值为1。$
<br>

- #### Does the ARP message contain the IP address of the sender?
  - $如图所示，ARP message中包含发送者的ip地址。$
  ![](11.3.jpg)
<br>

- ####  Where in the ARP request does the “question” appear – the Ethernet address of the machine whose corresponding IP address is being queried?
    - $如图所示，opcode表明了这是一个查询请求，目标机器的ip地址包含在Target IP address域$
    ![](11.4.jpg)
<br>

### T13. Now find the ARP reply that was sent in response to the ARP request.
- 如图所示
  ![](12.jpg)
<br>

- #### How many bytes from the very beginning of the Ethernet frame does the ARP opcode field begin?
  - $如图所示，在opcode域前面有20个字节。$
<br>

- #### What is the value of the opcode field within the ARP-payload part of the Ethernet frame in which an ARP response is made?
  - $如图所示，opcode的值为2。$
<br>

- #### Where in the ARP message does the “answer” to the earlier ARP request appear – the IP address of the machine having the Ethernet address whose corresponding IP address is being queried?
   - $如图所示，在Sender MAC address 和 Sender IP address中含有需要查询的ip地址和其相关的mac地址。$
<br>

### T14. What are the hexadecimal values for the source and destination addresses in the Ethernet frame containing the ARP reply message?
- $如上一题图所示，源地址为00:50:56:9f:00:7f，目的地址为86:9d:fc:b0:83:f7。$
<br>

### T15. Open the ethernet-ethereal-trace-1 trace file in http://gaia.cs.umass.edu/wireshark-labs/wireshark-traces.zip. The first and second ARP packets in this trace correspond to an ARP request sent by the computer running Wireshark, and the ARP reply sent to the computer running Wireshark by the computer with the ARP-requested Ethernet address. But there is yet another computer on this network, as indicated by packet 6 – another ARP request. Why is there no ARP reply (sent in response to the ARP request in packet 6) in the packet trace?
- $因为回复只能被另一台计算机接受（即发送该广播的计算机），因此在packet trace记录中没有ARP reply。$
<br>

### EX-1. The arp command:arp -s InetAddr EtherAddr allows you to manually add an entry to the ARP cache that resolves the IP address InetAddr to the physical address EtherAddr. What would happen if, when you manually added an entry, you entered the correct IP address, but the wrong Ethernet address for that remote interface?
- $使用arp -s InetAddr EtherAddr指令会添加一个静态表项。发往该ip地址的以太帧将会包含错误的目的以太地址，从而无法被目标机器正确接收。$
<br>

### EX-2. What is the default amount of time that an entry remains in your ARP cache before being removed. You can determine this empirically (by monitoring the cache contents) or by looking this up in your operation system documentation. Indicate how/where you determined this value.
- $在https://learn.microsoft.com/zh-cn/troubleshoot/windows-server/networking/address-resolution-protocol-arp-caching-behavior查到ARP cache的生存时间默认是在15s到45s间选取一个随机值。$
- $在电脑上查询结果如下：$
![](ex-2.jpg)