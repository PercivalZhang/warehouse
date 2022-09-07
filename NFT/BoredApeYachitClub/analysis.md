# BoredApeYachtClub (BAYC) NFT分析

## openSea Collection

https://opensea.io/collection/boredapeyachtclub

## 官网

to be continued...

## NFT合约
0xbc4ca0eda7647a8ab7c2061c2e118a18a936f13d [点击查看](https://etherscan.io/address/0xbc4ca0eda7647a8ab7c2061c2e118a18a936f13d#code)


## abi文件：
[点击bayc.json查看ABI文件内容](https://github.com/PercivalZhang/warehouse/blob/main/NFT/BoredApeYachitClub/bayc.json)

[从etherscan查看ABI](https://etherscan.io/address/0xbc4ca0eda7647a8ab7c2061c2e118a18a936f13d#code)

## 关键合约方法
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
> token URI, 字符串类型，ipfs链接

eg：  ipfs://QmeSjSinHpPnmXmspMjwiXyN6zS4E9zccariGR3jxcaWtq/7062

## NFT Token Metadata

获取到了token id后，可以通过上面的tokenURI方法获取 对应的tokenURI，该项目的tokenURI是一个ipfs链接，通过该链接完成JSON格式的元数据获取。


TokenURI获取IPFS链接 eg:  ipfs://QmeSjSinHpPnmXmspMjwiXyN6zS4E9zccariGR3jxcaWtq/7062

元数据范例：
```
{
    "image": "ipfs://QmbVg8ta5jXsHs83sSheX1RxmB6m5ctQ6cUrELb5BQnbzP",
    "attributes": [
        {
            "trait_type": "Hat",
            "value": "Spinner Hat"
        },
        {
            "trait_type": "Fur",
            "value": "Brown"
        },
        {
            "trait_type": "Mouth",
            "value": "Tongue Out"
        },
        {
            "trait_type": "Eyes",
            "value": "Sleepy"
        },
        {
            "trait_type": "Background",
            "value": "Aquamarine"
        }
    ]
}
```
