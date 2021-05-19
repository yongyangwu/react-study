### React.memo 仅检查 props 变更。如果函数组件被 React.memo 包裹，且其实现中拥有 useState 或 useContext 的 Hook，当 context 发生变化时，它仍会重新渲染

只有你的应用严格遵循对象不可变, 且组件的渲染只依赖 props，state 时才可以使用 PureComponent 和 React.memo 。这里其他依赖还包括 localStorage/sessionStorage, window 属性例如 location ，如果依赖这些，则不可以使用上述优化，或者就算使用了也达不到响应式的效果。PureComponent, memo 二者的比较范围有区别，PureComponent 会将 props 和 state 都进行一次浅比较，而 memo 只会对 props 进行浅比较。如果严格按照对象不可变原则进行编码，大部分场景还是建议所有组件都使用 PureComponent 或 memo 进行优化的，这两者在生产环境下使用率极高，可以放心使用。
