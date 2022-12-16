# ns3命令

## clean, configure, build and run

**Important:每次修改了cmakelists要重新congfigure一遍** 

```
./ns3 clean 
./ns3 configure --enable-examples --enable-tests
./ns3 build lifi 
./ns3 run lifi-example

```

## Debugging

```
./ns3 run lifi-example --command-template="gdb %s" 
```

## gdb command
### 断点
1. 在某一行设置断点
```
break 117
b 117
```
即在117行设置断点
2. 在某函数设置断点
```
break myfuntion
b myfunction
```
即在myfunction这个函数处设置断点

### 运行

# random

```
There are three primary mechanisms to change the seed or run numbers
 * from their default integer value of 1:
 *
 * 1. Through explicit call of SeedManager::SetSeed () and
 *    SeedManager::SetRun () (commented out below)
 * 2. Through the passing of command line arguments such as:
 *    `./ns3 run program-name --command-template="%s --RngRun=<value>"`
 * 3. Through the use of the NS_GLOBAL_VALUE environment variable, such as:
 *    `$ NS_GLOBAL_VALUE="RngRun=<value>" ./ns3 run program-name`
 
NS_GLOBAL_VALUE="RngRun=3" ./ns3 run lifi-example
SeedManager::SetRun ()
```



```
run(r)
step(s)
continue(c)
```

### 查看trace

```
bt
```



## run program with parameters

```
./ns3 run '<ns3-program> --arg1=value1 --arg2=value2 ...' 
./ns3 run <ns3-program> --command-template="%s <args>" 
./ns3 run test-runner --command-template="%s --suite=mytest --verbose" 
```

## log

### level

- error

- info

- logic
- function
- nocond

### 在代码中更改level

```c++
NS_LOG_FUNCTION (this << congestionTypeId.GetName ());
NS_LOG_UNCOND (this << congestionTypeId.GetName ());
```

### 直接更改环境变量不更改代码

**注意component的大小写，不要多加空格**

标准模板：

```shell
export 'NS_LOG=component_name=which_level|some_prefix'
```
举例：

```
export 'NS_LOG=MpTcpSocketBase=level_all|prefix_func|prefix_time'
export 'NS_LOG=Star=level_all|prefix_func:TcpSocketBase=info|prefix_func' 
export 'NS_LOG=*=error|prefix_func' 
export 'NS_LOG=UdpL4Protocol=logic|prefix_func|prefix_time' 
export 'NS_LOG=TcpL4Protocol=level_all|prefix_func|prefix_time' 
export 'NS_LOG=ArpL3Protocol=logic|prefix_func|prefix_time' 
```


export 'NS_LOG=Ipv4L3Protocol=logic|prefix_func|prefix_time:UdpL4Protocol=logic|prefix_func|prefix_time:ArpL3Protocol=logic|prefix_func|prefix_time' 

 

export 'NS_LOG=LiFiErrorModel=level_all|prefix_func|prefix_time:UdpL4Protocol=logic|prefix_func|prefix_time:ArpL3Protocol=logic|prefix_func|prefix_time' 

 

LiFiErrorModel 

 

 

./ns3 run scratch/mytcpstar >log.out 2>&1 

b TcpSocketBase::ProcessTcpOptions 

 

## 将终端2>&1表示把标准错误输出重定向到标准输出 

TcpSocketBase 

OnOffApplication 

 

## Adding a New Module to ns-3

```
./utils/create-module.py new-module 
```





### PeekHeader

uint32_t ns3::Packet::PeekHeader	(	Header & 	header	)	const

Deserialize but does *not* remove the header from the internal buffer.





# Introduction

- LiFi
  - motivation
  - literature review

- MPTCP
  - motivation
  - literature review

- ns3 introduction


# LiFi Principle

- physical layer
  -  Analytical modeling of LiFi channel (propagation, snr)

- mac layer
- mobility model
  - rotation geometry
  - waypoint random model
- 


# LiFi framework in ns3

how packet transmit through every layer and function



# MPTCP Principle
- Process
- Different Scheduler
- 

# MPTCP Implementation in ns3

- special options
- token




# Integration between WiFi and LiFi
- Handover
- MPTCP
- 

# Performance Evaluation and Discussion
- Senario Design

- Simulation Setup (parameters)

- Result

  

# Conclusions

