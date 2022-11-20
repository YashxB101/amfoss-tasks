#include <iostream>
using namespace std;

int countDistinct(int arr[], int n)
{
    int res = 1;
    for (int i = 1; i < n; i++) {
        int j = 0;
        for (j = 0; j < i; j++)
            if (arr[i] == arr[j])
                break;
        if (i == j)
            res++;
    }
    return res;
}

int main() {
    int t;
    cin>>t;
    for (int i=0;i<t;i++){
        int n,flag=0,count=0;
        cin>>n;
        int arr[n];
        for (int j=0;j<n;j++){
            cin>>arr[j];
            if (arr[j]==0) {
                flag=1;
                count++;
            }
        }
        int res=countDistinct(arr,n);
        if (flag==1){
            cout<<n-count<<endl;
            continue;
        }
        else if (res==n){
            cout<<n+1<<endl;
        }
        else cout<<n<<endl;
    }

    return 0;
}

<img width="1345" alt="image" src="https://user-images.githubusercontent.com/100985592/202915797-daaf4a25-6976-4b8d-9603-6285efca43d7.png">

