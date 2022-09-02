 ```cpp
 #include <iostream>
using namespace std;
#include <string>
#include <cstring>
#define row 5
#define col 6
#include<utility>
#include <queue>
// y change to col, x change to row
int sx, sy, tx, ty, dx[4] = {0, 0, 1, -1}, dy[4] = {1,-1, 0, 0};
string s;
int ans[row][col];

void BFS(int mp[][col]) {
	memset(ans, -1, sizeof(ans));
	ans[sx][sy] = 0;
	queue <pair<int, int>> q;
	q.push({ sx, sy });
	while (!q.empty()) {
		pair<int, int> now = q.front();
		// 找到目標點可以break
		if (now.first == tx && now.second == ty)
			break;
		q.pop();
		for (int i = 0; i < 4; ++i) {
			// 有沒有超出map
			if (now.first + dx[i] < row && now.first + dx[i] >= 0 && now.second + dy[i] < col && now.second + dy[i] >= 0)
				//有沒有牆, 有沒有走過 (這樣可以找到最短)
				if (mp[now.first + dx[i]][now.second + dy[i]] != 1 && ans[now.first + dx[i]][now.second + dy[i]] == -1) {
					q.push({ now.first + dx[i],now.second + dy[i] });
					ans[now.first + dx[i]][now.second + dy[i]] = ans[now.first][now.second] + 1;
				}
		}
	}
}


int main() {
	//(3, 1) -> (2,0)
	while (cin >> sx >> sy >> tx >> ty) {
		--sx;
		--sy;
		--tx;
		--ty;
		int map[row][col];
		for (int i = 0; i < row; ++i) {
			cin >> s;
			for (int j = 0; j < col; ++j)
				map[i][j] = s[j] - '0';
		}
		BFS(map);
		for (int i = 0; i < row; ++i) {
			for (int j = 0; j < col; ++j) {
				cout << ans[i][j] << ' ';
			}
			cout << endl;
		}
		cout << endl << ans[tx][ty];
	}

	return 0;
}
 ```
<h2> Testing case
1 1 1 6
000000
011101
000010
011000
000010
