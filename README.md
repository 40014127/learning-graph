#include <bits/stdc++.h>
#define ll long long

using namespace std;
const int ma = 1e5+5;

vector < pair <int, int > > v[1005];
int w[1005];
int main()
{
  /*freopen("si.txt","r",stdin);
  freopen("so.txt","w",stdout);*/

  //n,k = 1000
  //m = 1e6
  //w[i] = 100000
  int n,m,k;
  cin>>n>>m>>k;
  for(int i=1;i<=n;i++)
    cin>>w[i];
  int x,y;
  for(int i=0;i<m;i++)
  {
    cin>>x>>y;
    v[x].push_back(make_pair(w[y],y));
    v[y].push_back(make_pair(w[x],x));
  }
  for(int i=1;i<=n;i++)
  sort(v[i].begin(), v[i].end());
  
  for(int i=1;i<=n;i++)
  {
    if(v[i].size()>=k)
      cout<<v[i][v[i].size()-k].second<<endl;
    else
      cout<<"-1"<<endl;
  }
  return 0;
}
