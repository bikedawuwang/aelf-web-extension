# API Reference

通过提供的API方法，你可以快速便捷的进行链上的一些操作，如转账，查询等操作。
而且我们提供了不同的调用方式，我们通过 GET_ADDRESS 为例：

1. aelf.< method name > 

```javascript

    aelf.getAddress({
        appName: 'test'
    }, (error, result) => {
        console.log('>>>>>>>>>>>>>>>>>>>', result);
    });

    // result = {
    //     ...,
    //     addressList: [
    //         {
    //             address: '...',
    //             name: '...',
    //             publicKey: {
    //                 x: '...',
    //                 y: '...'
    //             }
    //         }
    //     ]
    // }

```

2. window.NightElf.api({appName. < method name >})

```javascript
    window.NightElf.api({
        appName: param.appName,
        method: 'GET_ADDRESS'
    }).then(result => {
       console.log('>>>>>>>>>>>>>>>>>>>', result);
    });
```

两种方法获取的值是相同的，但是我们更推荐你使用第一种方式。