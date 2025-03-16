# Problema del palíndromo más largo posible
Given a string s, determine the longest palindromic substring in s. A substring is considered a palindrome if it reads the same forward and backward.<br>
A substring is a contiguous sequence of characters within a string. The longest palindromic substring is the substring with the maximum length that satisfies this condition.<br>

Solución hecha en C#:

```
int n = input_string.Length;
bool[,] dp = new bool[n,n];

for(int i = 0; i < n; i++){
	dp[i,i] = true;
}
int start = 0;
int maxLen = 1;

for(int i = 0; i < n-1; i++){
	if(input_string[i] == input_string[i+1]){
		dp[i,i+1] = true;
		if(maxLen < 2){
			start = i;
			maxLen = 2;
    }
  }
}
for(int k = 3; k <= n; k++){
	for(int i = 0; i < n-k+1; i++){
		int j = i+k-1;
		if(dp[i+1,j-1] && input_string[i] == input_string[j]){
			dp[i,j] = true;
			if(k > maxLen){
				start = i;
				maxLen = k;
      }
    }
  }
}
return input_string.Substring(start, maxLen);
```
