# REV Free Flag

Given c code below

```c
#include<stdio.h>
#include<string.h>


int main(int argc, char **argv){
    int c[] = {119, 74, 101, 91, 107, 81, 116, 44, 16, 99, 20, 107, 76, 41, 127, 122, 20, 118, 71, 71, 80, 125, 82, 117, 17, 118, 84, 44, 20, 118, 127, 44, 84, 44, 83, 44, 78, 71, 78, 43, 87, 122, 73, 43, 127, 126, 82, 113, 69, 118, 68, 116, 89, 101};
    char inp[100];
    printf("apa flagnya\n");
    scanf("%s", &inp);
    int len = strlen(inp);
    if(len != 54){
        printf("bukan");
        return 0;
    }
    for(int i=0; i<len; i++){
        if(i%2==1 && inp[i] != (c[i] ^ 24)){
            printf("bukan");
            return 0;
        } else if (i%2==0  && inp[i] != (c[i] ^ 32)){
            printf("bukan");
            return 0;
        }
    }
    printf("mantap!!\n");
    return 0;
}
```

The code checks the input length must be 54. Then for each odd index, it will XOR the letter's ascii code with 24, and for even index, it will XOR the letter's ascii code with 32.

Here is my solver in python

```py
c = [119, 74, 101, 91, 107, 81, 116, 44, 16, 99, 20, 107, 76, 41, 127, 122, 20, 118, 71, 71, 80, 125, 82, 117, 17, 118, 84, 44, 20, 118, 127, 44, 84, 44, 83, 44, 78, 71, 78, 43, 87, 122, 73, 43, 127, 126, 82, 113, 69, 118, 68, 116, 89, 101]
flag = ''
for i in range(0, 54):
    if i % 2 == 1:
        flag += chr(c[i] ^ 24)
    else:
        flag += chr(c[i] ^ 32)

print(flag)
```
The flag is
```
WRECKIT40{4sl1_b4ng_perm1nt44n_4t4s4n_n3wbi3_friendly}
```