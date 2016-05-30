#include <iostream>
#include <cstdio>
#include <string>
#include <cstring>
#include <algorithm>
#include <cmath>
using namespace std;
int n;
const int MAXN=20010;
int c1[MAXN],c2[MAXN];
struct OX{
    int v;
    int loc;
}a[MAXN];
int lowbit(int t){
    return t&(-t);
}
void change(int *c,int i,int x){
    while(i<MAXN){
        c[i]+=x;
        i+=lowbit(i);
    }
    return ;
}
int sum(int *c,int i){
    int res(0);
    while(i>0){
        res+=c[i];
        i-=lowbit(i);
    }
    return res;
}
bool cmp(OX a,OX b){
    return a.v<b.v;
}
int main(){
    scanf("%d",&n);
    for(int i=0;i<n;i++){
        scanf("%d%d",&a[i].v,&a[i].loc);
    }
    sort(a,a+n,cmp);
    long long ans(0);
    int d(0);
    for(int i=0;i<n;i++){
        int loc=a[i].loc;
        int v=a[i].v;
        int cnt=sum(c1,loc);
        int dist=sum(c2,loc);
        ans+=(long long)v*(cnt*loc-dist+d-(i-cnt)*loc-dist);
        change(c1,loc,1);
        change(c2,loc,loc);
        d+=loc;
    }
    cout<<ans<<endl;
	return 0;
}
