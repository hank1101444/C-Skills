```cpp
	stack <int> s;
	s.push(1);
	s.push(3);
	stack <int>s1;
	s1 = s;
	while (!s1.empty()) {
		cout << s1.top();
		s1.pop();
	}
```
