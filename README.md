# COP 5616DOSP project 1

## Group members :
- Zhanhong Huang (UF ID:75580672)
- Shiru Wei      (UF ID:08892233)

## Usage:
(1) Open the terminal and go to the directory of the project.

(2) Type in the following command:
```
dotnet fsi Boss.fsx 4（the lead 0s, which can be changed)
```
(3) Open another terminal and type in the following command:
```
dotnet fsi Worker.fsx 127.0.0.1
```
(4) The result will be shown on the first terminal screen.


## 1. Size of the work unit (n = 5, n is the number of leading 0's)

```
n: the number of leading 0's
k: the length of coin
The default option for the coin encryption is 10 times as a round
```


|    n    |     k    |     *workSize    |    real_Time    |     CPU_Time    |     Ratio     |
|---------|----------|------------------|-----------------|-----------------|---------------|
|    5    |     8    |      100000      |     6.215       |     33.620      |     5.4099    |
|    5    |     8    |      10000       |     5.006       |     28.490      |     5.7098    |
|    5    |     8    |      1000        |     4.543       |     26.680      |     5.8732    |
|    5    |     8    |      100*        |     3.674*      |     20.510*     |     5.5828    |
|    5    |     8    |      10          |     7.060       |     46.100      |     6.5299    |
|    5    |     8    |      1           |     22.299      |     208.940     |     9.5670    |

According to the realTime and CPU_Time, when the size of work unit is around 100, the bitcoin machine meets the best performance on our devices.

## 2. The result of running our program for input 4

![image](https://github.com/shiruwei9/EEL_6825_Project/blob/master/Picture2.png)

```
The CPU_runtime is 1.420s
The Real_time is 0.255s
The ration is 485.94%

Note: The bitcoin machine will meet a higher ratio after several rounds of operation because of the higher usage of CPU.
```
## 3.The coin with the most 0s you managed to find

The moset 0s we managed to find is 7

## 4. The largest number of working machines you were able to run your code with

We achieved a system with two working machines


## Environment:

Device: Dell XPS 15 7590 

Processor: Intel(R) Core(TM) i7-9750H CPU @ 2.60GHz   

RAM: 15.7GB

Runtime Environment: VScode_Linux(WSL: Ubuntu)


Test date: 09/24/2021 
		 	 		
