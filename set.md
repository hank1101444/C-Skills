# 有雙向迭帶器
```cpp
	set <int> s;
	s.insert(1);
	s.insert(9);
	s.insert(4);
	set <int>::iterator it;
	for (it = s.begin(); it != s.end(); it++) {
		cout << *it;
	}
	s.erase(2);
	set <int>::iterator search;
	search = s.find(2);
	if (search != s.end()) {
		cout << *search;
	}
	else {
		cout << "not";
	}

```
