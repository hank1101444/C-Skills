# char
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
# int
```cpp
// CPP Program to demonstrate that we can use memset() to
// set all values as 0 or -1 for integral data types also
#include <iostream>
using namespace std;
#include <cstring>
// Driver Code
int main()
{
	int a[5];

	// all elements of A are zero
	memset(a, 0, sizeof(a));
	for (int i = 0; i < 5; i++)
		cout << a[i] << " ";
	cout << endl;

	// all elements of A are -1
	memset(a, -1, sizeof(a));
	for (int i = 0; i < 5; i++)
		cout << a[i] << " ";
	cout << endl;

	// Would not work
	memset(a, 5, sizeof(a)); // WRONG
	for (int i = 0; i < 5; i++)
		cout << a[i] << " ";
}

```
