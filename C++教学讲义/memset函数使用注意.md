


`memset` 是一个C/C++标准库函数，用于将一块内存区域的内容设置为指定的值。它通常用于初始化数组或结构体等数据结构。以下是 `memset` 的基本用法及其参数说明：

```cpp
void *memset(void *str, int c, size_t n);
```

#### 使用示例
**初始化数组**
```cpp
#include <stdio.h> 
#include <string.h> 

int main() { 
	char str[50]; // 将str前10个字节设置为字符'A' 
	memset(str, 'A', 10); 
	str[10] = '\0'; // 确保字符串以null结尾 
	printf("String after memset: %s\n", str); 
	return 0; 
}
```
此代码段将 `str` 数组的前10个字节设置为字符 `'A'`，然后手动添加一个空字符 `\0` 来结束字符串，最后打印结果。

#### 初始化整型数组

需要注意的是，当使用 `memset` 对整型数组进行初始化时，由于每个字节都会被设置为目标值，所以如果目标是将整型数组的所有元素设置为0，可以这样做：

```cpp
#include <stdio.h> 
#include <string.h> 
int main() { 
	int numbers[5]; // 将numbers数组所有元素设置为0 
	memset(numbers, 0, sizeof(numbers)); 
	
	for(int i = 0; i < 5; ++i) { 
		printf("%d ", numbers[i]); 
	} 
	
	printf("\n"); 
	return 0; 
}
```

这里，`memset(numbers, 0, sizeof(numbers))` 将整个 `numbers` 数组的**每个字节**都设为 `0`，因此所有整数都被初始化为 `0`。注意，如果你尝试将非零值（例如 `-1`）通过这种方式赋给整数数组，则需要小心，因为这实际上会将每个字节设置为你指定的值，可能不会得到你预期的结果(`int`类型是32位，也就是4字节，每个字节都设置为-1后，得到的32位二进制数并不是-1对应的而二进制数)。

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwNDYyNTEzODcsMTU2MTE0MzI0OF19
-->