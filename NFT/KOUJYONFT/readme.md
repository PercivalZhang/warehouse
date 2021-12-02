# 盲盒KOUJYONFT NFT分析

## 2. 官网

无

## 3. 区块链网络
**HECO**

## 4. NFT合约
0x360A1cE539135E90C3f40cE64D30D577896E896f [点击查看](https://hecoinfo.com/address/0x360A1cE539135E90C3f40cE64D30D577896E896f#code)


## 5. Code和ABI文件：
[sourcecode和ABI](https://hecoinfo.com/address/0x360A1cE539135E90C3f40cE64D30D577896E896f#code)

## 6. 关键合约方法
### 6.1 通用方法
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

**baseURI**() - 获取NFT的URI链接前半部分

**返回值**
> 字符串string， NFT资源链接前半部分

> eg: https://nft.nextype.finance/nft/16/

---

**tokenURI**(*int tokenId*) - 获取指定Id的token对应的URI

 
**输入参数**
> tokenId: token编号

**返回值**
> token URI, 字符串类型

> eg: https://nft.nextype.finance/nft/16/1


## 7. NFT Token URI说明
该合约NFT的tokenURI由baseURI + tokenId拼接而成，比如tokenId为1的NFT，其tokenURI为：https://nft.nextype.finance/nft/16/1

通过NFT的tokenURI，可以获取NFT的metadata元数据，用于UI展示。

比如tokenId为1的NFT，通过tokenURI获取的metadata数据如下：
```
{
    "image": "https://gateway.pinata.cloud/ipfs/QmbQdZr6P52NopuCcxYNPvx3g269BfT5u43AJPGMSPoFM8",
    "image_small": "https://gateway.pinata.cloud/ipfs/QmcVxkjfUZXWJ32X13Sy8z7nbzB3TxdTZVmSgmiiUSDyvF",
    "name": "Huobi KOUJYO",
    "description": "Huobi Wallet Memorial NFT limited to 10,000 copies with special benefits in the blockchain game MiningTycoon\r\n",
    "attributes": null
}
```
