//rating trap//
#include <iostream>
#include<stdio.h>
#include<cmath>
#include<string.h>
#include<bits/stdc++.h>
using namespace std;
#define ll long long int 
#define eb emplace_back
#define loop0 for(int i=0;i<n;i++)
#define loop1 for(int i=1; i<n; i++)
#define mp make_pair
#define fast ios_base::sync_with_stdio(false);cin.tie(0); cout.tie(0)
#define sc1(x) cin>>x
#define sc2(x,y) cin>>x>>y
#define sc3(x,y,z) cin>>x>>y>>z
#define rev0(i,n)  for(int i=n-1; i>=0; i--)
#define rev1(i,n)  for(int i=n; i>0; i--)
#define all(x) (x).begin(),(x).end()
#define rep(i,a,b)  for(int i=a;i<b;i++)
#define nl cout<<endl;
#define setb  __builtin_popcount
// containers//
typedef  vector < int > vi;
typedef  vector < long long int >  vll;
typedef  pair< int,int > pi;
typedef  pair< ll, ll >  pll;
typedef vector<pair<int,int>> vpi;
typedef vector<pair<ll,ll>> vpl;
//=============================================================================================================//
//=============================================================================================================//
const long long INF=1e18;
const int32_t Mod=1e9+7;
const int32_t MM=998244353;
const int N=4e4 + 5;
#define SIEVE
// int primes[N];
// vector<int> pr;
// void sieve(){
//     for(int i=2;i<N;i++){
//         if(primes[i]==0){
//             pr.eb(i);
//             for(int j=i*i;j<N;j+=i){
//                 primes[j]=1;
//             }
//         }
//         primes[i]^=1;
//     }
// }
long long lcm(int a, int b)
{
    return (a / gcd(a, b)) * b;
}
 
ll noofFactors(int n){
    ll cnt=0;
    int val=sqrt(n);
    for(int i=1; i<=val;i++){
        if(n%i==0){
            cnt++;
            if(i!=(n/i)){
                cnt++;
            }
        }
    }
    return cnt;
}

int countBits( int number)
{   
    return (int)log2(number)+1;
}
 
bool checkKthBit(int n, int k){
    n=n>>k;
    if((n&1)==1){
        return 1;
    }
    return 0;
}
 
int getFirstSetBit(int n){
    int count=0;
    while(n!=0){
        if((n&1)==1){
            count++;
            break;
            }
        count++;
        n=n>>1;
    }
    return count;
}
 
bool isPrime(long long int n){
    if (n==1) return false;
    else {
        for(int i=2;i<=sqrt(n);i++){
            if(n%i==0) return false;
        }
    }
    return true;
}
 
ll  srt(ll  n){
    int low=1,high=n;
    int ans=1;
    while(low<=high){
        int mid=(low+high)/2;
        if(mid*mid<=n){
            ans=mid;
            low=mid+1;
        }
        else{
            high=mid-1;
        }
    }
    return ans;
} 
 
ll  fibonacci(ll  n){
    if(n==1 || n==0){
        return 1;
    }
    return fibonacci(n-1)+fibonacci(n-2);
}
 
ll  power(int a,int b){
    ll  ans=1;
    while(b>0){
        if((b&1)==1){
            ans=ans*a;
        }
        b=b>>1;
        a=a*a;
    }
    return ans;
}
 
int binarycon(int n){
    int ans=0;
    int i=0;
    while(n!=0){
        int bit=n&1;
        ans+=((bit)*power(10,i));
        n=n>>1;
        i++;
    }
    return ans;
}
 
int crt(int n){
    int low=1,high=n;
    int ans=1;
    while(low<=high){
        int mid=(low+high)/2;
        if(mid*mid<=n){
            ans=mid;
            low=mid+1;
        }
        else{
            high=mid-1;
        }
    }
    return ans;
}
 
int gcd(int a ,int b){
    if(b==0) return a;
    else{
        return gcd(b,a%b);
    }
}
 
vi facts(int n){
    vi v(n+1);
    for(int i=1;i<=n;i++){
        for(int j=i;j<=n;j+=i){
            v[j]++;
        }
    }
    return v;
}
 
int search(int low ,int high,int arr[],int x){
    if(high<low) return -1;
    int mid=(low+high)/2;
    if(arr[mid]==x) return mid;
    if(arr[mid]<x) return search(mid+1,high,arr,x);
    return search(low,mid-1,arr,x);
}
 
int highestPowerof2(int n)
{
   int p = (int)log2(n);
   return (int)pow(2, p);
}
 
vll arrinpll(int n){
    vll a;
    loop0{
        ll num;
        cin>>num;
        a.eb(num);
    }
    return a;
}
 
bool isPerfectSquare(ll n){
    if (ceil((double)sqrt(n)) == floor((double)sqrt(n))) return true;
    return false;
}
 
int sumofDig(ll n){
    int ans=0;
    while(n!=0){
        int bit=n%10;
        ans+=bit;
        n=n/10;
    }
    return ans;
}
 
vi setBits(int n){
    vi bits(32,0);
    int i=0;
    while(n!=0){
        if(n&1) bits[i]=1;
        i++;
        n=n>>1;
    }
    return bits;
 
}
 
vi a;
vi arrinp(int n){
    loop0{
        int num;
        cin>>num;
        a.eb(num);
    }
    return a;
}   
 
ll div_sum(ll x){
    ll sum=0;
    ll st=sqrt(x);
    for(int i=1;i<=st;i++){
        if(x%i!=0) continue;
        sum+=i;
        if(x/i!=i) sum+=(x/i);
    }
    return sum;
}
 
 
vll divisors(ll n){
    vll div;
    for (int i=1; i<=sqrt(n); i++)
    {
        if (n%i == 0)
        {
            if (n/i == i) div.eb(i);
            else{
                div.eb(i);
                div.eb(n/i);
            }
        }
    }
    return div;
}

long long modFact(int n, int p)
{
    if (n >= p)
        return 0;
 
    long long result = 1;
    for (int i = 1; i <= n; i++)
        result = (result * i) % p;
    return result;
}

    bool isVal(vector<int> &cnta, vector<int> & cntb){
        for(int i=0;i<26;i++){
            if(cnta[i]<cntb[i]) return false;
        }
        return true;
    }
     
     
int main(){
    int t;
    cin>>t;
    while(t--){
        int n;
        cin>>n;
        string s;
        cin>>s;
        multimap<int,int>ans;
        for(int i=0;i<n;i++){
            if(s[i]=='1'){
                int num=i+1;
                for(int k=i;k<n;k++){
                    if(s[k]=='1') s[k]='0';
                    else s[k]='1';
                }
                ans.insert(pair<int,int>(num,n-i));
            }
        }
        int len=ans.size();
        cout<<len<<endl;
        for(auto it: ans)  cout<<it.first<<" "<<it.second<<endl;
    } 
    return 0;
}
