### 1.useState 函数接收一个初始化参数 initialState,其返回值用数组解构出两个参数:state 和 setState。

### 2.在初始化渲染期间，返回的状态 (state) 与传入的第一个参数 (initialState) 值相同。

### 3.setState 函数用于更新 state。它接收一个新的 state 值并将组件的一次重新渲染加入队列。

### 4.在后续的重新渲染中，useState 返回的第一个值将始终是更新后最新的 state。

​### 5.注意: React 会确保 setState 函数的标识是稳定的，并且不会在组件重新渲染时发生变化。这就是为什么可以安全地从 useEffect 或 useCallback 的依赖列表中省略 setState。
