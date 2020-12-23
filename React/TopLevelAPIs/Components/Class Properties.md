# Class Properties
## defaultProps
1. 只有當 props 值為 undefined 時，才會使用 defaultProps，若 props 值為 null，則以 null 為主
## displayName
1. 通常用以 debugging 的訊息提示，且不需特別設定，displayName 會以 function 或 class 的名字
2. 使用時機通常是要客製化 debugging 的訊息提示，或是使用 HOC 時，參考[連結](https://reactjs.org/docs/higher-order-components.html#convention-wrap-the-display-name-for-easy-debugging)