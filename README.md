# Counnt-primes-leetcode

class Solution {
public:
    int countPrimes(int n) {
        if(n <= 2) return 0;
        vector<bool> arr (n, false);
        int counter = 0;
        for(int i = 2; i <= sqrt(n); i ++){
            if(arr[i]) continue;
            int tmp = 2 * i;
            while(tmp < n){
                if(!arr[tmp]){
                    counter ++;
                    arr[tmp] = true;
                }
                tmp += i;
            }
        }
        return n - counter - 2 ;
    }
};
