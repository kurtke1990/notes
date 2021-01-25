## clientHeight
1. 計算時不含margin、border與橫向卷軸
2. 當直向卷軸出現時，clientHeight = 內容高度 + padding-top + padding-bottom
3. 當直向卷軸未出現時，clientHeight = 內容高度 + padding-top + padding-bottom

## clientWidth
1. 計算時不含margin、border與直向卷軸
2. 當橫向卷軸出現時，clientWidth = 內容寬度 + padding-left + padding-right
3. 當橫向卷軸未出現時，clientWidth = 內容寬度 + padding-left + padding-right

## 圖解
![clientHeight&clientWidth](/images/clientHeight&clientWidth.png)