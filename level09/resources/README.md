## Check files in home

ls -la

->  -rwsr-sr-x 1 flag09 level09 7640 Mar  5  2016 level09
    ----r--r-- 1 flag09 level09   26 Mar  5  2016 token

## check level09 and we see that it adds positions in the ascci table according 
## to the position in which it is in the input.

./level09 f4kmm6p

->  f5mpq;v

## to exploit then we need to use "token" but we need to decode with a program made by us in C
## we need to upload with de following command

```bash
    scp -P 4242 decoder.c level09@ip:/tmp/.
```

## compile decode.c and execute with the input token content

gcc decoder.c -o decode

./decoder $(cat ~/token)

->  f3iji1ju5yuevaus41q1afiuq

## Log in to user flag09

su flga09 (password: f3iji1ju5yuevaus41q1afiuq)

## execute getflag

getflag

->  Check flag.Here is your token : s5cAJpM8ev6XHw998pRWG728z

## Log in to user level10

su level10 (password: s5cAJpM8ev6XHw998pRWG728z)