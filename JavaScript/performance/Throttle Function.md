# Throttle Function
控制一個 function 被連續呼叫時，只會在目前時間到達特定的時間才會被執行，而非每次呼叫就立刻執行
```Javascript
function throttle(fn, wait) {
	let inThrottle = false; // 是否開始 throttle
	let timeoutId = null; // 紀錄 setTimeout callback function id
	let lastTime = null; // 上一次 fn 執行的時間
	
	return function() {
    	const context = this;
		const args = arguments;
		
		if (!inThrottle) {
			fn.apply(context, args);
			lastTime = Date.now(); // fn 執行的時間
			inThrottle = true;
		} else {
			// 清除上一次的 setTimeout function
			clearTimeout(timeoutId);
		  
			// 重新建立新的 setTimeout function
			timeoutId = setTimeout(function() {
			// 如果目前時間距離上一次 fn 執行的時間大於 wait，則再次執行 fn，並重新紀錄 lastTime
				if (Date.now() - lastTime >= wait) {
					fn.apply(context, args);
					lastTime = Date.now();
				}
			// 如果 wait - (Date.now() - lastTime) 小於 0
			// 則立刻執行 setTimeout 裡的 callback function
			// 如果 wait - (Date.now() - lastTime) 大於 0
			// 則以 wait - (Date.now() - lastTime) 的時間做為 setTimeout 執行 callback function 的時間
			}, Math.max(wait - (Date.now() - lastTime), 0));
		}
  	};
}
```

## 範例
```Javascript
// 當連續觸發 scroll event 時，printOne function 不會每次 scroll 都執行，而是每 1 秒執行一次 printOne function

const printOneFn = function() {
	console.log(1)
}

window.addEventListener('scroll', throttle(printOneFn, 1000))
```