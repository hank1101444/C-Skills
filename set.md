# 有雙向迭帶器
```cpp
	set <int> s = {2,3};
	s.insert(1);
	s.insert(9);
	s.insert(4);
	set <int>::iterator it;
	// for (std::set<int>::reverse_iterator it = myset.rbegin(); it != myset.rend(); it++) //反向
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
