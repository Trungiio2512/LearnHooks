### useRef - use reference

### dùng khi nào

- lưu các giá trị qua một biến tham chiếu từ bên ngoài
  -( giông với việc tạo một biến bên ngoài Component rồi dùng biến đố để gán, dùng lại, ... trong component)
  -( mỗi khi component re-render thì sẽ tạo một vùng nhớ mới và useRef sẽ dùng property current để lưu lại giá trị (tham chiếu) được gán cho property current trong component trước đó - vùng nhớ trước dó)

### cách dùng

import {useRef} from 'react'

function Component () {
const val = useRef(initRef)
...
}

1. useRef là một function
   => khi gọi useRef => object có key: current
2. có thể gán lại cho biến
3. initRef có thể là bất cứ giá trị gì

### các trường hợp hay sử dụng useRef

    - lấy giá trị, ... trong component trước đó - kết hợp với useEffect
    - lấy element dom thật trong component
