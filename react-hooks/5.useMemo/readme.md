### 在子组件不需要父组件的值和函数的情况下，只需要使用 memo 函数包裹子组件即可。

### 而在使用值和函数的情况，需要考虑有没有函数传递给子组件使用 useCallback，值有没有所依赖的依赖项而使用 useMemo,而不是盲目使用这些 hooks 等

### 只有你的应用严格遵循对象不可变, 且组件的渲染只依赖 props，state 时才可以使用 PureComponent 和 React.memo 。这里其他依赖还包括 localStorage/sessionStorage, window 属性例如 location ，如果依赖这些，则不可以使用上述优化，或者就算使用了也达不到响应式的效果。

### PureComponent, memo 二者的比较范围有区别，PureComponent 会将 props 和 state 都进行一次浅比较，而 memo 只会对 props 进行浅比较。

### 如果严格按照对象不可变原则进行编码，大部分场景还是建议所有组件都使用 PureComponent 或 memo 进行优化的，这两者在生产环境下使用率极高，可以放心使用。
