```c
#include <stdio.h>
#include <stdlib.h>
int N, * M;
#define FOR(s,e) for (int s = 0; s < e; s++)
int safe(int r, int c) {
    FOR(i, r) if (M[i] == c || M[i] - i == c - r || M[i] + i == c + r)
        return 0;
    return 1;}
void Q(int r) { if (r == N) { FOR(i, N) {
    FOR(j, N) if (M[i] == j) printf("Q "); else printf(". ");
    puts("");}puts("");return;}
    FOR(c, N) if (safe(r, c)) { M[r] = c;Q(r + 1); }}
int main() {
    scanf("%d",&N);
    M = (int*)calloc(N, sizeof(int));
    Q(0);
}
```