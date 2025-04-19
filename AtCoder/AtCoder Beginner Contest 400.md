# AtCoder Beginner Contest 400

20250416 22:03\~23:43（100 mins）

Outcome: 100 + WA(6) + WA(3) …

---

### Record

### A：

The only problem I had solved, and it was easy.

### B：

I got 6 WA, I don’t know why？ I must complete this…

### C：

I also thought I could get it…

### Other：

I had no time to even look at it.

---

# A

Let's skip this question.

# B

Problem Statement: <https://atcoder.jp/contests/abc400/tasks/abc400_b>

What I wrote originally:

```cpp
#include<iostream>
#include<cmath>
#include<limits.h>
using namespace std;
int main(){
    long a =0, b =0;
    cin >> a >> b;
    long sum =0;
    sum = (pow(a,b+1)-1)/(a-1);
    if(sum > pow(10,9) || sum < 0 ){
        cout<< "inf";
    }
    else{
        cout << sum;
    }
}
```

The answer I got from GPT：

```cpp
#include<iostream>
using namespace std;

int main(){
    long N, M;
    cin >> N >> M;

    long sum = 0;
    long current = 1;  // 初始化當前項目為 N^0 = 1
    for (int i = 0; i <= M; i++) {
        sum += current;
        
        // 若 sum 超過 10^9，就輸出 "inf"
        if (sum > 1000000000) {
            cout << "inf";
            return 0;
        }
        
        current *= N;  // 下一項是 N 的 i+1 次方
    }

    cout << sum;  // 若 sum 沒有超過 10^9，則輸出 sum
    return 0;
}
```

I didn't think this was a hard question, so I felt a bit disappointed in myself.

### C

What I wrote in the contest.（AC11、WA18）

```cpp
#include<iostream>
#include<cmath>
#include<vector>
#include <algorithm>
using namespace std;
int main(){
    long long N =0;
    cin >> N;
    // b use try;
    vector<long long> appear;

    int ansNum =0;
    for(long long i=1;i<sqrt(N);i++){
        int twoIndex = 1;
        while(pow(2,twoIndex) <= N /pow(i,2) ){
            long long temp = pow(i,2) * pow(2,twoIndex);
            vector<long long>::iterator it = std::find(appear.begin(), appear.end(), temp);
            if(it == appear.end() ){
                appear.push_back(temp);
                ansNum++;
            }
            twoIndex++;

        }
    }

    cout << ansNum;
}

```

Answer I found in the forum

```cpp
//Answer I found in the forum
#include <bits/stdc++.h>
using namespace std;
#define ll long long
#define ull unsigned long long

void solve() {
    ll n;
    cin >> n;
    cout<<(ll)sqrt((long double)n/4) + (ll)sqrt((long double)n/2)<<endl;
}


int main() {
    int t = 1;
    //cin >> t;
    while (t--)
        solve();
}
```

The key step: 

---

![image.png](./AtCoder%20Beginner%20Contest%20400-assets/image.png)

![image 1.png](./AtCoder%20Beginner%20Contest%20400-assets/image%201.png)

---