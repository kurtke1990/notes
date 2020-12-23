# componentDidMount()
1. 可在此做需要 DOM 完成渲染後的初始化動作
2. 適合在此做取後端資料的動作，或是事件監聽等
3. 如果在此做有做事件的監聽，需在 componentWillUnmount() 去做移除監聽的動作
4. 可在此做 setState()
5. 當 DOM 渲染需要某 element 的大小或位置時，可以在此做
6. 因為在此做 setState() 會再次執行 render()，故可能會有 performance issue，如果能在 constructor() 做初始化，則盡量選擇在 constructor() 做完