```cpp
#include <iostream>
using namespace std;

int main() {
	char a[20][20];
	cout << sizeof(a);
	memset(a, 'h', sizeof(a));
	return 0;
}
```
