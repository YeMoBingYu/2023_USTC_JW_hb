# Lab_04_TCP
## PB21111686_赵卓
### Part1
#### T1. What is the IP address and TCP port number used by the client computer (source) that is transferring the file to gaia.cs.umass.edu? To answer this question, it’s probably easiest to select an HTTP message and explore the details of the TCP packet used to carry this HTTP message, using the “details of the selected packet header window” (refer to Figure 2 in the “Getting Started with Wireshark” Lab if you’re uncertain about the Wireshark windows.
- 如图所示，在下载的tcp-ethereal-trace-1文件中找到带有HTTP信息的TCP包，可以看到client computer的ip地址为192.168.1.102，TCP端口为1161
  ![](1.jpg)


#### T2. What is the IP address of gaia.cs.umass.edu? On what port number is it sending and receiving TCP segments for this connection?
- 由第一题图可知，gaia.cs.umass.edu 的ip地址为128.119.245.12；在此次连接中收发TCP段的端口为80。

#### T3. What is the IP address and TCP port number used by your client computer (source) to transfer the file to gaia.cs.umass.edu?
- 如图所示，从自己抓包结果可知，client computer的ip地址为192.168.156.38，tcp端口号为59017。
  ![](3.jpg)

### Part2
#### T4. What is the sequence number of the TCP SYN segment that is used to initiate the TCP connection between the client computer and gaia.cs.umass.edu? What is it in the segment that identifies the segment as a SYN segment?
- 如图所示，TCP SYN的序列号是0；在段中是flags含有的一个标志位标明这个段是SYN段。
    ![](4.jpg)

#### T5. What is the sequence number of the SYNACK segment sent by gaia.cs.umass.edu to the client computer in reply to the SYN? What is the value of the Acknowledgement field in the SYNACK segment? How did gaia.cs.umass.edu determine that value? What is it in the segment that identifies the segment as a SYNACK segment?
- SYNACK的序列号是0；Acknowledgement filed的值为1；gaia.cs.umass.edu 根据上次收到的TCP segment的序列号加1得到；在段中是flags含有的两个标志位一起标明这个段是SYNACK段。
    ![](5.jpg)

#### T6. What is the sequence number of the TCP segment containing the HTTP POST command? Note that in order to find the POST command, you’ll need to dig into the packet content field at the bottom of the Wireshark window, looking for a segment with a “POST” within its DATA field.
- 如图，包含HTTP POST指令的TCP段的序列号为1。
    ![](6.jpg)

#### T7. Consider the TCP segment containing the HTTP POST as the first segment in the TCP connection. What are the sequence numbers of the first six segments in theTCP connection (including the segment containing the HTTP POST)? At what time was each segment sent? When was the ACK for each segment received? Given the difference between when each TCP segment was sent, and when its acknowledgement was received, what is the RTT value for each of the six segments? What is the EstimatedRTT value (see Section 3.5.3, page 242 in text) after the receipt of each ACK? Assume that the value of the EstimatedRTT is equal to the measured RTT for the first segment, and then is computed using the EstimatedRTT equation on page 242 for all subsequent segments.
- 6个TCP序号分别为：1，748，2208，3668，5128，6588。
  发送时间分别为：Oct 29, 2023 14:38:50.565397000，Oct 29, 2023 14:38:50.565462000，Oct 29, 2023 14:38:50.565462000，Oct 29, 2023 14:38:50.565462000，Oct 29, 2023 14:38:50.565462000，Oct 29, 2023 14:38:50.565462000。
  接收到ACK的时间分别为Oct 29, 2023 14:38:50.937485000，Oct 29, 2023 14:38:50.937485000，Oct 29, 2023 14:38:50.937485000，Oct 29, 2023 14:38:50.937485000，Oct 29, 2023 14:38:50.937485000，Oct 29, 2023 14:38:50.937485000。
  RTT值分别为0.372088，0.372023，0.372023，0.372023，0.372023，0.372023。
  根据后五次RTT值依次更新EstimatedRTT得到的值分别为0.372289，0.372152，0.372152，0.372152，0.372152，0.372152。
    ![](7.1.jpg)
    ![](7.2.jpg)
    ![](7.3.jpg)
#### T8. What is the length of each of the first six TCP segments?
- 由上一题的图中可以看到，长度分别为747，1460，1460，1460，1460，1460.

#### T9. What is the minimum amount of available buffer space advertised at the received for the entire trace? Does the lack of receiver buffer space ever throttle the sender?
- 可用缓存空间的最小值为29200；因此在整个捕获中缓存空间一直较大，没有限制发送方。
    ![](9.jpg)
#### T10. Are there any retransmitted segments in the trace file? What did you check for (in the trace) in order to answer this question?
- 没有发生重传；可以检查发送的tcp段的序列号是否重复可以验证是否重传。

#### T11. How much data does the receiver typically acknowledge in an ACK? Can you identify cases where the receiver is ACKing every other received segment (see Table 3.2 on page 250 in the text).
- 在一个ACK中通常每次确认的数据量为1460；在确认量大于1460时，为表中第二种情况(延迟确认)，例如在56号TCP段和57号TCP段间ACK的差值为4380。
    ![](11.jpg)

#### T12. What is the throughput (bytes transferred per unit time) for the TCP connection? Explain how you calculated this value.
- 从图中可知发送的总字节数为153068，用总字节数除以发送用时（约0.613974s），即可得到吞吐量为249306bytes/。
    ![](12.jpg)

### Part3
#### T13. Use the Time-Sequence-Graph(Stevens) plotting tool to view the sequence number versus time plot of segments being sent from the client to the gaia.cs.umass.edu server. Can you identify where TCP’s slowstart phase begins and ends, and where congestion avoidance takes over? Comment on ways in which the measured data differs from the idealized behavior of TCP that we’ve studied in the text.
- 时间序列图如下：
![](13.1.jpg)
- TCP的慢启动阶段如下所示，在此之后就是拥塞控制接管：
![](13.2.jpg)
- 在测量数据中，慢启动阶段不是理想的指数增长。

#### T14. Answer each of two questions above for the trace that you have gathered when you transferred a file from your computer to gaia.cs.umass.edu.
- 时间序列图如下：
![](14.jpg)
- tcp的慢启动阶段大约在前0.5s，在此之后就是拥塞控制接管。
- 在测量数据中，慢启动阶段不是理想的指数增长。