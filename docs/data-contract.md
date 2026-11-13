# 业务资料约定

温度单位摄氏度，压力单位MPa；a、b、c为质量份额。device为整区设备，history.day相同表示同一设备日。候选表是已通过兼容审查的网格子集，variance_scenarios给两个误差层的方差。

每行id在该表内唯一，文件顺序不代表业务事件顺序。清单schema=1，各表登记文件名、字节长度、SHA256、行数及完整字段集合，未知版本或内容变化应重新登记。金额及测量数值均为独立资料，不代表任何现实机构的经营数据。

- candidates：id、temperature、pressure、a、b、c、device。
- history：id、candidate、day、response、failed。
- budget：id、days、runs_per_day、max_repeats。
- variance_scenarios：id、whole_plot、within_plot。

normal与boundary是相互独立的资料包，不能直接拼接重复id。引用字段按本项目domain.py的REFERENCES登记。读取检查只检查完整性、身份及这些直接引用，不替代领域分析中的可识别性、时点可见性或可行性判断。
