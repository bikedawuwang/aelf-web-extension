# AELF

目前 NightELF 只支持 AELF。

你可以通过以下方式连接到 AELF，通过下面这段代码，如果您查看过 AELF 官方文档就不难发现 NightELF 在使用方法上与 aelf-sdk 基本相同。

如果你想了解 ```httpProvider``` 更多的参数可以点击 [JS SDK](https://docs.aelf.io/v/dev/sdk-reference/js-sdk) 查看

```javascript
    const aelf = new window.NightElf.AElf({
        // Enter your test address in this location
        httpProvider: [
            'https://127.0.0.1:8000/chain', // host
            null, // timeout
            null, // user
            null, // password
            // header
            [{
                name: 'Accept',
                value: 'text/plain;v=1.0'
            }]
        ],
        appName // your Dapp name
    });
```