# BUDO2 NFT分析

## 1. 官网

[https://budo2.com](https://budo2.com)

## 2. 区块链网络
**HECO**

## 3. NFT
该项目是卡牌游戏，目前主要NFT Token就是GameCard：
- **GameCard**卡牌
-- 合约地址：[0x0d58C0b5bfae8437337303203555049c03f49DfA](https://hecoinfo.com/address/0x0d58C0b5bfae8437337303203555049c03f49DfA)

> 备注： 合约代码不开源，ABI文件参见章节4。
> 
## 4. ABI文件：
[card.json](https://github.com/PercivalZhang/warehouse/blob/main/NFT/BUDO2/card.json)


## 5. 关键合约方法

**name**() - 获取NFT Token名字

---

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

**tokenURI**(*int tokenId*) - 获取指定Id的token对应的URI

**输入参数**
> tokenId: token编号

**返回值**
> token URI, 字符串类型

> **备注：**本项目中的tokenURI返回的是一个URI链接，eg：https://budo2.com/api/nft/card/4  
> 目前项目还没完全上线，因此该链接返回404，已经联系项目方，索取返回数据范例。
---

## 6. 测试代码
```
const  owner = await  cardHelper.getOwnerOf(1026);
console.log(owner); //0x20bb1Ed4f5799993500475979902DFc8dfa83dB3
//获取目标用户拥有的NFT Token数目
const  balance = await  cardHelper.balanceOf(owner);
console.log(balance);
//按照下标遍历目标用户拥有的所有NFT Token，获取其token Id
const  tokenId = await  cardHelper.tokenOfOwnerByIndex(owner, 0);
console.log(tokenId); //601
const  tokenURI = await  cardHelper.tokenURI(tokenId);
console.log(tokenURI); //https://budo2.com/api/nft/card/4
```