# GET_ADDRESS / getAddress

```javascript
    aelf.getAddress({
        appName: 'hzzTest'
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