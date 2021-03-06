# 关于QUANTAXIS未来的发展方向 [ISSUE 1296](https://github.com/QUANTAXIS/QUANTAXIS/issues/1296)


```

github 开源地址: https://github.com/QUANTAXIS/QUANTAXIS

文档地址: http://doc.yutiansut.com

```

@yutiansut 2019-09-18


QUANTAXIS 目前开源2年有余 在github上获得了约2700+的star和1186+的fork, quant字段下排名第5名, 并且形成了一个较为活跃的社区, 也提供了一个较为完整(谈不上完善)的量化解决方案

在下面的一年里, QUANTAXIS 准备逐步向一下方向发展



## A 1个基础 3个核心

一个基础是

- 快速易用易部署的标准解决方案


三个核心方向

-  数据层的优化

- 分析能力的扩展

- 实时流计算/ 复杂事件处理能力

分布式/集群等作为可扩展功能提供



## B 关于1个基础


快速 ==> 部署快捷/ 安装迅速

易用 ==> 支持全市场量化分析 / 易于扩展 / 完善的文档支持/ 

易于部署 ==>  无缝支持多系统/ 纯新手从安装到使用不超过1小时

标准解决方案 ==> 给出一个工业级功能完整的量化解决方案, 并将组件标准化/ 协议标准化/ 格式标准化/


支持基于docker/ k8s 的单机/集群的 0基础快速部署能力


## C1 关于3个核心 / 数据层

数据层分为三块, 自下而上分为

1. 底层多数据源的可扩展能力

2. 中间层 多数据库的支持能力, 多数据格式的扩展能力,  多场景环境下数据运维的自动化能力

3. 上层的  数据分析的表达能力, 基于gpu的数据运算能力, 机器学习的无缝支持能力, 多市场多标的扩展能力



### C1.1 底层  多数据源的可扩展能力:

1/ 支持商业级数据源 和 免费数据源的自由选择和切换

2/ 支持自定义数据源的导入导出标准

3/ 支持mock数据(可模拟数据)

4/ 支持标准化数据源/ 非标准化的数据源的 扩展


### C1.2 中间层

#### C1.2.1 多数据库的支持能力

计划在2020年底前 官方支持

- mongodb  [作为OLTP的核心]
- redis          [作为实时数据缓存的核心/ 分布式任务收集]
- aresdb       [作为GPU查询的核心]
- clickhouse  [列数据库, 作为OLAP实时查询/策略等上层应用的核心]


#### C1.2.2 多数据格式的扩展能力

官方支持:

- numpy.array
- pd.DataFrame/ pd.Series
- arrow 

支持json/ protobuf 等序列化/反序列化能力

以及一些兼容gpu运算的数据格式

- cudf
- gpudataframe

#### C1.2.3 多场景环境下数据运维的自动化能力

数据的自动清洗

数据定时更新

数据审计/ 数据质量维护


### C.1.3 上层应用 (核心基于QADataStruct)
 
#### C1.3.1 数据分析的表达能力

支持链式计算/ 支持矩阵式广播

#### C1.3.2 基于gpu的数据运算能力

支持gpu列式运算/ cudf等

#### C1.3.3 机器学习的无缝支持能力

支持tensorflow/ pytorch 常用机器学习平台的转化 和结果收集

#### C1.3.4 多市场多标的扩展能力

支持全市场(包括且不限于)

- 主板
- 创业板
- 科创板
- 期货
- 债券/ 可转债/企业债
- 基金
- 港股  股票/指数
- 美股
- 国际期货
- 汇率利率

支持多标的的指标批量运算能力



## C2 关于3个核心 / 分析能力

分析能力分为3块, 分别是


- 历史数据(多周期)的 运算加速
- 实时流数据处理能力
- 数据可视化能力


### C2.1 历史数据(多周期) 运算能力


对于历史数据的多周期指标运算, 回测的加速

tick/ 逐笔级别计算速度的加速

模拟交易的撮合速度加速

### C2.2 实时流数据的处理能力

提供复杂事件处理引擎 提供对于实时的

- 数据流
- 指标流
- 订单流
- 账户数据流
- 新闻信息流

等处理能力, 支持定时任务,周期任务 和 事件驱动任务

### C2.3 数据可视化能力

提供可定制可扩展的 

- 账户数据实时可视化
- 风险指标实时可视化
- 策略事件实时可视化
- 订单流实时可视化
- 流计算中的自定义事件的可视化标准


## C3 关于3个核心 / 流处理能力 & 复杂事件处理能力

#### C3.1 关于流处理能力, 提供

-  标准的业务总线(QAEventMQ) 支持横向扩展能力/ 支持集群部署
-  标准的数据传播/ 事件流的传播能力 (路由/广播/定向/延迟)
-  提供HA高可用的总线服务
-  提供可供可视化的数据流标准事件单元

-  支持高并发事务
-  支持实时的聚合查询等


#### C3.2 复杂事件处理能力

- 提供实时/延迟/定时/循环 的事件处理模式

(如 实时风控/ 云端条件订单/ 定时账单导出/ 循环每日运维/重连)

- 提供多来源/ 多场景的 事件处理能力

(如 新闻/行情等多来源的实时处理能力)
(如 股票  alpha/t0 多策略场景的仓位分配)
(如 股票/期货等多市场的套利处理能力)

- 提供标准的基于金融量化场景定制的复杂事件处理引擎 QCEP


以上很多是部分在内部使用(尚未标准化的)功能和计划, 也有一些是待定尚未完整确定的不稳定计划,  在优先支持内部使用孵化/ 待稳定后会逐步开源

QUANTAXIS 致力于提供一个开放式的标准化解决方案, 希望大家可以拥有一些得心趁手的工具可以在二级市场获得属于自己的alpha, 也希望大家能够 多多提交意见/ 代码更佳~ 