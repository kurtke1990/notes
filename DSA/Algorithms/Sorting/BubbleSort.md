# Bubble Sort

## 原理

每次重覆比較相鄰元素，若目前元素大於下一個元素，則交換位置，直到所有元素由小到大排序完成。

## 複雜度與穩定性

| 時間複雜度(最好) | 時間複雜度(最壞) | 時間複雜度(平均) | 空間複雜度 | 穩定性 |
| ---------------- | ---------------- | ---------------- | ---------- | ------ |
| O(n)             | O(n^2)           | O(n^2)           | O(1)       | 穩定   |

## 圖解
![BubbleSort](/images/BubbleSort.gif)

## 程式碼
```java
import java.util.Arrays;

/*
 * 原理: 檢查 array 中每一個 element，若目前的 element 大於下一個 element，則交換位置
 * 時間複雜度: O(n^2)
 * 空間複雜度: O(1)
 */
public class BubbleSorting {
	public static void main(String[] args) {
		int[] data = { 23, 25, 30, 9, -30, 30, 16, 21, -49 };

		for (int i = 0; i < data.length - 1; i++) {
			// 因為經過每 i 次循環後，較大值都會往後排列
			// 所以 j 只需檢查到 data.length - 1 - i 個數即可
			for (int j = 0; j < data.length - 1 - i; j++) {
				if (data[j] > data[j + 1]) {
					swap(data, j, j + 1);
				}
			}
		}

		System.out.println("結果: " + Arrays.toString(data));
	}

	private static void swap(int[] data, int i, int j) {
		int temp = data[i];
		data[i] = data[j];
		data[j] = temp;
		System.out.println(Arrays.toString(data));
	}
}
```

