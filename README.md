# BaekJoonSolve
think-logic
백준 1904번
#include <stdio.h>
int dp[100]; //dp
int Tile(int N)
{
  if(N==2)
    return 2;
  if(N==1) //기저사례
    return 1;
  if(N<=0)
    return 0; //만들 수 없으므로; 
  if(dp[N]!=0) //dp를 썻으면
    return dp[N];
  dp[N]=Tile(N-1)+Tile(N-2);
  return dp[N];

}
int main(void)
{
  int N;
  scanf("%d",&N);
  printf("%d\n",Tile(N));
}

맨 처음에 Tile[N]을 만드려먼 Tile[N-1]에 1을 추가하는거 + Tile[N-2]에 00을 추가하면 된다는걸 파악했는데
1을 추가하는 행위나 00을 추가하는 행위가 같은 행위라는 걸 인지하지못햿다
그래서 00이:x개 1이 N-2x개 이러면서 삽질을 했었다
