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

    // 对Dapp进行授权 如果需要使用 Transfer 进行交易 我们需要对Dapp 授权 MultiToken 合约。
    // 到这一步 NightELF 会出现弹窗提示登录，如果当前NightELF 中没有任何 keypair 则会提醒你添加 keypair 到 NightELF
    // 当已经拥有 keypair 并且通过授权，你可以到 NightELF 内的应用管理选项查看授权的详细信息

    aelf.login({
        appName: 'test', // 你的Dapp名称
        chainId: 'AELF',
        payload: {
            method: 'LOGIN', 
            contracts: [{
                chainId: 'AELF',
                contractAddress: '4rkKQpsRFt1nU6weAHuJ6CfQDqo6dxruU3K3wNUFr6ZwZYc',
                contractName: 'MultiToken',
                description: 'MultiToken Contract',
                github: ''
            }]
        }
    }, (error, result) => {
        console.log('login>>>>>>>>>>>>>>>>>>', result);
    });

    // 注意 wallet.address 为你已授权的账户地址
    const wallet = {
        address: '2J...du'
    }

    // multitokenContract 用来存放合约方法
    let multitokenContract = null;

    aelf.chain.contractAtAsync(
        '4rkKQpsRFt1nU6weAHuJ6CfQDqo6dxruU3K3wNUFr6ZwZYc',
        wallet,
        (error, result) => {
            console.log('>>>>>>>>>>>>> contractAtAsync >>>>>>>>>>>>>');
            console.log(error, result);
            multitokenContract = result;
        }
    );

    const payload = {
        to: '6W...FH' // 要交易给谁
        symbol: 'ELF' // 代币类型
        amount: 100  // 数量
    }

    // 交易可以通过 result 中返回的 TransactionId 进行查询
    multitokenContract.Transfer(payload, (error, result) => {
        console.log('>>>>>>>>>>>>> Transfer >>>>>>>>>>>>>');
        console.log(result);
    })

```

这样就通过 NightELF 就进行了一次 Transfer 转账。

## 如何知道哪个账户对你的Dapp进行了授权

如果当前 NightELF 中的 keypair 有对你进行授权的话。
你可以通过 ```aelf.login``` 的返回值查询到哪个账户对你的Dapp进行了授权  