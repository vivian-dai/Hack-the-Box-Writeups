# Baby RE

Author: [Xh4H](https://app.hackthebox.eu/users/21439)  
Category: Reversing  
Points: 10

## Challenge Description
> Show us your basic skills! (P.S. There are 4 ways to solve this, are you willing to try them all?)\

[baby](./baby)

## Approach
I have yet to find all four ways to solve it but will add if I do. Open [baby](./baby) with [Ghidra](https://ghidra-sre.org) and navigate to the main function.
```c
undefined8 main(void)

{
  int iVar1;
  undefined8 local_48;
  undefined8 local_40;
  undefined4 local_38;
  undefined2 local_34;
  char local_28 [24];
  char *local_10;
  
  local_10 = "Dont run `strings` on this challenge, that is not the way!!!!";
  puts("Insert key: ");
  fgets(local_28,0x14,stdin);
  iVar1 = strcmp(local_28,"abcde122313\n");
  if (iVar1 == 0) {
    local_48 = 0x594234427b425448;
    local_40 = 0x3448545f5633525f;
    local_38 = 0x455f5354;
    local_34 = 0x7d5a;
    puts((char *)&local_48);
  }
  else {
    puts("Try again later.");
  }
  return 0;
}
```
### Method 1
The first method is simply running it. We see the line `iVar1 = strcmp(local_28,"abcde122313\n");` meaning we need our input to equal to "abcde122313" and a new line character.
```bash
$ ./baby
Insert key:
abcde122313
HTB{B4BY_R3V_TH4TS_EZ}
```
### Method 2
The second method is noticing the hex:
```c
if (iVar1 == 0) {
  local_48 = 0x594234427b425448;
  local_40 = 0x3448545f5633525f;
  local_38 = 0x455f5354;
  local_34 = 0x7d5a;
  puts((char *)&local_48);
}
```
These are in [little endian](https://en.wikipedia.org/wiki/Endianness) so we can start from `local_34` and decode up to `local_48`. this gives us "}ZE_ST4HT_V3R_YB4B{BTH" which we can reverse and get the flag.
```python
print("}ZE_ST4HT_V3R_YB4B{BTH"[::-1])
```
### Flag
`HTB{B4BY_R3V_TH4TS_EZ}`