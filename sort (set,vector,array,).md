## set
### set以自定義的型態宣告時想要排序必需要改寫此物件的 operator< 不需要寫sort
```cpp
#include<iostream>
#include<vector>
#include<set>
#include<string>
#include<algorithm>
using namespace std;
struct student {
	string name;
	int score;

};
//自定義“小於”
//bool comp(const student& a, const student& b) {
//	return a.score < b.score;
//
//}
bool operator < (const student& stu1, const student& stu2) {
	return stu1.score > stu2.score;

}
int main() {
	//vector<student> vectorStudents;
	set<student> setStudents;
	//int n = 5;
	int n = 3;
	while (n--) {
		student oneStudent;
		string name;
		int score;
		cin >> name >> score;
		//strcpy(oneStudent.name, name.c_str());
		oneStudent.score = score;
		oneStudent.name = name;
		setStudents.insert(oneStudent);

	}
	cout << "===========排序後================" << endl;
	for (set<student>::iterator it = setStudents.begin(); it != setStudents.end(); it++) {
		cout << "name: " << it->name << " score: " << it->score << endl;

	}

	return 0;

}
```
## vector
```cpp
#include<iostream>
#include<vector>
#include<set>
#include<string>
#include<algorithm>
using namespace std;
struct student {
	string name;
	int score;

};
//自定義“小於”
bool comp(const student& a, const student& b) {
	return a.score < b.score;
}

int main() {
	vector<student> vectorStudents;
	int n = 3;
	while (n--) {
		student oneStudent;
		string name;
		int score;
		cin >> name >> score;
		//strcpy(oneStudent.name, name.c_str());
		oneStudent.score = score;
		oneStudent.name = name;
		vectorStudents.push_back(oneStudent);
	}
	cout << "===========排序後================" << endl;
	sort(vectorStudents.begin(), vectorStudents.end(),comp);
	for (vector<student>::iterator it = vectorStudents.begin(); it != vectorStudents.end(); it++) {
		cout << "name: " << it->name << " score: " << it->score << endl;
	}

	return 0;

}
```
