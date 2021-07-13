# Infiltration

Author: [greenwolf](https://app.hackthebox.eu/users/110957)
Category: OSINT
Points: 30

## Challenge Description
> Can you find something to help you break into the company 'Evil Corp LLC'. Recon social media sites to see if you can find any useful information.

## Approach
A Google search of "evil corp llc" will give a [Linkedin company](https://www.linkedin.com/company/evil-corp-llc/) as the first result. The profile says "HTB{WW91IGNhbiBkbyB0aGlzLCBrZWVwIGdvaW5nISEh}". Decoding "WW91IGNhbiBkbyB0aGlzLCBrZWVwIGdvaW5nISEh" from [base64](https://www.base64decode.org/) results in "You can do this, keep going!!!" Let's keep going!  
The next result is [Eryn Mcmahon's Instagram](https://www.instagram.com/eryn_mcmahon12). After looking through every post, [this one](https://www.instagram.com/p/BvbnFhTj9YS) seemed to have many comments about the flag. If you zoom in, you can see the flag on the tag in the bottom left
![post](./post.jpg)

### Flag
`HTB{Y0ur_Enum3rat10n_1s_Str0ng_Y0ung_0ne}`