# CHECK_PERMISSION / checkPermission

```javascript
    aelf.checkPermission({
        appName: 'hzzTest',
        type: 'address', // if you did not set type, it aways get by domain.
        address: '4WBgSL2fSem9ABD4LLZBpwP8eEymVSS1AyTBCqXjt5cfxXK'
    }, (error, result) => {
        console.log('checkPermission>>>>>>>>>>>>>>>>>', result);
    });

    // result = {
    //     ...,
    //     permissions:[
    //         {
    //             address: '...',
    //             appName: 'hzzTest',
    //             contracts: [{
    //                 chainId: 'AELF',
    //                 contractAddress: '4rkKQpsRFt1nU6weAHuJ6CfQDqo6dxruU3K3wNUFr6ZwZYc',
    //                 contractName: 'token',
    //                 description: 'token contract',
    //                 github: ''
    //             },
    //             {
    //                 chainId: 'AELF TEST',
    //                 contractAddress: 'TEST contractAddress',
    //                 contractName: 'TEST contractName',
    //                 description: 'contract description',
    //                 github: ''
    //             }],
    //             domian: 'Dapp domain'
    //         }
    //     ]
    // }
```