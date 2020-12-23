# Instance Properties
## props
1. 從外面傳進 component
2. props.children 用於 component 內有不同的結構時，將其傳入，類似於 slots
## state
1. 必須為一個 plain JavaScript object
2. 不要直接對 this.state 做操作，必須透過 setState() 去改變 state