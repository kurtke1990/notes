# componentDidUpdate()
1. 當資料發生更新時，被執行
2. 可依序接收 prevProps、prevState、snapshot 參數
3. mounting 階段(即首次渲染)不會執行
4. 可在此做 DOM 操作
5. 也可以在此做後端取資料的動作，但前提是需要判斷目前的 props 與 prevProps 是否要做
6. 也可以在此做 setState()，但前提是需要判斷目前的 props 與 prevProps 是否要做，否則會導致無窮迴圈
7. 如果 getSnapshotBeforeUpdate() 有 return 值，則在 snapshot 參數可接收
8. 如果 shouldComponentUpdate() return false，則 componentDidUpdate() 不會被執行