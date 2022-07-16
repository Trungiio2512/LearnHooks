### memo

- memo() => Higher Order Component (HOC)

### dùng khi nào

- dùng để ghi nhớ lại props của 1 Component để nó quyết định render lại Component đó hay không để tối ưu lại hiệu năng
  => memo giúp xử lý Component tránh việc re-render trong những tình huống không cần thiết

### nguyên lý hoạt động

- memo(component)

- memo nhận tham số là Component
- check các props của Component này sau mỗi lần có bị re-render có bị thay đổi hay không
- Component nhận vô số props. Chỉ cần ít nhậts có 1 props bị thay đổi giá trị => Component re-render.
- Ngược lại => Không cho Component re-render

### cách dùng

function Content ({state2}) {
return <h1>{state2}</h1>
}

export default memo(Content)

import {useState} from 'react'
import Content from './Content.js'

function App () {
const [state, setStaSte] = useState(10)

    return (
        <div>
            <h1>{state}</h1>
            <Content state2 = {state2}/>
            <button onClick= {() => setState(state + 1)}> UP </button>
            <button onClick= {() => setState(state2 + 1)}> UP2 </button>
        </div>
    )

}

### Giải thích

TH1: nếu không sử dụng memo - mỗi khi App re-render => Content cũng re-render
Th2: sử dụng memo

    (*) state thay đổi => App re-render => Content không render

    (*) state2 thay đổi => App re-render => Content re-render
