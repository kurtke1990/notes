# constructor()
1. 必須要有 super()
	1. 因為 component 使用 class 方式建立，需要 extends React.Component，所以必須要有
	2. 若 constructor 有傳入 props 的話，super 也必須傳入
	3. **必須在 this 之前宣告**，若不先宣告，會無法取得 **this.props**
2. 如果不用初始化 state 或是 method bind this 的動作，就不用實作
3. 不要在此呼叫 setState()，直接使用 ```this.state = { K: V }``` 的方式，初始化資料
4. 不要在此做有 [side-effect](/其他筆記/side-effect.md) 的操作，應在componentDidMount()