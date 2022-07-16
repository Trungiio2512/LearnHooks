### useState

### dùng khi nào

khi bạn đang có một dữ liệu và bạn đang hiển thị dữ liệu đó ra giao diện người dùng rồi khi các bạn muốn dữ liệu đó được thay đổi thì giao diện đó được cập nhật lại

### cách sử dụng

import {useState} from 'react'

function Component () {
const [state, setState] = useState(initState)
...
}

### lưu ý

1.Component luôn được gọi lại mỗi khi set state
2.Initial state chỉ dùng cho lần đầu
3.Initial state với callback
-- chỉ nhận (giá trị) cái mà callback return về
-- vd: initState = 0

    return(
        <div>
            <h1>{state}</h1>
            <button onClick = {() => handleCount}>
        </div>
    )
    (+)
        const hanldeCount = () => {
            setState(state + 1)
            setState(state + 1)
            setState(state + 1)
        }

        => chỉ trả về với state = 1
    (+)
        const hanldeCount = () => {
            setState(prev => prev + 1);
            setState(prev => prev + 1);
            setState(prev => prev + 1);
        }

        => trả về với state = 3

4.setState với callback
-- tham số trong call back sẽ không tham chiếu tới state trước đó nhưng tham sô là state trước đó
-- vd:

    function Component () {
        const [state, setState] = useState(initState)
         const hanldeCount = () => {
            setState(prev => prev + 1);

        }
        return(
        <div>
            <h1>{state}</h1>
            <button onClick = {() => handleCount}>
        </div>
        )
    }

    (+) với initState = 10
    => cứ mỗi lần set state => Component re-render => lại log initState là 10 mặc dù state thay đổi (tăng lên) giao diện thay đổi

    (+) initState = () => { return 10 }
    => cứ mỗi lần set state => Component re-render => không gọi lại initState là 10

5.setState là thay thế giá trị state mới
