


`memset` 是一个C/C++标准库函数，用于将一块内存区域的内容设置为指定的值。它通常用于初始化数组或结构体等数据结构。以下是 `memset` 的基本用法及其参数说明：

```cpp
void *memset(void *str, int c, size_t n);
```

**使用示例**
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



<!--stackedit_data:
eyJoaXN0b3J5IjpbMjAwMTQxMTA3MCwxNTYxMTQzMjQ4XX0=
-->