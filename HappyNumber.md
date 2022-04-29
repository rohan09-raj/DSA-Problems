### Question
https://leetcode.com/problems/happy-number

### Solution
```JAVA
class Solution {
	public boolean isHappy(int n) {
		ArrayList<Integer> list = new ArrayList();
		
    int count = 1;
		
    if(n == 1 || n == 7) {
			return true;
		} else {
			return digitSum(n,list,count);
		}
	}
			
  public boolean digitSum(int n, List<Integer> list,int count){
		int sum = 0;

    while(n > 0){
			int digit = n % 10;
			sum += digit * digit;
			n = n/10;
		} 

    if(list.contains(sum) && count != 1 ) {
			return false;
		} else {
			list.add(sum);
			count++;
    }
		
    if(sum == 1) {
      return true;
    }	else {
      return digitSum(sum,list,count);
    }
	}
}
```
