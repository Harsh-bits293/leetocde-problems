### Problem statement - Given an integer n, return true if it is a power of four. Otherwise, return false. An integer n is a power of four, if there exists an integer x such that n == 4x.
<br>

### My Original approch

```cpp
    bool isPowerOfFour(int num) {
        if(n==0)
            return false;
        if(n==1)
            return true;
        
        if(n%4==0)
        return isPowerOfFour(n/4);
        
        return false;
    }
```
## Math based approach using log base 4

num= 4^a
then a = log_4 (num)

If a is an integer then num is a power of 4
How to check a is an integer when log_4 is a decimal value
check if(ceil(a)==floor(a))
```cp
    bool isPowerOfFour(int n) 
    {
       if(n==0)return false;

       float a= log(n) / log(4);
      
        if(ceil(a)==floor(a))
            return true;
        return false;
    }
``` 
## Bit-manupulation
    1. No of Set Bit Always Be Only ONE 
    2. That SetBit Possition Should Be always In odd Place [ starting from Left ] 
```cp
bool isPowerOfFour(int num) {
        if(num<0)return false;
        int no_of_one = 0,pos = 1,ones_pos = 0;
        while(num){
            if(num&1)no_of_one+=1,one_pos = pos;
            num>>=1,pos+=1;
        }
        return no_of_one==1&&one_pos&1;
    }
```
## Smart approach
```cp
    bool isPowerOfFour(int num) {
        if(num<0)return false;
        for(int i=0;i<32;i+=2)if(num==1<<i)return true;
        return false;
    }

```
Similar questions-:
1. Power of 2
2. Power of 3(approaches-[link](https://leetcode.com/problems/power-of-three/discuss/1178701/Power-Of-Three-or-Loops-Recursive-Direct-Approach-or-Multiple-Solutions-Explained-w-Clean-Code))
 
