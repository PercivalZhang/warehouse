# PlatoFarm NFT分析

## 2. 官网

https://www.platofarm.game/index

## 3. 区块链网络
**HECO**

## 4. NFT合约
0x892E674dA88F5BBc11886f10a072286FEE8B33Df [点击查看](https://hecoinfo.com/address/0x892E674dA88F5BBc11886f10a072286FEE8B33Df#code)


## 5. ABI文件：
[plato.nft.json](https://github.com/PercivalZhang/warehouse/blob/main/NFT/PlatoFarm/plato.nft.json)

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


**tokenURI**(*int tokenId*) - 获取指定Id的token对应的URI

 
**输入参数**
> tokenId: token编号

**返回值**
> token URI, 字符串类型

> token URI = https://resource.platofarm.game/nft/ + tokenId, eg: https://resource.platofarm.game/nft/100000059241


## 7. NFT种类说明

tokenId的前三位数字用于区别NFT token所属的分类：

比如：
- 100 农田
- 101 果地
- 102 饲料机

具体编号参见文件：[ID规则文件](https://github.com/PercivalZhang/warehouse/blob/main/NFT/PlatoFarm/ID.rules.xlsx)
