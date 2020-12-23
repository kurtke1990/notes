# React.PureComponent
1. 與 React.Component 差別為，React.Component 沒有實作 shouldComponentUpdate()，但 React.PureComponent 有實作，且實作內容為 props 與 state 的 shallow comparison，因此當 props 與 state 與前次的 props 與 state 相同，則不會再次執行 render()，進而提升效能
2. 因為是 shallow comparison，故不適合有深層資料結構的 component 作為 PureComponent，如果有深層資料結構的 PureComponent，那麼必須執行 forceUpdate() 來確保資料能更新，或是透過 immutable objects 來快速比對該深層資料結構，是否需要更新
3. 會 skip 整個 component subtree 的 props 更新