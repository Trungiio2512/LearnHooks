### useEffect

### dùng khi nào

//hay dùng

1. update DOM
2. Call API
3. listener Event
4. timer

### cách dùng

import {useEffect} from 'react';

function Component () {
useEffect (callback , [deps])
...
}

callback : bắt buộc
[]: không bắt buộc
deps: không bắt buộc

### lưu ý

1. useEffect (callback)
   - callback luôn được gọi lại mỗi khi component re-render
   - callback gọi sau khi element thêm vào DOM
2. useEffect (callback, [])
   - callback gọi một lần duy nhât sau khi component được mounted
3. useEffect (callback, [deps])
   - callback được gọi lại mỗi khi deps thay đổi
4. lưu ý chung cho 3 th trên
   - callback luôn được gọi lần đầu khi component được mounted
   - cleanup function luôn được gọi trước khi component unmounted
   - cleanup function luôn được gọi trước khi callback được gọi
   - khi component được mounted, cleanup function không được gọi
