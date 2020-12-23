# componentWillUpdate()
1. 往後版本會被移除，若需使用，前方需要加上 **UNSAFE_**，即 UNSAFE_componentWillUpdate()
2. 依序可接收 nextProps、nextState 參數
3. 當 props 或 state 更新時，與在 render() 之前執行
4. 首次渲染不會執行
5. 不能在此執行 setState() 或是 dispatch Redux action
6. 在此做 DOM 的操作，如: 儲存 scroll 位置等，可以移到 getSnapshotBeforeUpdate()
7. 在 shouldComponentUpdate() 之後執行，若 shouldComponentUpdate() return false，則不執行