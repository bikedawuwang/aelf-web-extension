# Examples

如何使用 NightELF 开发你的 Web application ?

## Let's take a look at the flow

your Dapp -> Connect -> aelf-sdk.js -> sign

## 如何通过 NightELF 在 AELF 上发送交易

```JavaScript
    // 在这之前你需要确认 NightELF 已经注入到 window
     const aelf = new window.NightElf.AElf({
        // Enter your test address in this location
        httpProvider: [
            'http://192.168.197.56:8101/chain',
            [{
                name: 'Accept',
                value: 'text/plain;v=1.0'
            }]
        ],
        appName
    });

    // 我们还需要确认我们已经可以正常连接到链
    aelf.chain.getChainInformation((error, result) => {
        console.log('>>>>>>>>>>>>> getChainInformation >>>>>>>>>>>>>');
        console.log(error, result);
    });


```