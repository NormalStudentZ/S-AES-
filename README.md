# S-AES算法实现
重庆大学大数据与软件学院信息安全导论作业2：S-AES算法的实现，在胡海波老师的指导下，由刘天任和刘泽源使用JAVA语言共同完成。
## 编程和测试要求
### 3.1 第1关：基本测试       
根据S-AES算法编写和调试程序，提供GUI解密支持用户交互。输入可以是16bit的数据和16bit的密钥，输出是16bit的密文。
### 3.2 第2关：交叉测试
考虑到是"算法标准"，所有人在编写程序的时候需要使用相同算法流程和转换单元(替换盒、列混淆矩阵等)，以保证算法和程序在异构的系统或平台上都可以正常运行。设有A和B两组位同学(选择相同的密钥K)；则A、B组同学编写的程序对明文P进行加密得到相同的密文C；或者B组同学接收到A组程序加密的密文C，使用B组程序进行解密可得到与A相同的P。
### 3.3 第3关：扩展功能
考虑到向实用性扩展，加密算法的数据输入可以是ASII编码字符串(分组为2 Bytes)，对应地输出也可以是ACII字符串(很可能是乱码)。
### 3.4 第4关：多重加密
#### 3.4.1 双重加密
将S-AES算法通过双重加密进行扩展，分组长度仍然是16 bits，但密钥长度为32 bits。
#### 3.4.2 中间相遇
攻击假设你找到了使用相同密钥的明、密文对(一个或多个)，请尝试使用中间相遇攻击的方法找到正确的密钥Key(K1+K2)。
#### 3.4.3 三重加密
将S-AES算法通过三重加密进行扩展，下面两种模式选择一种完成：
(1)按照32 bits密钥Key(K1+K2)的模式进行三重加密解密，
(2)使用48bits(K1+K2+K3)的模式进行三重加解密。
### 3.5 第5关：工作模式
基于S-AES算法，使用密码分组链(CBC)模式对较长的明文消息进行加密。注意初始向量(16 bits) 的生成，并需要加解密双方共享。在CBC模式下进行加密，并尝试对密文分组进行替换或修改，然后进行解密，请对比篡改密文前后的解密结果。
## 闯关过程
### 3.1 第1关：基本测试       
测试案例：使用密钥1001101010001110对明文1101001010110100进行加密，并通过逆向操作验证解密是否成功。
![image](https://github.com/user-attachments/assets/c07e0a4a-03d3-4a1b-bb4b-e6a440559f5e)
### 3.2 第2关：交叉测试
本次实验中，我们组使用了陈果和崔函旭小组的明文，密钥组进行交叉测试，效果如下：
![a61e433ee299aec246ad61f76522bc3d](https://github.com/user-attachments/assets/8f869eea-c96a-43cc-8dde-73ae1a503646)
输入相同的明文和密钥，得到了相同的结果：
![image](https://github.com/user-attachments/assets/315992bd-9028-4f5b-8aea-52a0450a7b51)
### 3.3 第3关：扩展功能
测试案例：使用密钥1100101101010010对明文fawoi34524WEVB/*@进行加密，并通过逆向操作验证解密是否成功。
![image](https://github.com/user-attachments/assets/60f2688c-ea20-4cf3-abff-34d75fc5dd00)
### 3.4 第4关：多重加密
#### 3.4.1 双重加密
测试案例：使用密钥10110010100101101010010010101001对明文1011010010100001进行加密，并通过逆向操作验证解密是否成功。
![image](https://github.com/user-attachments/assets/60e51154-654f-4567-982f-ea406560357a)
#### 3.4.2 中间相遇
测试案例：使用明文0111011100011100，密文1010101110101100进行测试，以下是部分找到的结果
![image](https://github.com/user-attachments/assets/094c5931-ffd5-4919-af2a-65fb54e47bfb)
![image](https://github.com/user-attachments/assets/808158d8-d967-4751-812b-b4e6acebad0e)
#### 3.4.3 三重加密
测试案例：使用密钥10110101100011010110111001010110对明文1011001010101011进行加密，并通过逆向操作验证解密是否成功。
![image](https://github.com/user-attachments/assets/5c5a0be4-7d80-4b1c-8d63-b7d689f888dc)


