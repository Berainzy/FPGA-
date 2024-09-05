# HLS编译指令
```
#pragma HLS ARRAY_PARTITION variable=data dim=1 complete
```
数组分区命令，将变量名为data的数组在第一维度上进行分区，complete指一种分区方式，将数组完全分割成独立的小块，有助于提高并行处理能力。
```
#pragma HLS BIND_STORAGE variable=const_weight type=ROM_1P impl=LUTRAM
```
作用为指定变量const_weight的存储方式，type=ROM_1P：指定存储类型为单端口只读存储器（Read-Only Memory）。这种类型的存储器适合存储不会改变的数据，如常量或权重。
impl=LUTRAM：指定实现方式为查找表存储器（Look-Up Table RAM）。LUTRAM 是一种 FPGA 上的存储资源，可以用来实现小型的只读存储器或小型的随机访问存储器。它提供了快速的数据访问速度。
```
#pragma HLS PIPELINE II=1 
```
#pragma HLS PIPELINE：这是一个指令，告诉 HLS 工具将紧随其后的函数或循环实现为流水线结构。
II=1：这里的 II 代表 Initiation Interval，即启动间隔。它指定了在流水线中，连续两次迭代之间的时间间隔。II=1 表示每个时钟周期都可以启动一个新的迭代，这是可能的最高流水线并行度。
