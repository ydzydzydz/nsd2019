# nsd1905_review_day02

网络架构：

- 接入层：负责将主机接入网络
- 汇聚层：负责VLAN间通信
- 核心层：负责到外界的通信

IP地址规划、VLAN规划

- VLAN 1：一教室，192.168.1.0/24
- VLAN 2：二教室，192.168.2.0/24
- VLAN 20：20教室，192.168.20.0/24
- VLAN 101：办公区1，192.168.101.0/24

回答问题套路：nW1H => What / Why / When / Where / How

VLAN：VLAN是虚拟局域网。为了防止在大规模的平面网络中实现广播控制，引入VLAN。首先，根据部门或功能等创建VLAN；然后，将交换机上相应的端口加入到VLAN。为了实现不同交换机上相同VLAN通信，需要配置TRUNK中继。为了实现不同VLAN通信，需要配置三层交换。










