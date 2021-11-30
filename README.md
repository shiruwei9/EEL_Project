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
- Then, run below command, You can change the 500 to any integer, it represents the number of users
```
dotnet fsi --langversion:preview Client.fsx 500 0
```

## Result

![image](https://github.com/shiruwei9/Py/blob/master/4.png)

#### Zipf
(_________________________________________________________________
_________________
_________________
________________)
## Analysis
It takes long more time for the tweet sending especially with hash tag and user mentioned.

Zipf Subscribe cost 2nd most time, since it requires total 2*N subscribes operations.

Query cost the 3nd most time, since it consists of tons of string transmission.

For other operations, it just need N operations, so they don't cost as much time as previous 3 operations.



## Environment:

Device: Dell XPS 15 7590 

Processor: Intel(R) Core(TM) i7-9750H CPU @ 2.60GHz   

RAM: 15.7GB

Runtime Environment: VScode_Linux(WSL: Ubuntu)


Test date: 09/24/2021 
		 	 		
