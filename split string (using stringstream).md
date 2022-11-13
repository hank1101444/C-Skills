https://home.gamer.com.tw/creationDetail.php?sn=4114818
https://www.twblogs.net/a/5edbb321c98ca1ea826e4bd4
```cpp
#include <iostream>
#include <string>
#include<sstream>
#include <vector>
using namespace std;

vector <string> split(const string &s,const char del) {
	vector <string> v;
	stringstream ss(s);
	string sp;
	// 沒有 getline(cin, ss) 要先存在 string
	while (getline(ss, sp, del))		// while 跳出條件看第一個係數 ss 繼承 istream 最後也是return eof, del 只是看說如果讀到關鍵字原要執行下一行
		v.push_back(sp);
	//if (!ss)
	//	cout << "nono" << endl;
	return v;
}

int main() {
	string s;
	getline(cin, s);
	vector <string> v = split(s, '%');
	for (int i = 0; i < v.size(); ++i)
		cout << v[i] << endl;

	return 0;
}
```
