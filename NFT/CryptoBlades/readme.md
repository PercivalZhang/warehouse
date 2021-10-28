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

## 5. 关键合约方法
### 5.1 通用方法
以下的方法，是上述三个NFT合约（character/weapon/shield）都通用的方法。

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

> **备注：**本项目中的tokenURI返回都为空，忽略该方法。
---
**get**(*int tokenId*) - 获取目标NFT的详情

**输入参数**
> tokenId: token编号

**返回值**
> 结构体，包含了NFT的详细信息
---
**getTrait**(*int tokenId*) - 获取目标NFT的元素属性

**输入参数**
> tokenId: token编号

**返回值**
> 整形int，NFT具备的元素属性，可以是以下5种元素中的一个（0:Fire火 | 1:Earth土 ｜ 2:Lightning闪电 ｜ 3:Water水｜ 4:PWT非元素）

### 5.2 Weapon/Shield通用方法
Weapon和Shield都隶属于装备，因此除了装备属性多少不同外，合约大部分相同，该章节列取了两个合约中都通用的方法。

**getStatPattern**(*int tokenId*) - 获取目标装备的状态模式Code

**输入参数**
> tokenId: token编号

**返回值**
> 整形int， NFT Token的状态模式code，该code用于查询装备附加属性对应的元素trait类别
---
**getStat1Trait**(*int statPattern*) - 获取目标装备附加属性1的元素trait类型

**getStat2Trait**(*int statPattern*) - 获取目标装备附加属性2的元素trait类型

**getStat3Trait**(*int statPattern*) - 获取目标装备附加属性3的元素trait类型

**输入参数**
> statPattern: token的状态模式code，由**getStatPattern**(*int tokenId*) 方法获取

**返回值**
> 整形int， NFT Token的附加属性的元素trait类型，可以是以下5种元素中的一个（0:Fire火 | 1:Earth土 ｜ 2:Lightning闪电 ｜ 3:Water水 ｜ 4:PWT非元素）
---
**getStars**(*int tokenId*) - 获取目标装备的星级Code

**输入参数**
> tokenId: token编号

**返回值**
> 整形int， NFT Token星级code，0～4对应星级1～5星
---
**getDurabilityPoints**(*int tokenId*) - 获取目标装备的耐久度

**输入参数**
> tokenId: token编号

**返回值**
> 整形int，装备耐久度

## 6 Character/Weapon/Shield详情解读

在**章节5.1**中介绍的方法*get(int tokenId）*获取NFT详情，下面将介绍本项目三种NFT的详细信息的内容。

三种NFT都具备trait元素属性，元素Code对应关系如下：
- 0 ：Fire
- 1：Earth
- 2：Lightning
- 3：Water

### 6.1 Character英雄关键信息
|      Field字段          |Type类型                       |Note备注                     |
|----------------|-------------------------------|-----------------------------|
|0(xp)|`Int`            |经验值          |
|1(level)          |`Int`            |级别，1～128     |
|2(trait)          |`Int`  |元素属性, 0-3 [0(fire) > 1(earth) > 2(lightning) > 3(water)]|

在合约代码中的*get(int tokenId）*返回全部详情字段：
```
c.xp, c.level, c.trait, c.staminaTimestamp,

getRandomCosmetic(cc.seed, 1, 13), // head

getRandomCosmetic(cc.seed, 2, 45), // arms

getRandomCosmetic(cc.seed, 3, 61), // torso

getRandomCosmetic(cc.seed, 4, 41), // legs

getRandomCosmetic(cc.seed, 5, 22), // boots

getRandomCosmetic(cc.seed, 6, 2) // race
```
解读Character详情的TS代码如下：
```
const  callbackCharacter = async (tokenId: Number, helper: ContractHelper) => {
    //获取战力值
	const  power = await  helper.callReadMethod('getPower', tokenId);
	const  characterInfo = await  helper.callReadMethod('get', tokenId);
	/**
	* return (c.xp, c.level, c.trait, c.staminaTimestamp,
			getRandomCosmetic(cc.seed, 1, 13), // head
			getRandomCosmetic(cc.seed, 2, 45), // arms
			getRandomCosmetic(cc.seed, 3, 61), // torso
			getRandomCosmetic(cc.seed, 4, 41), // legs
			getRandomCosmetic(cc.seed, 5, 22), // boots
			getRandomCosmetic(cc.seed, 6, 2) // race
		);
	*/
	const  xp = characterInfo[0]; //经验
	const  level = characterInfo[1]; //级别
	const  traitCode = characterInfo[2]; //元素特性 0:Fire火 | 1:Earth土 ｜ 2:Lightning闪电 ｜ 3:Wate水
	const  trait = getTraitFromCode(Number.parseInt(traitCode), TraitType.Character);
	logger.info(`character[${tokenId}] : Power:${power} | XP:${xp} | Level:${level} | Trait:${trait}`);
};
```
### 6.2 Weapon武器关键信息
|      Field字段          |Type类型                       |Note备注                     |
|----------------|-------------------------------|-----------------------------|
|0(_properties)|`Int`            |属性值          |
|1(_stat1)          |`Int`            |附加属性值     |
|2(_stat2)          |`Int`  |附加属性值 |
|3(_stat3)          |`Int`  |附加属性值|

在合约代码中的*get(int tokenId）*返回的全部字段：
```
uint16 _properties, uint16 _stat1, uint16 _stat2, uint16 _stat3, uint8 _level,

uint8 _blade, uint8 _crossguard, uint8 _grip, uint8 _pommel,

uint24 _burnPoints, // burn points.. got stack limits so i put them together

uint24 _bonusPower // bonus power
```

每件武器可以最多附加三种元素/非元素的属性，每种元素有对应不同的属性，其对应关系如下：
* 0: Fire火 >Strength力量
* 1: Earth土 > Dexterity敏捷
* 2: Lightning光 > Charm魅力
* 3: Water水 > Intelligence智力
* 4: traitless非元素 > 没有对应的属性类型

而武器本身的星级决定了该武器可以附加的属性的数目。
具体规则如下：
* 3星和3星以下，只能有1个附加的属性
* 4星，有2个附加属性
* 5星，有3个附加属性

解读Weapon详情的TS代码如下：
```
const  callbackWeapon = async (tokenId: Number, helper: ContractHelper) => {
	//星级1～5星，code： 0～4
	const  starts = await  helper.callReadMethod('getStars', tokenId);
	//获取本身元素属性（0:Fire火 | 1:Earth土 ｜ 2:Lightning闪电 ｜ 3:Wate水）
	const  traitCode = await  helper.callReadMethod('getTrait', tokenId);
	const  trait = getTraitFromCode(Number.parseInt(traitCode), TraitType.Equipment);
	//获取当前耐久度，最大耐久度20
	const  durabilityPoints = await  helper.callReadMethod('getDurabilityPoints', tokenId);
	logger.info(`weapon[${tokenId}] : Stars(${starts}) | Trait(${trait}) | DurabilityPoints(${durabilityPoints})`);
	const  details = await  helper.callReadMethod('get', tokenId);
	/**
	* uint16 _properties, uint16 _stat1, uint16 _stat2, uint16 _stat3, uint8 _level,
	uint8 _blade, uint8 _crossguard, uint8 _grip, uint8 _pommel,
	uint24 _burnPoints, // burn points.. got stack limits so i put them together
	uint24 _bonusPower // bonus power
	*/
	// console.log(details);
	/**
		* 武器最大可以有3个额外属性
		* stat1/stat2/stat3
		* 每个属性可以是四种元素属性中一种（0:Fire火 | 1:Earth土 ｜ 2:Lightning光 ｜ 3:Wate水）
		* 也可以是非元素属性，即traitless（4）
		* Fire火对应是strength
		* Earth土对应是dexterity
		* Lightning光对应是Charm
		* Water水对应是Intelligence
		*
		* weapon的星级(1~5星)决定了其可以附加额外属性的数量
		* 规则：
		* 3星和3星以下，只能有1个附加的属性
		* 4星，有2个附加属性
		* 5星，有3个附加属性
	*/
	const  statPattern = await  helper.callReadMethod('getStatPattern', tokenId);
	const  stat1TraitCode = await  helper.callReadMethod('getStat1Trait', statPattern);
	const  stat1Trait = getTraitFromCode(Number.parseInt(stat1TraitCode), TraitType.State);
	const  stat2TraitCode = await  helper.callReadMethod('getStat2Trait', statPattern);
	const  stat2Trait = getTraitFromCode(Number.parseInt(stat2TraitCode), TraitType.State);
	const  stat3TraitCode = await  helper.callReadMethod('getStat3Trait', statPattern);
	const  stat3Trait = getTraitFromCode(Number.parseInt(stat3TraitCode), TraitType.State);
	logger.info(
	`weapon[${tokenId}] : Stat1(${stat1Trait}:${details._stat1}) / Stat2(${stat2Trait}:${details._stat2}) / Stat3(${stat3Trait}:${details._stat3})`,
	);
};
```

### 6.3 Shield盾牌关键信息

|      Field字段          |Type类型                       |Note备注                     |
|----------------|-------------------------------|-----------------------------|
|0(_properties)|`Int`            |属性值          |
|1(_stat1)          |`Int`            |附加属性值，（0:Fire火 / 1:Earth土 / 2:Lightning光 / 3:Water水 / 4:traitless无元素属性）     |
|2(_stat2)          |`Int`  |附加属性值，（0:Fire火 / 1:Earth土 / 2:Lightning光 / 3:Water水 / 4:traitless无元素属性） |
|3(_stat3)          |`Int`  |附加属性值，（0:Fire火 / 1:Earth土 / 2:Lightning光 / 3:Water水 / 4:traitless无元素属性）|
在合约代码中的*get(int tokenId）*返回的详情全部字段：
```
uint16 _properties, uint16 _stat1, uint16 _stat2, uint16 _stat3
```
每个盾牌可以最多附加三种元素/非元素的属性，每种元素有对应不同的属性，其对应关系如下：
* 0: Fire火 >Strength力量
* 1: Earth土 > Dexterity敏捷
* 2: Lightning光 > Charm魅力
* 3: Water水 > Intelligence智力
* 4: traitless非元素 > 没有对应的属性类型

而盾牌本身的星级决定了该武器可以附加的属性的数目。
具体规则如下：
* 3星和3星以下，只能有1个附加的属性
* 4星，有2个附加属性
* 5星，有3个附加属性

解读Shield详情的TS代码如下：
```
const  callbackShield = async (tokenId: Number, helper: ContractHelper) => {

	//星级1～5星，code： 0～4
	const  starts = await  helper.callReadMethod('getStars', tokenId);
	//获取本身元素属性code（0:Fire火 | 1:Earth土 ｜ 2:Lightning闪电 ｜ 3:Wate水）
	const  traitCode = await  helper.callReadMethod('getTrait', tokenId);
	const  trait = getTraitFromCode(Number.parseInt(traitCode), TraitType.Equipment);
	//获取当前耐久度，最大耐久度20
	const  durabilityPoints = await  helper.callReadMethod('getDurabilityPoints', tokenId);
	logger.info(`shield[${tokenId}] : Stars(${starts}) | Trait(${trait}) | DurabilityPoints(${durabilityPoints})`);
	const  details = await  helper.callReadMethod('get', tokenId);
	/**
		* uint16 _properties, uint16 _stat1, uint16 _stat2, uint16 _stat3
	*/
	// console.log(details);
	/**
		* 盾牌可以附加3个额外属性
		* stat1/stat2/stat3
		* 每个属性可以是四种元素属性中一种（0:Fire火 | 1:Earth土 ｜ 2:Lightning光 ｜ 3:Wate水）
		* 也可以是非元素属性，即traitless（4）
		* Fire火对应是strength
		* Earth土对应是dexterity
		* Lightning光对应是Charm
		* Water水对应是Intelligence
		*
		* 盾牌的星级(1~5星)决定了其可以附加额外属性的数量
		* 规则：
		* 3星和3星以下，只能有1个附加的属性
		* 4星，有2个附加属性
		* 5星，有3个附加属性
	*/
	const  statPattern = await  helper.callReadMethod('getStatPattern', tokenId);
	//获取附加属性1对应的元素code
	const  stat1TraitCode = await  helper.callReadMethod('getStat1Trait', statPattern);
	const  stat1Trait = getTraitFromCode(Number.parseInt(stat1TraitCode), TraitType.State);
	const  stat2TraitCode = await  helper.callReadMethod('getStat2Trait', statPattern);
	const  stat2Trait = getTraitFromCode(Number.parseInt(stat2TraitCode), TraitType.State);
	const  stat3TraitCode = await  helper.callReadMethod('getStat3Trait', statPattern);
	const  stat3Trait = getTraitFromCode(Number.parseInt(stat3TraitCode), TraitType.State);
	logger.info(
	`shield[${tokenId}] : Stat1(${stat1Trait}:${details._stat1}) / Stat2(${stat2Trait}:${details._stat2}) / Stat3(${stat3Trait}:${details._stat3})`,
	);
};
```