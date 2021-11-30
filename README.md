# Project 4 – Twitter Clone (Part 1)
**COP5615 - Distributed Operating Systems Principles**

---
## Group Information

* [Jiaqi Cheng- 34563129]
* [Shiru Wei- 08892233]

---

## Description
We finish **all** functionality of Project4 Part I requirements.

#### Running options 

There 2 files we provide in ./fsx
- `Server.fsx` is the server
- `Client.fsx` is the client, and can do the performace test.


## Implementation
#### Client
The major responsibility of client is to send the message string to the server, and disply the result string to the screen

#### Server
The Twitter Server we biult is basically made up by 3 Class: Tweet, User, and Twitter. 
- Tweet shows the time we sending the tweet, which comes with System time stamp
- User provides the identity of the message and the user.
- Twitter is a Singleton instance, which is consist of many HashMap, in order to speed up the search for "#" and "@"

#### for "#" and "@", HashMap to speed up
Whenever a new Tweet is published, it will be parsed. If it contains "#" or "@", it will then be add to the HashMap.

#### Connecting and disconnecting
When we checked the user is connected/ disconnected, we would update the session/ remove the upcoming update information
After disconnecting, it will no longer refresh automatically.
## How to use

#### Command Explanation

Command format: 
**Very Important**
```
"dotnet fsi --langversion:preview" + "name.fsx" ( + "usernumber" + "function")
```
The function 0 is querying tweets the users subscribed to.
The function 1 is querying tweets with specific hashtag
The function 2 is querying the mentions.(@)

#### Example 1: Functionality
Open 1st terminal as Server
```
dotnet fsi --langversion:preview Server.fsx
```

open 2nd terminal as Client and set up the function
```
dotnet fsi --langversion:preview Clinet.fsx 5 0

```

Then Input Below Command line by line into CLient Terminal
```
engine createUser "user1@gmail.com"
engine createUser "user3@gmail.com"
engine createUser "user4@gmail.com"
engine createUser "user2@gmail.com"
engine createUser "user0@gmail.com"
engine subscribe: add follow info!!!!
engine subscribe: add follow info!!!!
engine subscribe: add follow info!!!!
engine subscribe: add follow info!!!!
engine subscribe: add follow info!!!!
engine sendTweet: add all tweets info!!!
```

![image](https://github.com/shiruwei9/Py/blob/master/1.png)

#### Example 2: Search specific hash tag.(#)
Input Below Command line by line into CLient Terminal
```
dotnet fsi --langversion:preview Clinet.fsx 5 1
```

![image](https://github.com/shiruwei9/Py/blob/master/2.png)

#### Example 3: Search specific user mentioned.(@)
Input Below Command line by line into CLient Terminal
```
dotnet fsi --langversion:preview Clinet.fsx 5 2
```

![image](https://github.com/shiruwei9/Py/blob/master/3.png)

#### Example 4: Performance Test
- Firstly, reopen a Server as mentioned above.
- Then, run below command, You can change the 5 to any integer, it represents the number of users
```
dotnet fsi --langversion:preview Client.fsx 5 0
```

## Result

![image](https://github.com/shiruwei9/Py/blob/master/4.png)

#### time cost in 3 different test scales
All test result obtained from `.fs` file in Jetbrains Rider IDE.
(milliseconds)

- For N<400, we sent a tweet "tweet_content+useri_jth @user$ #topic$ " ($ means random)
- For N>=400, we sent a tweet "t"

| N    | Register  | N users each send 10 tweets | Zipf Subscribe | query N users |  query N hasgtag  |  query N mention | N Randon Ops |
|------|-----------|-----------------------------|----------------|---------------|-------------------|------------------|--------------|
| 5    | 599.6734  | 184.5998                    | 21.8749        | 51.1026       | 29.262            | 24.1199          | 51.5178      |
| 10   | 659.8578  | 387.1673                    | 50.5391        | 103.9618      | 47.1174           | 56.1817          | 53.2401      |
| 25   | 807.435   | 1191.5766                   | 128.7027       | 246.3215      | 128.7414          | 123.4499         | 171.5757     |
| 50   | 769.0788  | 1691.3756                   | 467.9807       | 764.2445      | 493.4429          | 338.9445         | 219.0232     |
| 100  | 1341.3728 | 3748.3057                   | 446.3389       | 930.0312      | 433.1106          | 449.2736         | 947.7343     |
| 200  | 1232.6446 | 6565.2218                   | 865.9617       | 2279.6697     | 1400.8518         | 1336.9309        | 867.6679     |
| 400  | 1486.0643 | 8704.6874                   | 1675.8635      | 1553.9948     | 1303.3077         | 741.304          | 1330.1301    |
| 800  | 2510.7779 | 18426.727                   | 3333.8554      | 2343.8812     | 1452.3169         | 1437.4424        | 2010.4858    |
| 1600 | 4214.8476 | 35609.2485                  | 7195.5841      | 4874.3492     | 2860.3245         | 2820.996         | 4934.7314    |
| 3200 | 7642.8433 | 111190.343                  | 15425.6988     | 14089.3911    | 6775.7368         | 6146.9854        | 10698.6298   |

![](pictures/2.png)

#### number of subscribes, simulate a Zipf distribution
![](pictures/1.png)



## What is the largest network you managed to deal with
the biggest number of users we tested is 3200

We change some cinfiguration under this scenario, tweet content is only a single character "t".


Result is as below
```
The time of register 3200 users is 7642.843300
The time of send 10 tweets is 111190.342900
The time of Zipf subscribe 3200 users is 15425.698800
The time of query 3200 users is 14089.391100
The time of query 3200 hasgtag is 6775.736800
The time of query 3200 mention is 6146.985400
The time of 3200 random operations is 10698.629800
```

## Analysis
Send Tweet cost the most of time, since server will have to parse "@user" and "#topic", this will cost tons of server time. As a result, it's the most time-consuming operations

Zipf Subscribe cost 2nd most time, since it requires total 2*N subscribes operations.

Query cost the 3nd most time, since it consists of tons of string transmission. This will cost a lot of time.

For other operations, it just need N operations, so they don't cost as much time as previous 3 operations.





## Environment

```
- FSharp.Core 3.0.2
- Akka.FSharp 1.2.0
- Akka.Remote 1.2.0
- FsPickler 1.2.21
```

## Environment:

Device: Dell XPS 15 7590 

Processor: Intel(R) Core(TM) i7-9750H CPU @ 2.60GHz   

RAM: 15.7GB

Runtime Environment: VScode_Linux(WSL: Ubuntu)


Test date: 09/24/2021 
		 	 		
