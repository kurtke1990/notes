# render()
1. 在 class component 中，唯一一個必須要實作的 lifecycle method
2. 執行時，會檢查 props 與 state，且 return 類型如下
	1. React Element，無論是 ```<div>``` 或 ```<MyComponent />``` 都屬於 React Element，最終會被渲染成 DOM
	2. Boolean 或 null，不會渲染成任何 DOM 結構，多數用以判斷該 component 是否要顯示
	3. String 與 number，會被渲染成 text node
	4. Portals，子元件中有不同的 DOM 結構，[範例](https://reactjs.org/docs/portals.html)
	5. Arrays 與 fragments
3. 必須是 pure function，即不可做任何 state 的改變，若在此做 setState()，會導致無窮迴圈
4. 不可在此做 browser 相關的操作，如: 監聽事件等
5. 若 shouldComponentUpdate() return false，則 render() 不會被執行