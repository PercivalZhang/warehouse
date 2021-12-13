# REBORN(Nextype) NFT资产分析

## 2. 官网

无

## 3. 区块链网络
**HECO**

## 4. NFT合约
### 4.1 Talent合约

**合约地址:** 0xcfc929bB6cC9cA7559F5A33eef82B8aBCC156600 [点击查看](https://hecoinfo.com/address/0xcfc929bB6cC9cA7559F5A33eef82B8aBCC156600#readContract)


**Code和ABI文件:**
[查看sourcecode和ABI](https://hecoinfo.com/address/0x360A1cE539135E90C3f40cE64D30D577896E896f#code)

### 4.2 LifeNode合约

**合约地址:** 0x3BfB29844759b9B2A486a489DF8977E9659D8179 [点击查看](https://hecoinfo.com/address/0x3BfB29844759b9B2A486a489DF8977E9659D8179#readContract)

**Code和ABI文件:**
[查看sourcecode和ABI](https://hecoinfo.com/address/0x3BfB29844759b9B2A486a489DF8977E9659D8179#code)

### 4.3 LifeMemorial合约

**合约地址:** 0x075f48eeBD8d6fbd8ad22fCDaaaa872Ea35963AC [点击查看](https://hecoinfo.com/address/0x075f48eeBD8d6fbd8ad22fCDaaaa872Ea35963AC#readContract)

**Code和ABI文件:**
[查看sourcecode和ABI](https://hecoinfo.com/address/0x075f48eeBD8d6fbd8ad22fCDaaaa872Ea35963AC#code)

## 5. 关键合约方法
### 5.1 通用方法
**name**() - 获取NFT Token名字

---

> 

**symbol**() - 获取NFT Token名字

---


**totalSupply**() - 获取NFT Token铸造总量

---


**balanceOf**(*address owner*) - 获取目标账户名下的NFT Token数量

**输入参数**
> owner: 目标地址

**返回值**
> 整形int， NFT Token 数量
---

**tokenOfOwnerByIndex**(*address owner*, *int index*) - 获取目标地址名下的NFT token ID列表

 
**输入参数**
> owner: 目标地址

> index: 下标，从0开始，最大值为balanceOf(*address owner*)返回值减去1

**返回值**
> 返回int类型，tokenId

---

**tokensOfOwner**(*address owner*) - 获取目标地址名下的NFT token ID列表和property属性列表

 
**输入参数**
> owner: 目标地址

**返回值**
> 返回值1: int[]数组，tokenId列表

> 返回值2: int[]数组，property列表

**备注说明**
> 两个返回的数组长度相等=tokenId列表的长度，没有property的话，第二个返回值就是一个全0的数组。

> 推荐使用该方法，减少对链的访问次数。

---

**baseURI**() - 获取NFT的URI链接前半部分

**返回值**
> 字符串string， NFT资源链接前半部分

> 以Talent NFT合约为例，其baseURI: https://reborn-apiheco.nextype.finance/card/talent/

---

**tokenURI**(*int tokenId*) - 获取指定Id的token对应的URI

 
**输入参数**
> tokenId: token编号

**返回值**
> token URI, 字符串类型

> 以Talent NFT合约为例，其编号7210的NFT的tokenURI: https://reborn-apiheco.nextype.finance/card/talent/12061/7210


## 7. NFT Token Metadata
通过NFT token的tokenURI获取NFT的metadata元数据。

以下列举了三种NFT合约对应的三个NFT的元数据以供参考。

> 备注：本项目有两种NFT（LifeNode和LifeMemorial）的metadata中的部分字段做了编码处理，可以参见章节7.4中的说明进行相应的解码操作。

### 7.1 Talent合约下编号7210的NFT的metadata数据
```
{
    "icon":"resource\/assets\/talent\/12061.png",
    "name":"Prudent","age":"[0]",
    "image":"https:\/\/reborn-appheco.nextype.finance\/\/resource\/assets\/nft\/T3.png",
    "image_small":"https:\/\/reborn-appheco.nextype.finance\/\/resource\/assets\/nft\/T3.png",
    "description":"You are prudent in everything. INT+1",
    "desc":"You are prudent in everything. INT+1",
    "chr":0,"int":1,"str":0,"mny":0,"spr":0,"attr_num":0,"rarity":3
}
```

### 7.2 LifeNode合约下编号1的NFT的metadata数据
```
{
    "image":[104,116,116,112,115,58,47,47,114,101,98,111,114,110,45,97,112,112,104,101,99,111,46,110,101,120,116,121,112,101,46,102,105,110,97,110,99,101,47,47,114,101,115,111,117,114,99,101,47,97,115,115,101,116,115,47,110,102,116,47,78,46,112,110,103],
    "image_small":[104,116,116,112,115,58,47,47,114,101,98,111,114,110,45,97,112,112,104,101,99,111,46,110,101,120,116,121,112,101,46,102,105,110,97,110,99,101,47,47,114,101,115,111,117,114,99,101,47,97,115,115,101,116,115,47,110,102,116,47,78,46,112,110,103],
    "name":[76,105,102,101,32,78,111,100,101,32,67,97,114,100],
    "description":[76,105,102,101,32,78,111,100,101,32,67,97,114,100],
    "age":30,
    "score":21500,
    "attr":{
        "int":12,
        "str":10,
        "chr":2,
        "spr":4,
        "mny":5
    },
    "genius":[
        {
            "icon":"resource\/assets\/talent\/10120.png",
            "name":"Inner intelligence IV",
            "age":"[0,30,60,90]",
            "image":"https:\/\/reborn-appheco.nextype.finance\/\/resource\/assets\/nft\/T4.png",
            "image_small":"https:\/\/reborn-appheco.nextype.finance\/\/resource\/assets\/nft\/T4.png",
            "description":"INT+4",
            "desc":"INT+4",
            "chr":0,
            "int":4,
            "str":0,
            "mny":0,
            "spr":0,
            "attr_num":0,
            "rarity":4
        },
        {
            "icon":"resource\/assets\/talent\/10070.png",
            "name":"Pessimism I",
            "age":"[0,30,60,90]",
            "image":"https:\/\/reborn-appheco.nextype.finance\/\/resource\/assets\/nft\/T1.png",
            "image_small":"https:\/\/reborn-appheco.nextype.finance\/\/resource\/assets\/nft\/T1.png",
            "description":"DEL-1",
            "desc":"DEL-1",
            "chr":0,
            "int":0,
            "str":0,
            "mny":0,
            "spr":-1,
            "attr_num":0,
            "rarity":1
        },
        {
            "icon":"resource\/assets\/talent\/11030.png",
            "name":"Tough I",
            "age":"[0,30]",
            "image":"https:\/\/reborn-appheco.nextype.finance\/\/resource\/assets\/nft\/T2.png",
            "image_small":"https:\/\/reborn-appheco.nextype.finance\/\/resource\/assets\/nft\/T2.png",
            "description":"PHY+2 at the age of 40",
            "desc":"PHY+2 at the age of 40",
            "chr":0,
            "int":0,
            "str":2,
            "mny":0,
            "spr":0,
            "attr_num":0,
            "rarity":2
        }
    ],
    "age_events":[
        {
            "age":0,
            "events":[
                {
                    "event_id":100100,
                    "msg":"You are born as a boy.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100100.png"
                }
            ]
        },
        {
            "age":1,
            "events":[
                {
                    "event_id":100220,
                    "msg":"Your live in a dark basement under a busy street.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100220.png"
                }
            ]
        },
        {
            "age":2,
            "events":[
                {
                    "event_id":101040,
                    "msg":"You love watching stars alone.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/101040.png"
                }
            ]
        },
        {
            "age":3,
            "events":[
                {
                    "event_id":100630,
                    "msg":"Your parents are divorced.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100630.png"
                }
            ]
        },
        {
            "age":4,
            "events":[
                {
                    "event_id":100910,
                    "msg":"You have a dog.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100910.png"
                }
            ]
        },
        {
            "age":5,
            "events":[
                {
                    "event_id":101080,
                    "msg":"You have read a lot of books since you were a kid.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/101080.png"
                }
            ]
        },
        {
            "age":6,
            "events":[
                {
                    "event_id":105010,
                    "msg":"You attend a public elementary school.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105010.png"
                }
            ]
        },
        {
            "age":7,
            "events":[
                {
                    "event_id":105220,
                    "msg":"There is a little girl you like very much in the class.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105220.png"
                }
            ]
        },
        {
            "age":8,
            "events":[
                {
                    "event_id":105510,
                    "msg":"Your parents are so busy that you have little chance to meet them.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105510.png"
                }
            ]
        },
        {
            "age":9,
            "events":[
                {
                    "event_id":107000,
                    "msg":"Part of the school's equipment is in disrepair for many years, you lose a lot of fun.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/107000.png"
                }
            ]
        },
        {
            "age":10,
            "events":[
                {
                    "event_id":100560,
                    "msg":"Your parents give birth to another daughter.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100560.png"
                }
            ]
        },
        {
            "age":11,
            "events":[
                {
                    "event_id":100640,
                    "msg":"Your father rarely comes back home.",
                    "add_msg":"You don't even remember the exact looks of your father.",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100640.png"
                }
            ]
        },
        {
            "age":12,
            "events":[
                {
                    "event_id":110201,
                    "msg":"You hate going to school so you don't go to a middle school.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/110201.png"
                }
            ]
        },
        {
            "age":13,
            "events":[
                {
                    "event_id":101390,
                    "msg":"Your parents don't give you allowance.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/101390.png"
                }
            ]
        },
        {
            "age":14,
            "events":[
                {
                    "event_id":101010,
                    "msg":"Parents take you to the beach to play.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/101010.png"
                }
            ]
        },
        {
            "age":15,
            "events":[
                {
                    "event_id":114001,
                    "msg":"You enter society early and start finding a job.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/114001.png"
                }
            ]
        },
        {
            "age":16,
            "events":[
                {
                    "event_id":130500,
                    "msg":"You witness a rare meteor shower with your own eyes.",
                    "add_msg":"",
                    "branch_id":130510,
                    "icon":"resource\/assets\/event\/130500.png"
                },
                {
                    "event_id":130510,
                    "msg":"You make a wish.",
                    "add_msg":"",
                    "branch_id":130511,
                    "icon":"resource\/assets\/event\/130510.png"
                },
                {
                    "event_id":130511,
                    "msg":"You don't know why you become more open-minded.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130511.png"
                }
            ]
        },
        {
            "age":17,
            "events":[
                {
                    "event_id":100780,
                    "msg":"Your parents buy lottery tickets.",
                    "add_msg":"Of course you don't win the lottery.",
                    "branch_id":100781,
                    "icon":"resource\/assets\/event\/100780.png"
                },
                {
                    "event_id":100781,
                    "msg":"Win a 10 dollars lottery.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100780.png"
                }
            ]
        },
        {
            "age":18,
            "events":[
                {
                    "event_id":115650,
                    "msg":"You have become a vagrant.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/115650.png"
                }
            ]
        },
        {
            "age":19,
            "events":[
                {
                    "event_id":114003,
                    "msg":"You start trying to make your own living.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/114003.png"
                }
            ]
        },
        {
            "age":20,
            "events":[
                {
                    "event_id":115650,
                    "msg":"You have become a vagrant.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/115650.png"
                }
            ]
        },
        {
            "age":21,
            "events":[
                {
                    "event_id":114003,
                    "msg":"You start trying to make your own living.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/114003.png"
                }
            ]
        },
        {
            "age":22,
            "events":[
                {
                    "event_id":115650,
                    "msg":"You have become a vagrant.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/115650.png"
                }
            ]
        },
        {
            "age":23,
            "events":[
                {
                    "event_id":114003,
                    "msg":"You start trying to make your own living.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/114003.png"
                }
            ]
        },
        {
            "age":24,
            "events":[
                {
                    "event_id":115600,
                    "msg":"You become a programmer.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/115600.png"
                }
            ]
        },
        {
            "age":25,
            "events":[
                {
                    "event_id":117250,
                    "msg":"You start to learn about cryptocurrencies in your spare time.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/117250.png"
                }
            ]
        },
        {
            "age":26,
            "events":[
                {
                    "event_id":135520,
                    "msg":"Quantum chips have entered the stage of civilian use.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135520.png"
                }
            ]
        },
        {
            "age":27,
            "events":[
                {
                    "event_id":200015,
                    "msg":"You joined the Technical Department of the SafePal Team and became a programmer, your haters now pay you SFP tokens for advice!",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/200015.png"
                }
            ]
        },
        {
            "age":28,
            "events":[
                {
                    "event_id":135630,
                    "msg":"Crude oil futures (WTI) fall to -40 USD.",
                    "add_msg":"",
                    "branch_id":135632,
                    "icon":"resource\/assets\/event\/135630.png"
                },
                {
                    "event_id":135632,
                    "msg":"You successfully buy the dips when the price is -37 USD and make a lot of money.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135632.png"
                }
            ]
        },
        {
            "age":29,
            "events":[
                {
                    "event_id":130560,
                    "msg":"You like baseball, often go to the stadium to watch baseball games and your favorite stars.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130560.png"
                }
            ]
        },
        {
            "age":30,
            "events":[
                {
                    "event_id":130901,
                    "msg":"You have a low self-esteem for your looks.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130901.png"
                }
            ]
        }
    ]
}
```

### 7.3 LifeMemorial合约下编号1372的NFT的metadata数据

```
{
    "image":[104,116,116,112,115,58,47,47,114,101,98,111,114,110,45,97,112,112,104,101,99,111,46,110,101,120,116,121,112,101,46,102,105,110,97,110,99,101,47,47,114,101,115,111,117,114,99,101,47,97,115,115,101,116,115,47,110,102,116,47,77,46,112,110,103],
    "image_small":[104,116,116,112,115,58,47,47,114,101,98,111,114,110,45,97,112,112,104,101,99,111,46,110,101,120,116,121,112,101,46,102,105,110,97,110,99,101,47,47,114,101,115,111,117,114,99,101,47,97,115,115,101,116,115,47,110,102,116,47,77,46,112,110,103],
    "name":[76,105,102,101,32,77,101,109,111,114,105,97,108,32,32,67,97,114,100],
    "description":[76,105,102,101,32,77,101,109,111,114,105,97,108,32,32,67,97,114,100],
    "age":156,
    "score":97800,
    "attr":{
        "int":7,
        "str":10,
        "chr":8,
        "spr":19,
        "mny":14
    },
    "genius":[
        {
            "icon":"resource\/assets\/talent\/10120.png",
            "name":"Inner intelligence I",
            "age":"[0,30,60,90]",
            "image":"https:\/\/reborn-appheco.nextype.finance\/\/resource\/assets\/nft\/T1.png",
            "image_small":"https:\/\/reborn-appheco.nextype.finance\/\/resource\/assets\/nft\/T1.png",
            "description":"INT+1",
            "desc":"INT+1",
            "chr":0,
            "int":1,
            "str":0,
            "mny":0,
            "spr":0,
            "attr_num":0,
            "rarity":1
        },
        {
            "icon":"resource\/assets\/talent\/10130.png",
            "name":"Strong body I",
            "age":"[0,30,60,90]",
            "image":"https:\/\/reborn-appheco.nextype.finance\/\/resource\/assets\/nft\/T1.png",
            "image_small":"https:\/\/reborn-appheco.nextype.finance\/\/resource\/assets\/nft\/T1.png",
            "description":"PHY+1",
            "desc":"PHY+1",
            "chr":0,
            "int":0,
            "str":1,
            "mny":0,
            "spr":0,
            "attr_num":0,
            "rarity":1
        },
        {
            "icon":"resource\/assets\/talent\/10140.png",
            "name":"Well-off family I",
            "age":"[0,30,60,90]",
            "image":"https:\/\/reborn-appheco.nextype.finance\/\/resource\/assets\/nft\/T1.png",
            "image_small":"https:\/\/reborn-appheco.nextype.finance\/\/resource\/assets\/nft\/T1.png",
            "description":"FAM+1",
            "desc":"FAM+1",
            "chr":0,
            "int":0,
            "str":0,
            "mny":1,
            "spr":0,
            "attr_num":0,
            "rarity":1
        }
    ],
    "age_events":[
        {
            "age":0,
            "events":[
                {
                    "event_id":100110,
                    "msg":"You are born as a girl.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100110.png"
                }
            ]
        },
        {
            "age":1,
            "events":[
                {
                    "event_id":100260,
                    "msg":"Your family owns large fields with beautiful scenery.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100260.png"
                }
            ]
        },
        {
            "age":2,
            "events":[
                {
                    "event_id":100560,
                    "msg":"Your parents give birth to another daughter.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100560.png"
                }
            ]
        },
        {
            "age":3,
            "events":[
                {
                    "event_id":100500,
                    "msg":"You haven't learned how to speak.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100500.png"
                }
            ]
        },
        {
            "age":4,
            "events":[
                {
                    "event_id":100540,
                    "msg":"You run faster than your peers.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100540.png"
                }
            ]
        },
        {
            "age":5,
            "events":[
                {
                    "event_id":105011,
                    "msg":"You attend a public elementary school.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105011.png"
                }
            ]
        },
        {
            "age":6,
            "events":[
                {
                    "event_id":100590,
                    "msg":"Your parents let you grow up freely.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100590.png"
                }
            ]
        },
        {
            "age":7,
            "events":[
                {
                    "event_id":105830,
                    "msg":"You have a unique talent for music and love it very much.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105830.png"
                }
            ]
        },
        {
            "age":8,
            "events":[
                {
                    "event_id":100960,
                    "msg":"Your mother's career is flourishing.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100960.png"
                }
            ]
        },
        {
            "age":9,
            "events":[
                {
                    "event_id":105831,
                    "msg":"You begin to practice composing a symphony.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105830.png"
                }
            ]
        },
        {
            "age":10,
            "events":[
                {
                    "event_id":105280,
                    "msg":"You start to be exposed to investment and financial management at a young age.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105280.png"
                }
            ]
        },
        {
            "age":11,
            "events":[
                {
                    "event_id":105650,
                    "msg":"You climb onto the tree and fall off.",
                    "add_msg":"",
                    "branch_id":105651,
                    "icon":"resource\/assets\/event\/105650.png"
                },
                {
                    "event_id":105651,
                    "msg":"You fall to the ground with a backflip.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105650.png"
                }
            ]
        },
        {
            "age":12,
            "events":[
                {
                    "event_id":110201,
                    "msg":"You hate going to school so you don't go to a middle school.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/110201.png"
                }
            ]
        },
        {
            "age":13,
            "events":[
                {
                    "event_id":101080,
                    "msg":"You have read a lot of books since you were a kid.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/101080.png"
                }
            ]
        },
        {
            "age":14,
            "events":[
                {
                    "event_id":110450,
                    "msg":"You have extremely important friends.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/110450.png"
                }
            ]
        },
        {
            "age":15,
            "events":[
                {
                    "event_id":114001,
                    "msg":"You enter society early and start finding a job.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/114001.png"
                }
            ]
        },
        {
            "age":16,
            "events":[
                {
                    "event_id":135590,
                    "msg":"Supersonic passenger planes are for large-scale civilian use again.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135590.png"
                }
            ]
        },
        {
            "age":17,
            "events":[
                {
                    "event_id":100840,
                    "msg":"You have an excellent financial talent since you were a child.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100840.png"
                }
            ]
        },
        {
            "age":18,
            "events":[
                {
                    "event_id":115640,
                    "msg":"You have found a comfortable job.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/115640.png"
                }
            ]
        },
        {
            "age":19,
            "events":[
                {
                    "event_id":135480,
                    "msg":"A certain country tests a 200 million equivalent nuclear bomb.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135480.png"
                }
            ]
        },
        {
            "age":20,
            "events":[
                {
                    "event_id":130660,
                    "msg":"Elon Musk says he wants to set up spacex.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130660.png"
                }
            ]
        },
        {
            "age":21,
            "events":[
                {
                    "event_id":120490,
                    "msg":"You watch dramas on netflix every day.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/120490.png"
                }
            ]
        },
        {
            "age":22,
            "events":[
                {
                    "event_id":115642,
                    "msg":"You travel to the nearby suburbs when you have nothing to do.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/115642.png"
                }
            ]
        },
        {
            "age":23,
            "events":[
                {
                    "event_id":114932,
                    "msg":"You and your friends go boating in the lake.",
                    "add_msg":"",
                    "branch_id":114933,
                    "icon":"resource\/assets\/event\/114932.png"
                },
                {
                    "event_id":114933,
                    "msg":"You enjoy the beautiful scenery quietly.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/114933.png"
                }
            ]
        },
        {
            "age":24,
            "events":[
                {
                    "event_id":200000,
                    "msg":"You have started using SafePal products, the security of your digital assets has improved!",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/200000.png"
                }
            ]
        },
        {
            "age":25,
            "events":[
                {
                    "event_id":130500,
                    "msg":"You witness a rare meteor shower with your own eyes.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130500.png"
                }
            ]
        },
        {
            "age":26,
            "events":[
                {
                    "event_id":101480,
                    "msg":"The cat that accompanied your childhood has passed away.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/101480.png"
                }
            ]
        },
        {
            "age":27,
            "events":[
                {
                    "event_id":200002,
                    "msg":"You recommended SafePal to your friends, and all your friends praise you after using it!",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/200002.png"
                }
            ]
        },
        {
            "age":28,
            "events":[
                {
                    "event_id":114910,
                    "msg":"In your spare time, you like to play snooker.",
                    "add_msg":"",
                    "branch_id":114911,
                    "icon":"resource\/assets\/event\/114910.png"
                },
                {
                    "event_id":114911,
                    "msg":"You play well.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/114911.png"
                }
            ]
        },
        {
            "age":29,
            "events":[
                {
                    "event_id":120470,
                    "msg":"You will take a look at pixiv and upload your own work in your spare time.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/120470.png"
                }
            ]
        },
        {
            "age":30,
            "events":[
                {
                    "event_id":126005,
                    "msg":"You move to a cottage in the country and run your own small garden.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/126005.png"
                }
            ]
        },
        {
            "age":31,
            "events":[
                {
                    "event_id":120380,
                    "msg":"You often watch football games.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/120380.png"
                }
            ]
        },
        {
            "age":32,
            "events":[
                {
                    "event_id":200003,
                    "msg":"In the process of transferring your digital assets, SafePal helps you save a lot of costs!",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/200003.png"
                }
            ]
        },
        {
            "age":33,
            "events":[
                {
                    "event_id":200001,
                    "msg":"Because you use SafePal products, you avoid the loss of  your digital assets!",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/200001.png"
                }
            ]
        },
        {
            "age":34,
            "events":[
                {
                    "event_id":130640,
                    "msg":"You buy Tesla's early stock as a support for your idol.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130640.png"
                }
            ]
        },
        {
            "age":35,
            "events":[
                {
                    "event_id":130620,
                    "msg":"You are not satisfied with your appearance, so you are considering plastic surgery.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130620.png"
                }
            ]
        },
        {
            "age":36,
            "events":[
                {
                    "event_id":200007,
                    "msg":"SFP Tokens issued by SafePal soared by 100000%! And you bought several a year ago!",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/200007.png"
                }
            ]
        },
        {
            "age":37,
            "events":[
                {
                    "event_id":110650,
                    "msg":"You have a fight with street gangsters.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/110650.png"
                }
            ]
        },
        {
            "age":38,
            "events":[
                {
                    "event_id":200039,
                    "msg":"You met the SafePal team while traveling around the world, and they enthusiastically took a group photo with you!",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/200039.png"
                }
            ]
        },
        {
            "age":39,
            "events":[
                {
                    "event_id":125130,
                    "msg":"You drive around the country with your family.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125130.png"
                }
            ]
        },
        {
            "age":40,
            "events":[
                {
                    "event_id":120435,
                    "msg":"You are addicted to Facebook and often share your life on it.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/120435.png"
                }
            ]
        },
        {
            "age":41,
            "events":[
                {
                    "event_id":115780,
                    "msg":"You start to pay attention to cryptocurrencies.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/115780.png"
                }
            ]
        },
        {
            "age":42,
            "events":[
                {
                    "event_id":115671,
                    "msg":"You have been taking good care of your figure.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/115670.png"
                }
            ]
        },
        {
            "age":43,
            "events":[
                {
                    "event_id":120280,
                    "msg":"Every investment you make has a huge impact on the cryptocurrency market.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/120280.png"
                }
            ]
        },
        {
            "age":44,
            "events":[
                {
                    "event_id":120425,
                    "msg":"You like to travel and share your travel feelings on twitter.",
                    "add_msg":"",
                    "branch_id":120426,
                    "icon":"resource\/assets\/event\/120425.png"
                },
                {
                    "event_id":120426,
                    "msg":"You become a well-known travel blogger on Twitter.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/120426.png"
                }
            ]
        },
        {
            "age":45,
            "events":[
                {
                    "event_id":200015,
                    "msg":"You joined the Technical Department of the SafePal Team and became a programmer, your haters now pay you SFP tokens for advice!",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/200015.png"
                }
            ]
        },
        {
            "age":46,
            "events":[
                {
                    "event_id":115800,
                    "msg":"You invest in cryptocurrencies.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/115800.png"
                }
            ]
        },
        {
            "age":47,
            "events":[
                {
                    "event_id":115810,
                    "msg":"The cryptocurrency you buy has doubled hundreds of times in a short period of time.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/115810.png"
                }
            ]
        },
        {
            "age":48,
            "events":[
                {
                    "event_id":130675,
                    "msg":"You buy a shiba for 8,000 dollars.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130675.png"
                }
            ]
        },
        {
            "age":49,
            "events":[
                {
                    "event_id":115930,
                    "msg":"You devote yourself to cryptocurrency investment, and you don't want to miss a single second.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/115930.png"
                }
            ]
        },
        {
            "age":50,
            "events":[
                {
                    "event_id":115940,
                    "msg":"You have become a celebrity in the cryptocurrency circle, and your methodology is highly respected.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/115940.png"
                }
            ]
        },
        {
            "age":51,
            "events":[
                {
                    "event_id":115660,
                    "msg":"You get up early for a run every day.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/115660.png"
                }
            ]
        },
        {
            "age":52,
            "events":[
                {
                    "event_id":120411,
                    "msg":"You become a very popular gourmet anchor of Tiktok.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/120411.png"
                }
            ]
        },
        {
            "age":53,
            "events":[
                {
                    "event_id":130655,
                    "msg":"Tesla stock has skyrocketed so you buy a model X to reward yourself.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130655.png"
                }
            ]
        },
        {
            "age":54,
            "events":[
                {
                    "event_id":130680,
                    "msg":"Your shiba has soared by 700,000 times. But you need 312 years to claim it.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130680.png"
                }
            ]
        },
        {
            "age":55,
            "events":[
                {
                    "event_id":125170,
                    "msg":"You contract a small shop with your spouse.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125170.png"
                }
            ]
        },
        {
            "age":56,
            "events":[
                {
                    "event_id":120270,
                    "msg":"You secretly control the economic lifeline of the entire country.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/120270.png"
                }
            ]
        },
        {
            "age":57,
            "events":[
                {
                    "event_id":125060,
                    "msg":"You occasionally flip through your childhood pictures.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125060.png"
                }
            ]
        },
        {
            "age":58,
            "events":[
                {
                    "event_id":125100,
                    "msg":"You like to repair your own yard.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125100.png"
                }
            ]
        },
        {
            "age":59,
            "events":[
                {
                    "event_id":126000,
                    "msg":"You and your family travel around in an RV.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/126000.png"
                }
            ]
        },
        {
            "age":60,
            "events":[
                {
                    "event_id":120210,
                    "msg":"You and your friend establish a cryptocurrency exchange.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/120210.png"
                }
            ]
        },
        {
            "age":61,
            "events":[
                {
                    "event_id":126035,
                    "msg":"You often go out with old friends to reminisce about the past.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/126035.png"
                }
            ]
        },
        {
            "age":62,
            "events":[
                {
                    "event_id":125420,
                    "msg":"Your spouse is unable to move because of old age.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125420.png"
                }
            ]
        },
        {
            "age":63,
            "events":[
                {
                    "event_id":130160,
                    "msg":"You are shot.",
                    "add_msg":"",
                    "branch_id":130161,
                    "icon":"resource\/assets\/event\/130160.png"
                },
                {
                    "event_id":130161,
                    "msg":"No fatal injuries are caused.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130161.png"
                }
            ]
        },
        {
            "age":64,
            "events":[
                {
                    "event_id":126010,
                    "msg":"You get well along with the neighbors in the village.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/126010.png"
                }
            ]
        },
        {
            "age":65,
            "events":[
                {
                    "event_id":125260,
                    "msg":"You like to go to the square to feed the pigeons.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125260.png"
                }
            ]
        },
        {
            "age":66,
            "events":[
                {
                    "event_id":135440,
                    "msg":"The United States announce to use bitcoin as legal currency.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135440.png"
                }
            ]
        },
        {
            "age":67,
            "events":[
                {
                    "event_id":130665,
                    "msg":"You are a fan of Elon Musk. You are waiting for spaceX to go public.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130665.png"
                }
            ]
        },
        {
            "age":68,
            "events":[
                {
                    "event_id":125332,
                    "msg":"You make some friends in the nursing home.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125332.png"
                }
            ]
        },
        {
            "age":69,
            "events":[
                {
                    "event_id":125470,
                    "msg":"You are far more open-minded than other elderly people.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125470.png"
                }
            ]
        },
        {
            "age":70,
            "events":[
                {
                    "event_id":126015,
                    "msg":"You are highly respected in the family.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/126015.png"
                }
            ]
        },
        {
            "age":71,
            "events":[
                {
                    "event_id":130670,
                    "msg":"Elon Musk mentions a new cryptocurrency, Dogecoin. You buy some dogecoins.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130670.png"
                }
            ]
        },
        {
            "age":72,
            "events":[
                {
                    "event_id":135430,
                    "msg":"Many countries in Africa enter the list of developed countries.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135430.png"
                }
            ]
        },
        {
            "age":73,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":74,
            "events":[
                {
                    "event_id":125300,
                    "msg":"You miss your youth.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125300.png"
                }
            ]
        },
        {
            "age":75,
            "events":[
                {
                    "event_id":126040,
                    "msg":"You often bask in the sun all afternoon on the balcony.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/126040.png"
                }
            ]
        },
        {
            "age":76,
            "events":[
                {
                    "event_id":135610,
                    "msg":"There are 4 circuit breakers for U.S. stocks in 10 days.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135610.png"
                }
            ]
        },
        {
            "age":77,
            "events":[
                {
                    "event_id":125340,
                    "msg":"Your children rarely come to visit you.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125340.png"
                }
            ]
        },
        {
            "age":78,
            "events":[
                {
                    "event_id":125450,
                    "msg":"Time doesn't seem to leave a mark on your face.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125450.png"
                }
            ]
        },
        {
            "age":79,
            "events":[
                {
                    "event_id":130685,
                    "msg":"You are invited to take a 15-minute space trip, for which you pay $28 million.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130685.png"
                }
            ]
        },
        {
            "age":80,
            "events":[
                {
                    "event_id":125460,
                    "msg":"Despite your old age, your mind is still moving like flying.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125460.png"
                }
            ]
        },
        {
            "age":81,
            "events":[
                {
                    "event_id":135520,
                    "msg":"Quantum chips have entered the stage of civilian use.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135520.png"
                }
            ]
        },
        {
            "age":82,
            "events":[
                {
                    "event_id":125270,
                    "msg":"You like to watch people come and go by the window.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125270.png"
                }
            ]
        },
        {
            "age":83,
            "events":[
                {
                    "event_id":115670,
                    "msg":"You feel like you are no longer young and beautiful.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/115670.png"
                }
            ]
        },
        {
            "age":84,
            "events":[
                {
                    "event_id":120790,
                    "msg":"You have witnessed a gang firefight.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/120790.png"
                }
            ]
        },
        {
            "age":85,
            "events":[
                {
                    "event_id":125220,
                    "msg":"You fall while walking.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125220.png"
                }
            ]
        },
        {
            "age":86,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":87,
            "events":[
                {
                    "event_id":125250,
                    "msg":"You like to sit on the street all day.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125250.png"
                }
            ]
        },
        {
            "age":88,
            "events":[
                {
                    "event_id":130760,
                    "msg":"Company Y announced that they have developed a mechanical limb with a 20-year warranty.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130760.png"
                }
            ]
        },
        {
            "age":89,
            "events":[
                {
                    "event_id":105710,
                    "msg":"You have had a happy year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105710.png"
                }
            ]
        },
        {
            "age":90,
            "events":[
                {
                    "event_id":126025,
                    "msg":"You and other old people are dancing to music on the street corner.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/126025.png"
                }
            ]
        },
        {
            "age":91,
            "events":[
                {
                    "event_id":135210,
                    "msg":"No country wants to bid for the Olympics, and the Olympics is ceased.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135210.png"
                }
            ]
        },
        {
            "age":92,
            "events":[
                {
                    "event_id":135200,
                    "msg":"The Nobel Prize is cancelled.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135200.png"
                }
            ]
        },
        {
            "age":93,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":94,
            "events":[
                {
                    "event_id":130756,
                    "msg":"You are getting old and your limbs are shrinking.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130756.png"
                }
            ]
        },
        {
            "age":95,
            "events":[
                {
                    "event_id":130761,
                    "msg":"You start to replace your limbs with mechanical ones one after another, it feels a little weird",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130761.png"
                }
            ]
        },
        {
            "age":96,
            "events":[
                {
                    "event_id":125290,
                    "msg":"You feel that there are fewer and fewer people who you can talk with.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125290.png"
                }
            ]
        },
        {
            "age":97,
            "events":[
                {
                    "event_id":126030,
                    "msg":"You still insist on climbing and exercising.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/126030.png"
                }
            ]
        },
        {
            "age":98,
            "events":[
                {
                    "event_id":125480,
                    "msg":"There are not many of your peers left.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125480.png"
                }
            ]
        },
        {
            "age":99,
            "events":[
                {
                    "event_id":125210,
                    "msg":"You feel that your body is getting weaker.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125210.png"
                }
            ]
        },
        {
            "age":100,
            "events":[
                {
                    "event_id":125490,
                    "msg":"You are the last one of your classmates to be alive.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125490.png"
                }
            ]
        },
        {
            "age":101,
            "events":[
                {
                    "event_id":135630,
                    "msg":"Crude oil futures (WTI) fall to -40 USD.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135630.png"
                }
            ]
        },
        {
            "age":102,
            "events":[
                {
                    "event_id":130650,
                    "msg":"Elon Musk says that you can buy a car with bitcoin so you book a CYBERTRUCK.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130650.png"
                }
            ]
        },
        {
            "age":103,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":104,
            "events":[
                {
                    "event_id":125440,
                    "msg":"You look younger than other people of your age.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125440.png"
                }
            ]
        },
        {
            "age":105,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":106,
            "events":[
                {
                    "event_id":130645,
                    "msg":"You buy a model 3.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130645.png"
                }
            ]
        },
        {
            "age":107,
            "events":[
                {
                    "event_id":142400,
                    "msg":"It's difficult for you to move.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/142400.png"
                }
            ]
        },
        {
            "age":108,
            "events":[
                {
                    "event_id":125280,
                    "msg":"All your friends have passed away.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/125280.png"
                }
            ]
        },
        {
            "age":109,
            "events":[
                {
                    "event_id":135620,
                    "msg":"There is a large backlog of cargo at the Port of L.A.",
                    "add_msg":"",
                    "branch_id":135621,
                    "icon":"resource\/assets\/event\/135620.png"
                },
                {
                    "event_id":135621,
                    "msg":"The things you buy online are piled up at the port, and the time of receipt is far away.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135621.png"
                }
            ]
        },
        {
            "age":110,
            "events":[
                {
                    "event_id":114724,
                    "msg":"Pioneer F has been out of Earth for 100 years.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/114724.png"
                }
            ]
        },
        {
            "age":111,
            "events":[
                {
                    "event_id":135600,
                    "msg":"The Hindenburg tourist space shuttle explodes in low-Earth orbit, and space shuttles are eliminated for the second time.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135600.png"
                }
            ]
        },
        {
            "age":112,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":113,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":114,
            "events":[
                {
                    "event_id":105701,
                    "msg":"You have had a bad year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":115,
            "events":[
                {
                    "event_id":114710,
                    "msg":"Scientists say that an asteroid will hit the Earth in a few years.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/114710.png"
                }
            ]
        },
        {
            "age":116,
            "events":[
                {
                    "event_id":135240,
                    "msg":"Commercial pleasure stimulators have been launched and have not yet been approved for production.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135240.png"
                }
            ]
        },
        {
            "age":117,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":118,
            "events":[
                {
                    "event_id":105701,
                    "msg":"You have had a bad year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":119,
            "events":[
                {
                    "event_id":126020,
                    "msg":"You are meticulous in taking care of your appearance.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/126020.png"
                }
            ]
        },
        {
            "age":120,
            "events":[
                {
                    "event_id":142402,
                    "msg":"You can't remember the last time you did something you like.",
                    "add_msg":"",
                    "branch_id":142403,
                    "icon":"resource\/assets\/event\/142402.png"
                },
                {
                    "event_id":142403,
                    "msg":"But your body can't do it anymore.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/142403.png"
                }
            ]
        },
        {
            "age":121,
            "events":[
                {
                    "event_id":130762,
                    "msg":"You have used the fourth-generation mechanical limbs of company Y, and you are used to all this.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130762.png"
                }
            ]
        },
        {
            "age":122,
            "events":[
                {
                    "event_id":135580,
                    "msg":"The Anglo-French submarine tunnel has been suspended indefinitely due to seawater intrusion.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135580.png"
                }
            ]
        },
        {
            "age":123,
            "events":[
                {
                    "event_id":142308,
                    "msg":"You go to a new-style French restaurant for dinner and order a Phase Fried Foie Gras.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/142308.png"
                }
            ]
        },
        {
            "age":124,
            "events":[
                {
                    "event_id":114714,
                    "msg":"With the advancement of science and technology, mankind begins to explore the back of the moon.",
                    "add_msg":"",
                    "branch_id":114719,
                    "icon":"resource\/assets\/event\/114714.png"
                },
                {
                    "event_id":114719,
                    "msg":"The sleeping interstellar observer is awakened and the whole world is watching all this.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/114719.png"
                }
            ]
        },
        {
            "age":125,
            "events":[
                {
                    "event_id":105701,
                    "msg":"You have had a bad year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":126,
            "events":[
                {
                    "event_id":105710,
                    "msg":"You have had a happy year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105710.png"
                }
            ]
        },
        {
            "age":127,
            "events":[
                {
                    "event_id":105710,
                    "msg":"You have had a happy year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105710.png"
                }
            ]
        },
        {
            "age":128,
            "events":[
                {
                    "event_id":135530,
                    "msg":"Newly marketed mobile phones with replaceable batteries are highly sought after.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135530.png"
                }
            ]
        },
        {
            "age":129,
            "events":[
                {
                    "event_id":135060,
                    "msg":"The global economy soars and the quality of your life improves.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135060.png"
                }
            ]
        },
        {
            "age":130,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":131,
            "events":[
                {
                    "event_id":135490,
                    "msg":"The technology of using carbon dioxide to synthesize starch has been put into production.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135490.png"
                }
            ]
        },
        {
            "age":132,
            "events":[
                {
                    "event_id":105710,
                    "msg":"You have had a happy year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105710.png"
                }
            ]
        },
        {
            "age":133,
            "events":[
                {
                    "event_id":130000,
                    "msg":"You are bitten by a snake.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130000.png"
                }
            ]
        },
        {
            "age":134,
            "events":[
                {
                    "event_id":142401,
                    "msg":"You stumble and fall.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/142401.png"
                }
            ]
        },
        {
            "age":135,
            "events":[
                {
                    "event_id":135080,
                    "msg":"You feel that extreme weather is getting more and more frequent.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135080.png"
                }
            ]
        },
        {
            "age":136,
            "events":[
                {
                    "event_id":130759,
                    "msg":"The solar flares erupted, causing the paralysis of mechanical limbs all over the world.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/130759.png"
                }
            ]
        },
        {
            "age":137,
            "events":[
                {
                    "event_id":105701,
                    "msg":"You have had a bad year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":138,
            "events":[
                {
                    "event_id":135540,
                    "msg":"The last produced banknote enters the museum, and banknotes officially die out.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135540.png"
                }
            ]
        },
        {
            "age":139,
            "events":[
                {
                    "event_id":135070,
                    "msg":"The global economic depression makes life more difficult.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135070.png"
                }
            ]
        },
        {
            "age":140,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":141,
            "events":[
                {
                    "event_id":105701,
                    "msg":"You have had a bad year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":142,
            "events":[
                {
                    "event_id":135390,
                    "msg":"Extreme climates occur frequently all over the world.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135390.png"
                }
            ]
        },
        {
            "age":143,
            "events":[
                {
                    "event_id":135560,
                    "msg":"40% of the ocean has been covered by rubbish.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135560.png"
                }
            ]
        },
        {
            "age":144,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":145,
            "events":[
                {
                    "event_id":105710,
                    "msg":"You have had a happy year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105710.png"
                }
            ]
        },
        {
            "age":146,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":147,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":148,
            "events":[
                {
                    "event_id":135470,
                    "msg":"Large-scale demonstrations break out all over the world.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/135470.png"
                }
            ]
        },
        {
            "age":149,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":150,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":151,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":152,
            "events":[
                {
                    "event_id":142000,
                    "msg":"For the first time, humans have discovered the planet Pandora where aliens exist.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/142000.png"
                }
            ]
        },
        {
            "age":153,
            "events":[
                {
                    "event_id":105700,
                    "msg":"You have had a dull year.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/105700.png"
                }
            ]
        },
        {
            "age":154,
            "events":[
                {
                    "event_id":142409,
                    "msg":"There are no familiar faces in your life.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/142409.png"
                }
            ]
        },
        {
            "age":155,
            "events":[
                {
                    "event_id":142408,
                    "msg":"You haven't experienced the feeling of communicating with people for a long time.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/142408.png"
                }
            ]
        },
        {
            "age":156,
            "events":[
                {
                    "event_id":130060,
                    "msg":"You choke to death by water.",
                    "add_msg":"",
                    "branch_id":100000,
                    "icon":"resource\/assets\/event\/130060.png"
                },
                {
                    "event_id":100000,
                    "msg":"Life end.You need to reborn now.",
                    "add_msg":"",
                    "branch_id":0,
                    "icon":"resource\/assets\/event\/100000.png"
                }
            ]
        }
    ]
}
```

### 7.4 部分字段的解码处理

**编码规则**：将字符串按照字符char进行拆解，返回每个char对应的code数组。

以章节7.3 - LifeMemorial合约下编号1372的NFT的metadata数据为例：

**示范字段** - *image*

**编码后的raw data:**
```
[104,116,116,112,115,58,47,47,114,101,98,111,114,110,45,97,112,112,104,101,99,111,46,110,101,120,116,121,112,101,46,102,105,110,97,110,99,101,47,47,114,101,115,111,117,114,99,101,47,97,115,115,101,116,115,47,110,102,116,47,77,46,112,110,103]
```

**解码后的data：**

```
https://reborn-appheco.nextype.finance//resource/assets/nft/M.png
```

解码参考code：
```JS
// 实现代码JS
const charCodes = [104,116,116,112,115,58,47,47,114,101,98,111,114,110,45,97,112,112,104,101,99,111,46,110,101,120,116,121,112,101,46,102,105,110,97,110,99,101,47,47,114,101,115,111,117,114,99,101,47,97,115,115,101,116,115,47,110,102,116,47,77,46,112,110,103];
const decodedStr = String.fromCharCode.apply(String, charCodes);
```
