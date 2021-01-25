## offsetHeight
1. 計算時不含 margin
2. 當直向卷軸出現時，offsetHeight = 內容高度 + padding-top + padding-bottom + border-top + border-bottom + 橫向卷軸高度 (若無則省略)
3. 當直向卷軸未出現時，offsetHeight = 內容高度 + padding-top + padding-bottom + border-top + border-bottom + 橫向卷軸高度 (若無則省略)

## offsetWidth
1. 計算時不含 margin
2. 當直向卷軸出現時，offsetWidth = 內容寬度 + padding-left + padding-right + border-left + border-right + 直向卷軸高度 (若無則省略)
3. 當直向卷軸未出現時，offsetWidth = 內容寬度 + padding-left + padding-right + border-left + border-right + 直向卷軸高度 (若無則省略)

## 圖解
![offsetHeight&offsetWidth](/images/offsetHeight&offsetWidth.png)