# React.memo
1. 是一個 Higher order component
2. 依序接收 component、comparison function 參數
3. 如果傳入的 component 給予相同的 props 會渲染相同的結果，則可以把此 component 放到 React.memo 中，紀錄最後一次的渲染結果，以達到重用目的，進而提升效能
4. React.memo 只會檢查 props，如果傳入的 component 有 state 或是 context，則當 state 或 context 改變時，仍然會重新渲染
5. 預設使用 shallow 比對 props，如果需要更深入的比對，則可以透過第二個參數傳入一個比對的 function，進行 props 比對