### map find
```cpp
int main() {
	map<int, string> m;
	m[9] = "hi";
	m[4] = "jif";
	map<int, string>::iterator it;
	for (int i = 0; i < 10; ++i) {
		it = m.find(i);
		if (it != m.end()) {
			cout << it->second << endl;
		}
		else {
			cout << "no element" << endl;
		}
	}


	return 0;
}
```
### set find
* 唯一性
&nbsp;
 set 跟 vector 不同之處是 set 容器裡面的元素是唯一的，具有不重複的特性，vector 則沒有這個限制。
* 不可修改性
&nbsp;
vector 可以修改元素的值，但 set 容器裡面元素的值是不可修改的。
* 順序性
&nbsp;
set 是有序的，也就是裡面的元素會按照特定順序擺放，跟插入順序無關，vector 則不是。
```cpp
int main() {
	set<int> s;
	s.insert(2);
	s.insert(3);

	set<int>::iterator it;
	for (set<int>::iterator it2 = s.begin(); it2 != s.end(); ++it2) {
		cout << *it2 << endl;

	}
	for (int i = 0; i < 10; ++i) {
		it = s.find(i);
		if (it != s.end()) {
			cout << *it << endl;
		}
		else
			cout << "no element" << endl;
	}

	return 0;
}
```

### string find & erase
```cpp
int main() {
    string str = "Hello World";
    string str2("World");
    // find string
    int found = str.find(str2);
    if (found != string::npos) {
       cout << "1 found\n";
    }

    found = str.find("Wo");
    if (found != string::npos) {
        cout << "2 found\n";
    }

    found = str.find("lo Wo");
    if (found != string::npos) {
        cout << "3 found\n";
    }

    found = str.find("Hx");
    if (found != string::npos) {
        cout << "4 found\n";
    }

    found = str.find('H');
    if (found != string::npos) {
        cout << str[found] << endl;
        //（1）erase(pos,n); 刪除從pos開始的n個字元，比如erase(0,1)就是刪除第一個字元
        //（2）erase(position); 刪除position處的一個字元(position是個string型別的迭代器)
        //（3）erase(first, last); 刪除從first到last之間的字元（first和last都是迭代器）
        str.erase(found, 1);
    }
    cout << str << endl;

    return 0;
}
```
