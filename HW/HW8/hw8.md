# HW8
## PB21111686_赵卓
### 8
- $(a).$
  $n=p*q=55$
  $z=(p-1)*(q-1)=40$
- $(b).$
  $e=3时，e比n小并且和z没有相同的因子$
- $(c).$
  $d=27时，de=1(mod\ \ z)，且d=27满足d\le 160$
- $(d).$
  $m=8，me=512$
  $则c=me\ \ mod\ \ n=17$

### 12
- $如图：$
  ```mermaid
  graph LR;
  A[m] --> B[+]
  K((S1)) --> C
  A --> C[H（.）] --> B
  B --(m,h)--> D[encription 
                  algotithm] --K_S2(m,h)--> E{Internet}
  L((S2)) --> D
  E --K_S2(m,h)--> F[Decription
                     algorithm]--(m,h)--> G>Compare]
  M((S2)) -->F
  F --m--> H[H（.）] --> G
  N((S1)) --> H
  ```



### 18
- $(a).$
  $不具有公钥/私钥对或预共享秘密，所以Bob无法验证Alice创建了消息。$

- $(b).$
  $是的，Alice简单地使用Bob的公钥对消息进行加密，并发送对Bob的加密消息。$