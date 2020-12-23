# shouldComponentUpdate()
1. 當有新的 state 或 props 時，被執行
2. 非常用 Lifecycle method
3. 可依序接收 nextProps、nextState
4. 在 render() 執行前被執行
5. 只存在效能調整時，才會出現此 lifecycle method，但可能導致出現更多問題，因此可考慮改用 [PureComponent](/React/TopLevelAPIs/Components/React.PureComponent.md)
6. 必須要 return boolean
	- return true
		後續的 lifecycle methods 才會繼續執行
	- return false
		後續的 lifecycle methods 不會執行，因此不會更新資料
7. 只有 setState() 會執行此 lifecycle method，forceUpdate() 不會