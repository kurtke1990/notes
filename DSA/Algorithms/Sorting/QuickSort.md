# Quick Sort

## 原理

在未排序的 array 挑選一個 pivot 進行比較，並分類成小於 pivot 與大於 pivot 的兩個部分，接著使用遞迴方式將這兩部分再次做一樣的步驟，直到 array 從小到大排序。

此演算法不是穩定的，因為相同值的 element 在輸入前與輸出後，出現順序可能會被改變。

## 複雜度與穩定性

| 時間複雜度(最好) | 時間複雜度(最壞) | 時間複雜度(平均) | 空間複雜度 | 穩定性 |
| ---------------- | ---------------- | ---------------- | ---------- | ------ |
| O(nlogn)             | O(n^2)           | O(nlogn)           | O(nlogn)       | 不穩定   |

## 圖解
![QuickSort](/images/QuickSort.gif)

## 程式碼
```java
import java.util.Arrays;

/*
 * 原理: 在未排序的 array 挑選一個 pivot 進行比較，並分類成小於 pivot 與大於 pivot 的兩個部分
 * 接著使用遞迴方式將這兩部分再次做一樣的步驟，直到 array 從小到大排序。
 * 此演算法不是穩定的，因為相同值的 element 在輸入前與輸出後，出現順序可能會被改變。
 * 
 * 時間複雜度: O(nlogn)
 * 空間複雜度: O(nlogn)
 */
public class QuickSort {
	public static void main(String[] args) {
		int[] data = { 23, 25, 30, 9, -30, 30, 16, 21, -49 };
		sort(data);
		System.out.println("結果: " + Arrays.toString(data));
	}

	public static void sort(int[] data) {
		partition(data, 0, data.length - 1);
	}

	private static void partition(int[] data, int start, int end) {
		if (start < end) {
			int pivot = data[start];
			int low = start + 1; // 因為以第一個值為 pivot，所以 low 設定 start + 1
			int high = end;
			while (true) {
				/*
				 * 當 low 值小於 pivot 表示 low 值所在位置為 pivot 的左邊
				 * 
				 * 因此無須換位 low index 向上遞增
				 */
				while (low < end && data[low] < pivot) {
					low++;
				}

				/*
				 * 當 high 值大於 pivot 表示 high 值所在位置為 pivot 的右邊
				 * 
				 * 因此無須換位 high index 向下遞減
				 */
				while (high > start && data[high] > pivot) {
					high--;
				}

				/*
				 * 當發生 high 值有比 pivot 小 且 low 值比 pivot 大的情況，則做交換
				 */
				if (low < high) {
					swap(data, low, high);
				} else {
					break;
				}
			}

			// 把 pivot 值放到 high 遞減後最終位置
			swap(data, start, high);

			// 遞迴比 pivot 小的部分
			partition(data, start, high - 1);

			// 遞迴比 pivot 大的部分
			partition(data, high + 1, end);
		}
	}

	private static void swap(int[] data, int i, int j) {
		int temp = data[i];
		data[i] = data[j];
		data[j] = temp;
		System.out.println(Arrays.toString(data));
	}
}
```

