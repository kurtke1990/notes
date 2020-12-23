# getSnapshotBeforeUpdate()
1. render() 之後執行
2. 可接收 prevProps、prevState
3. 必須要 return snapshot value 或 null
	1. snapshot value
		1. 任何值都可以
		2. 此值會在 componentDidMount() 的第 3 個 snapshot 參數接收到
	2. null
		1. 若無 snapshot value，必須要有
4. 可在此抓到 DOM 的資訊，如: scroll 位置等