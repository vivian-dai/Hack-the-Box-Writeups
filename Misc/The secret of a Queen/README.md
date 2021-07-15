# The secret of a Queen

Author: [brutale1602](https://app.hackthebox.eu/users/148257)  
Category: Crypto  
Points: 10

## Challenge Description
> Decrypt the code and find the Queen's secret!

### Downloads
![The secret of a Queen](./The%20secret%20of%20a%20Queen.png)

## Approach
A search of "queen cipher" brought up information about Mary Queen of Scots' Cipher. [decode.fr](https://www.dcode.fr) is a nice website for solving ciphers and they had the [Queen's cipher](https://www.dcode.fr/mary-stuart-code) as well. Pay careful attention to the letters. Also note that the 4th to 8th character as well as the last 5 characters are null characters which should be replaced with braces to be in flag format.

### Flag
`HTB{THEBABINGTONPLOT}`