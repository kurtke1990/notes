# componentWillReceiveProps()
1. 往後版本會被移除，若需使用，前方需要加上 **UNSAFE_**，即 UNSAFE_componentWillReceiveProps()
2. 當父元件重新 render() 才會執行，即使 props 未被更新，也會執行
3. 首次渲染不會執行