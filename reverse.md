## 注意char 要傳的是array 的記憶體位置 因為接收端為 pointer
```cpp
#include <iostream>
using namespace std;
#include <vector>
#include <algorithm>
#include <string>
int main() {
	
	/*vector <int> v;
	int a = 0;

	
	for (int i = 0; i < 10; i++) {
		v.push_back(a);
		a++;
	}
	reverse(v.begin(), v.end());

	for (int i = 0; i < 10; i++) {
		cout << v[i] << ' ';
	}*/


	//reverse string
	//string s;
	//cin >> s;
	//reverse(s.begin(), s.end());
	//cout << s << endl;


	//reverse char
	char b[20];
	cin >> b;
	int tmp = strlen(b);
	reverse(b, b+tmp);
	cout << b;

	return 0;
}
```
