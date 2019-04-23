# GET\_CHAIN\_INFORMATION / getChainInformation

```javascript
    const aelf = new window.NightElf.AElf({
        httpProvider: 'http://192.168.199.210:5000/chain',
        appName: 'Test'
    });

    aelf.chain.getChainInformation((error, result) => {
        console.log('>>>>>>>>>>>>> connectChain >>>>>>>>>>>>>');
        console.log(error, result);
    });

    // result = {
    //     ChainId: "AELF"
    //     GenesisContractAddress: "61W3AF3Voud7cLY2mejzRuZ4WEN8mrDMioA9kZv3H8taKxF"
    // }
```

