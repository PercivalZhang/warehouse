# CryptoBlades NFT分析

## 1. 官网

https://app.cryptoblades.io/

## 2. 区块链网络
**HECO**

## 3. NFT
该项目目前需要支持的NFT包括如下三种：
- **Character**英雄
-- 合约地址：[0xF6092CDEaabd02069cB56E2b770367AAcf49dfba](https://hecoinfo.com/address/0xF6092CDEaabd02069cB56E2b770367AAcf49dfba#readProxyContract)
- **Weapon**武器
-- 合约地址：[0xa0f254436E43239D2B3947A9D590C495738B6A4C](https://hecoinfo.com/address/0xa0f254436E43239D2B3947A9D590C495738B6A4C#readProxyContract)
- **Shield**盾牌
-- 合约地址：[0xb4eD70aC5B00ca0fd9526089489979e116E45ec0](https://hecoinfo.com/address/0xb4eD70aC5B00ca0fd9526089489979e116E45ec0#readProxyContract)


## 4. ABI文件：
[character.json](https://github.com/PercivalZhang/warehouse/blob/main/NFT/PlatoFarm/plato.nft.json)
[weapon.json](https://github.com/PercivalZhang/warehouse/blob/main/NFT/PlatoFarm/plato.nft.json)
[shield.json](https://github.com/PercivalZhang/warehouse/blob/main/NFT/PlatoFarm/plato.nft.json)

## 6. 关键合约方法
### 6.1 通用方法
以下的方法，是上述三个NFT合约（character/weapon/shield）都通用的方法。

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

> **备注：**本项目中的tokenURI返回都为空，忽略该方法。

### 6.2 Weapon/Shield通用方法
Weapon和Shield都隶属于装备，因此除了装备属性多少不同外，合约大部分相同，该章节列取了两个合约中都通用的方法。

**getStars**(*int tokenId*) - 获取目标装备的星级Code

**输入参数**
> tokenId: token编号

**返回值**
> 整形int， NFT Token星级code，0～4对应星级1～5星
---


**getTrait**(*int tokenId*) - 获取目标装备的元素属性

 
**输入参数**
> tokenId: token编号

**返回值**
> 整形int，装备具备元素属性，可以是以下4种元素中的一个（0:Fire火 | 1:Earth土 ｜ 2:Lightning闪电 ｜ 3:Wate水）