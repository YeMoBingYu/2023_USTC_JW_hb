# HW7
## PB21111686
### R7
- $因为AP传输信标帧。$
  $AP的信标帧将通过11个通道中的一个进行传输。信标帧允许附近的无线站发现和识别AP。$

### R11
- $最初，交换机在其转发表中有一个条目，该条目将无线站与较早的AP相关联。$
  $当无线站与新AP相关联时，新AP创建具有无线电台MAC地址的帧并广播该帧。$
  $该帧由交换机接收。这迫使交换机更新其转发表，以便通过新的AP发送发送到无线站的帧。$

### P5
- $a.$
  $两个AP通常具有不同的SSID和MAC地址。无线到达CAFTA的站将与其中一个SSID（即，其中一个AP）相关联。$
  $在关联之后，在新站点和AP之间存在虚拟链路。标记AP1和AP2。假设新站点与AP1相关联。$
  $当新的站发送帧，它将被寻址到AP1。$
  $尽管AP2还将接收帧，因为帧未被寻址，所以它将不处理帧。因此，两个ISP可以在同一信道上并行工作。$
  $然而,这两个ISP将共享相同的无线带宽。如果不同的无线站不同ISP同时发送，会发生冲突。$
  $对于802.11b，最大值两个ISP的聚合传输速率为11Mbps。$
- $b.$
  $现在，如果不同ISP（以及因此不同的信道）中的两个无线站发送同时，不会发生碰撞。$
  $因此，对于802.11b，两个ISP的传输速率为22Mbps。$

### P6
- $假设无线站h1有1000个长帧要发送。(h1可能是将MP3转发到其他无线电台的AP。)$
  $假设最初h1是唯一想要传输的站，但是在传输其第一个帧的中途，h2想发送一个帧。$
  $为了简单起见，也假设每个站都能听到其他站的信号(也就是说，没有隐藏的终端)。$
  $在传输之前，H2将感觉到信道是繁忙的，因此选择一个随机的退避值。$
  $现在假设在发送第一个帧之后，h1返回到步骤1；也就是说，它等待一个短时间(DIFS)，然后开始发送第二个帧。$
  $h1的第二帧将被传输，而h2被卡在退避中，等待空闲信道。因此，h1应该能够在h2有机会访问信道之前传输其所有1000帧。$
  $另一方面，如果h1在发送帧后进入步骤2，那么它也会选择一个随机的退避值，从而给h2一个公平的机会。$
  $因此，公平是这种设计选择的理由。$