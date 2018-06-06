# TCP UDP 的[最完整的区别](https://blog.csdn.net/Li_Ning_/article/details/52117463)

## TCP与UDP基本区别

  1.基于连接与无连接
  2.TCP要求系统资源较多，UDP较少； 
  3.UDP程序结构较简单 
  4.流模式（TCP）与数据报模式(UDP); 
  5.TCP保证数据正确性，UDP可能丢包 
  6.TCP保证数据顺序，UDP不保证 
　　
## UDP应用场景：

  1.面向数据报方式
  2.网络数据大多为短消息 
  3.拥有大量Client
  4.对数据安全性无特殊要求
  5.网络负担非常重，但对响应速度要求高

## 具体编程时的区别

   1.socket()的参数不同
　　 2.UDP Server不需要调用listen和accept
　　 3.UDP收发数据用sendto/recvfrom函数
　　 4.TCP：地址信息在connect/accept时确定
　　 5.UDP：在sendto/recvfrom函数中每次均 需指定地址信息
　　 6.UDP：shutdown函数无效
