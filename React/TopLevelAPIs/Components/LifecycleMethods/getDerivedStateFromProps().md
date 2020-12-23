# getDerivedStateFromProps()
1. 必須被宣告為 static
2. 非常用 Lifecycle method
3. 依序接收 props, state 參數
4. 必須要 return null 或是物件
	1. 若 return 為 null，則表示不做任何更新
	2. 若 return 為物件，則此物件會合併到 state 中，且該 value 不得再被修改
	3. 若 return 為物件，有相同的 key，則 value 會被 override 且不得再被修改
5. 在 render() 執行之前被執行
6. 使用此 Lifecycle method 會導致 code 變得冗長，因此遇到以下三種情況，能利用其他方式改寫
	1. 當 props 改變來取得資料或做動畫，可使用 componentDidUpdate() 替代
	2. 當 props 改變重新計算某個資料，可使用 memoization 替代，[範例](https://reactjs.org/blog/2018/06/07/you-probably-dont-need-derived-state.html#what-about-memoization)
	3. 當 props 改變需要重置某些 state，可用 fully controlled component 或 fully uncontrolled with a key 的方式替代，[範例](https://codesandbox.io/s/6v1znlxyxn?file=/index.js)