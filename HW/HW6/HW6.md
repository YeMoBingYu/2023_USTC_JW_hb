# HW6
## PB21111686_赵卓
### T5
- $R的值是0100$

### T8
- $E(p)=Np(1-p)^{N-1}$
  $E'(p)=N(1-p)^{N-1}-Np(N-1)(1-p)^{N-2}$
  $=N(1-p)^{N-2}((1-p)-p(N-1))$
  $\therefore E'(p)=0\Rightarrow p_{max}=\frac{1}{N}$
- $E(p_{max})=N\frac{1}{N}(1-\frac{1}{N})^{N-1}=(1-\frac{1}{N})^{N-1}=\frac{(1-\frac{1}{N})^N}{1-\frac{1}{N}}$
  $\lim_{x\to\infty}(1-\frac{1}{N})=1$
  $\lim_{N\to\infty}(1-\frac{1}{N})^N=\frac{1}{e}$
  $\therefore \lim_{N\to\infty}E(p_{max})=\frac{1}{e}$

### T11
- $A在一个节点成功的概率p(A)=(1-p)^3p$
  $\therefore A在第五个节点首次成功的概率$
  $p=(1-p(A))^4p(A)=p(1-p)^3(1-(1-p)^3p)^4$
- $A节点在时隙4的成功概率为p(A)=(1-p)^3p$
  $B节点在时隙4的成功概率为p(B)=(1-p)^3p$
  $C节点在时隙4的成功概率为p(C)=(1-p)^3p$
  $D节点在时隙4的成功概率为p(D)=(1-p)^3p$
  $因此某个节点在时隙4成功概率p_{A,B,C,D}=$
  $p(A)+p(B)+p(C)+p(D)=4p(1-p)^3$
- $每个时隙出现成功的概率p_{succeed}=p_{A,B,C,D}$
  $因此在时隙3中出现首个成功的概率p_{first-succeed-3}=(1-p_{succeed})^2p_{succeed}$
  $=4p(1-4(1-p)^3p)^2(1-p)^3$
- $效率E=p_{succeed}=4p(1-p)^3$

### T23
- $总共9+2=11个结点以100Mps发送数据，因此最大总聚合吞吐量MAX=11*100Mps=1100Mps$

### T24
- $每个集线器的速率为100Mps,位于一个碰撞域中$
  $因此最大聚合吞吐量为三个集线器和两台服务器的总和$
  $即最大聚合吞吐量MAX=3*100Mps+2*100Mps=500Mps$

### T25
- $由于将所有交换器都换成集线器，因此只有一个碰撞域，即最大聚合吞吐量MAX=100Mps$

### T26
- 结果如下：
<table>
<tr align="center"><th>行为</th><th>交换机状态</th><th>链路包去向</th><th>说明</th></tr>
<tr align="center"><td>B向E发送一个帧</td><td>交换机获取与B的MAC地址对应的接口</td><td>A,C,D,E,F</td><td>由于交换机表为空，所以交换机不知道E的MAC地址对应的接口</td></tr>
<tr align="center"><td>E向B回答一个帧</td><td>交换机获取与E的MAC地址对应的接口</td><td>B</td><td>交换机已经知道了与B的MAC地址对应的接口</td></tr>
<tr align="center"><td>A向B发送一个帧</td><td>交换机获取与A的MAC地址对应的接口</td><td>B</td><td>交换机已经知道了与B的MAC地址对应的接口</td></tr>
<tr align="center"><td>B向A回答一个帧</td><td>交换机状态保持不变</td><td>A</td><td>交换机已经知道了与A的MAC地址对应的接口</td></tr>
</table>