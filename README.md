# COP 5616DOSP project 1

## Group members :
- Zhanhong Huang (UF ID:75580672)
- Shiru Wei      (UF ID:08892233)

## Usage:
1. Open the terminal and go to the directory of the project.

2. Type in the following command:
```
dotnet fsi Boss.fsx 4（the lead 0s, which can be changed)
```
3. Open another terminal and type in the following command:
```
dotnet fsi Worker.fsx 127.0.0.1
```
4. The result will be shown on the first terminal screen.


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



|     n           |     k     |    *workSize    |     # of Threads    |     realTime    |     CPUTime    |     timeRatio     |
|-----------------|-----------|-----------------|---------------------|-----------------|----------------|-------------------|
|     10000000    |     24    |     10000000    |     1               |     8.07        |     8.151      |     0.99006257    |
|     10000000    |     24    |     1000000     |     10              |     6.53        |     13.275     |     0.49190207    |
|     10000000    |     24    |     100000      |     100             |     6.683       |     13.514     |     0.4945242     |
|     10000000    |     24    |    *10000       |     1000            |     6.207       |     13.083     |    *0.47443247    |
|     10000000    |     24    |     1000        |     10000           |     7.154       |     13.49      |     0.53031875    |
|     10000000    |     24    |     100         |     100000          |     10.458      |     17.536     |     0.59637318    |
|     10000000    |     24    |     10          |     1000000         |     15.286      |     23.454     |     0.65174384    |
|     10000000    |     24    |     1           |     10000000        |     01:26.5     |     01:44.9    |     0.82463696    |



|     n           |     k     |    *workSize    |     # of Threads    |     realTime    |     CPUTime    |     timeRatio     |
|-----------------|-----------|-----------------|---------------------|-----------------|----------------|-------------------|
|     10000000    |     24    |     10000000    |     1               |     8.07        |     8.151      |     0.99006257    |
|     10000000    |     24    |     1000000     |     10              |     6.53        |     13.275     |     0.49190207    |
|     10000000    |     24    |     100000      |     100             |     6.683       |     13.514     |     0.4945242     |
|     10000000    |     24    |    *10000       |     1000            |     6.207       |     13.083     |    *0.47443247    |
|     10000000    |     24    |     1000        |     10000           |     7.154       |     13.49      |     0.53031875    |
|     10000000    |     24    |     100         |     100000          |     10.458      |     17.536     |     0.59637318    |
|     10000000    |     24    |     10          |     1000000         |     15.286      |     23.454     |     0.65174384    |
|     10000000    |     24    |     1           |     10000000        |     01:26.5     |     01:44.9    |     0.82463696    |





## 2.

dotnet fsi proj1.fsx 1000000 4
OUTPUT:  Nothing

## 3.
real Time:  0.232s 
CPU Time: 0.442s
Ratio = 1.91

​					



## 4. 
```
The largest problem you managed to solve:    10^8
dotnet fsi proj1.fsx 100000000 24
Results: 
1 9 20 25 44 76 121 197 304 353 540 856 1301 2053 3112 3597 5448 8576 12981 20425 30908 35709 54032 84996 128601 202289 306060 353585 534964 841476 1273121 2002557 3029784 3500233 5295700 8329856 12602701 19823373 29991872 34648837 52422128 82457176
Time: Real: 00:01:08.188, CPU: 00:02:18.363	
```




## Environment:
Device: Dell XPS 15 7590 
Processor: Intel(R) Core(TM) i7-9750H CPU @ 2.60GHz   
RAM: 15.7GB
Runtime Environment: VScode_Linux(WSL: Ubuntu)

Test date: 09/24/2021 
		 	 		
