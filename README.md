# ML-systems
机器学习系统
计划中的内容：
  1. 机器学习系统架构；
  2. 向量召回系统：算法/架构及应用
  3. 最新进展和细节介绍

基础架构：

<img width="643" alt="p1" src="https://user-images.githubusercontent.com/19179476/155679654-e582071b-06f7-4ef5-9e9b-9e97d77f4ffc.png">

机器学习系统架构的基础组成部分：
1. 业务端；
      
      a. 提供原始数据，发起请求；
      
      b. 接收请求，决策；
3. 日志系统；关键指标：时效性，准确率
4. 模型训练系统；关键指标：时效性，准确率
5. 模型服务系统；关键指标：性能(高并发，低延时)，内存/CPU 占用
6. 特征服务系统；

      a. 专为模型提供服务的系统，区别于日志系统；
      
      b. 提供原始数据到特征的映射服务：
      
      c. 特征服务的产生背景：
      
          1. 离线/在线一致性：在线请求模型和离线训练预估模型，需要使用完全一致的特征映射。离线/在线 单独抽特征很容易产生不一致，需要抽象出一个特征抽取模块保证一致性；
          2. 特征计算的冗余性：大量特征计算是重复的，可使用特征服务预先算好特征直接复用；
