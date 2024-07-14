# HW5
## PB21111686_赵卓
### T3
- Dijkstra算法表格如下
<table>
<tr align="center">
<th>Step</th>
<th>N'</th>
<th>D(t),p(t)</th>
<th>D(u),p(u)</th>
<th>D(v),p(v)</th>
<th>D(w),p(w)</th>
<th>D(y),p(y)</th>
<th>D(z),p(z)</th>
</tr>
<tr align="center">
<td>0</td>
<td>x</td>
<td>无穷</td>
<td>无穷</td>
<td>3,x</td>
<td>6,x</td>
<td>6,x</td>
<td>8,x</td>
</tr>
<tr align="center">
<td>1</td>
<td>xv</td>
<td>7,v</td>
<td>6.v</td>
<td>3,x</td>
<td>6,x</td>
<td>6,x</td>
<td>8,x</td>
</tr>
<tr align="center">
<td>2</td>
<td>xvu</td>
<td>7,v</td>
<td>6,v</td>
<td>3,x</td>
<td>6,x</td>
<td>6,x</td>
<td>8,x</td>
</tr>
<tr align="center">
<td>2</td>
<td>xvuw</td>
<td>7,v</td>
<td>6,v</td>
<td>3,x</td>
<td>6,x</td>
<td>6,x</td>
<td>8,x</td>
</tr>
<tr align="center">
<td>3</td>
<td>xvuwy</td>
<td>7,v</td>
<td>6,v</td>
<td>3,x</td>
<td>6,x</td>
<td>6,x</td>
<td>8,x</td>
</tr>
</tr>
<tr align="center">
<td>4</td>
<td>xvuwyt</td>
<td>7,v</td>
<td>6,v</td>
<td>3,x</td>
<td>6,x</td>
<td>6,x</td>
<td>8,x</td>
</tr>
</tr>
<tr align="center">
<td>5</td>
<td>xvuwytz</td>
<td>7,v</td>
<td>6,v</td>
<td>3,x</td>
<td>6,x</td>
<td>6,x</td>
<td>8,x</td>
</tr>
</table>

### T7
- a.Dx(w)=2,Dx(y)=4,Dx(u)=7。
- b. 
   - c(x,y)>=1时，c(x,y)无论变大变小，x到u的最小开销都是7，因此不会通知邻居有新变化；c(x,y)=a<1时，最小成本通过y并且变为a+6并通知邻居新变化。
   - c(x,w)=a>6时，最小成本路径通过y变为11并通知邻居；c(x,w)=a<1时，最小成本路径通过w变为a+5并通知邻居。
- c.链路成本c(x，y)(c(x，y)>=1)任何变化都不会导致x通知它的邻居有到x的一个新的最小成本路径。

### T8
- Table x
<table>
<tr align="center">
<th colspan="5">Cost</th>
</tr>
<tr align="center">
<th rowspan="4">From</th>
<td></td>
<td>x</td>
<td>y</td>
<td>z</td>
</tr>
<tr align="center">
<td>x</td>
<td>0</td>
<td>3</td>
<td>4</td>
</tr>
<tr align="center">
<td>y</td>
<td>无穷</td>
<td>无穷</td>
<td>无穷</td>
</tr>
<tr align="center">
<td>z</td>
<td>无穷</td>
<td>无穷</td>
<td>无穷</td>
</tr>
<tr align="center">
<th colspan="5">Cost</th>
</tr>
<tr align="center">
<th rowspan="4">From</th>
<td></td>
<td>x</td>
<td>y</td>
<td>z</td>
</tr>
<tr align="center">
<td>x</td>
<td>0</td>
<td>3</td>
<td>4</td>
</tr>
<tr align="center">
<td>y</td>
<td>3</td>
<td>0</td>
<td>6</td>
</tr>
<tr align="center">
<td>z</td>
<td>4</td>
<td>6</td>
<td>0</td>
</tr>
</table>
  
- Table y
<table>
<tr align="center">
<th colspan="5">Cost</th>
</tr>
<tr align="center">
<th rowspan="4">From</th>
<td></td>
<td>x</td>
<td>y</td>
<td>z</td>
</tr>
<tr align="center">
<td>x</td>
<td>无穷</td>
<td>无穷</td>
<td>无穷</td>
</tr>
<tr align="center">
<td>y</td>
<td>3</td>
<td>0</td>
<td>6</td>
</tr>
<tr align="center">
<td>z</td>
<td>无穷</td>
<td>无穷</td>
<td>无穷</td>
</tr>
<tr align="center">
<th colspan="5">Cost</th>
</tr>
<tr align="center">
<th rowspan="4">From</th>
<td></td>
<td>x</td>
<td>y</td>
<td>z</td>
</tr>
<tr align="center">
<td>x</td>
<td>0</td>
<td>3</td>
<td>4</td>
</tr>
<tr align="center">
<td>y</td>
<td>3</td>
<td>0</td>
<td>6</td>
</tr>
<tr align="center">
<td>z</td>
<td>4</td>
<td>6</td>
<td>0</td>
</tr>
</table>

- Table z
<table>
<tr align="center">
<th colspan="5">Cost</th>
</tr>
<tr align="center">
<th rowspan="4">From</th>
<td></td>
<td>x</td>
<td>y</td>
<td>z</td>
</tr>
<tr align="center">
<td>x</td>
<td>无穷</td>
<td>无穷</td>
<td>无穷</td>
</tr>
<tr align="center">
<td>y</td>
<td>无穷</td>
<td>无穷</td>
<td>无穷</td>
</tr>
<tr align="center">
<td>z</td>
<td>4</td>
<td>6</td>
<td>0</td>
</tr>
<tr align="center">
<th colspan="5">Cost</th>
</tr>
<tr align="center">
<th rowspan="4">From</th>
<td></td>
<td>x</td>
<td>y</td>
<td>z</td>
</tr>
<tr align="center">
<td>x</td>
<td>0</td>
<td>3</td>
<td>4</td>
</tr>
<tr align="center">
<td>y</td>
<td>3</td>
<td>0</td>
<td>6</td>
</tr>
<tr align="center">
<td>z</td>
<td>4</td>
<td>6</td>
<td>0</td>
</tr>
</table>


### T14
- a.eBGP
- b.iBGP
- c.eBGP
- d.iBGP
  
### T15
- a.$I_1$，因为这个接口开始了从1d路由器到1c路由器的最低路径开销。
- b.$I_2$，$I_1$和$I_2$都有相同的$AS-PATH$路径长度，但是$I_2$开始了到最近$NEXT-TOP$路由器的路径。
- c.$I_1$，因为$I_1$开始了最短$AS-PATH$长度的路径。