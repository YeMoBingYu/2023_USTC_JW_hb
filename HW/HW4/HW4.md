# HW4
## PB21111686_赵卓
### T5
- a.转发表如下：
<table>
<tr align="center">
<th>Prefix Match</th>
<th>Link Interface</th>
</tr>
<tr align="center">
<td>11100000 00</td>
<td>0</td>
</tr>
<tr align="center">
<td>11100000 01000000</td>
<td>1</td>
</tr>
<tr align="center">
<td>1110000</td>
<td>2</td>
</tr>
<tr align="center">
<td>11100001 1</td>
<td>3</td>
</tr>
<tr align="center">
<td>otherwise</td>
<td>3</td>
</tr>
</table>

- b.
   - 最长前缀匹配第五个入口，因此使用3号链路接口。
   - 最长前缀匹配第三个入口，因此使用2号链路接口。
   - 最长前缀匹配第四个入口，因此使用3号链路接口。

### T7.
- 范围表如下：
<table>
<tr align="center">
<th>Destination Address Range</th>
<th>Link Interface</th>
</tr>
<tr align="center">
<td>11000000 
 through (32 addresses) 11011111</td>
<td>0</td>
</tr>
<tr align="center">
<td>10000000 
 through (64 addresses) 10111111</td>
<td>1</td>
</tr>
<tr align="center">
<td>11100000 
 through (32 addresses) 11111111 </td>
<td>2</td>
</tr>
<tr align="center">
<td>00000000 
through (128 addresses)                                                  01111111</td>
<td>3</td>
</tr>
</table>

### T8.
- 223.1.17.0/26 
- 223.1.17.128/25 
- 223.1.17.192/28

### T10.
- 转发表如下：
<table>
<tr align="center">
<th>Destination Address</th>
<th>Link Interface</th>
<tr align="center">
<td>11100000 00 (224.0/10)</td>
<td>0</td>
</tr>
<tr align="center">
<td>11100000 01000000 (224.64/16)</td>
<td>1</td>
</tr>
<tr align="center">
<td>1110000 (224/8)</td>
<td>2</td>
</tr>
<tr align="center">
<td>11100001 1 (225.128/9)</td>
<td>3</td>
</tr>
</tr>
<tr align="center">
<td>otherwise</td>
<td>3</td>
</tr>
</table>

### T12.
- a.
   - Subnet A: 214.97.255/24 (256 addresses) 
   - Subnet B: 214.97.254.0/25 - 214.97.254.0/29 (128-8 = 120 addresses) 
   - Subnet C: 214.97.254.128/25 (128 addresses)
   - Subnet D: 214.97.254.0/31 (2 addresses) 
   - Subnet E: 214.97.254.2/31 (2 addresses) 
   - Subnet F: 214.97.254.4/30 (4 addresses)
- b.
   - Router 1
   <table>
<tr align="center">
<th>Longest Prefix Match</th>
<th>Outgoing Interface</th>
</tr>
<tr align="center">
<td>11010110 01100001 11111111</td>
<td>Subnet A</td>
</tr>
<tr align="center">
<td>11010110 01100001 11111110 0000000</td>
<td>Subnet D</td>
</tr>
<tr align="center">
<td>11010110 01100001 11111110 000001</td>
<td>Subnet F</td>
</tr>
</table>

- Router 2
<table>
<tr align="center">
<th>Longest Prefix Match</th>
<th>Outgoing Interface</th>
</tr>
<tr align="center">
<td>11010110 01100001 11111111 0000000</td>
<td>Subnet D</td>
</tr>
<tr align="center">
<td>11010110 01100001 11111110 0</td>
<td>Subnet B</td>
</tr>
<tr align="center">
<td>11010110 01100001 11111110 0000001</td>
<td>Subnet E</td>
</tr>
</table>

- Router 3
<table>
<tr align="center">
<th>Longest Prefix Match</th>
<th>Outgoing Interface</th>
</tr>
<tr align="center">
<td>11010110 01100001 11111111 000001</td>
<td>Subnet F</td>
</tr>
<tr align="center">
<td>11010110 01100001 11111110 0000001</td>
<td>Subnet E</td>
</tr>
<tr align="center">
<td>11010110 01100001 11111110 1</td>
<td>Subnet C</td>
</tr>
</table>

### T14.
- $num=\frac{2400-20}{680}=4$
- 0，85，170，255。

         