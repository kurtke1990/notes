# Debouce Function
控制一個 function 被連續呼叫時，不會馬上被執行，直到不再呼叫且達到特定時間，才會執行
```Javascript
function debounce(fn, wait) {
	let timeoutId = null; // 紀錄 setTimeout callback function id
	
	return function() {
		const context = this;
		const args = arguments;
		
		clearTimeout(timeoutId); // 清除上一次的 setTimeout function
		
		timeoutId = setTimeout(function () { // 重新建立新的 setTimeout function
			fn.apply(context, args)
		}, wait);
	};
};
```

## 範例
```Javascript
// 當觸發 scroll event 時，若連續觸發 scroll，不會執行 printOne function，必須等到 scroll 停止且等待 1 秒後才會執行

const printOneFn = function() {
	console.log(1)
}

window.addEventListener('scroll', debounce(printOneFn, 1000))
```