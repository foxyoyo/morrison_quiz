# morrison_quiz

## 目錄結構
- <b>Quiz_A : </b> Please design a Git branching workflow for multiple repositories on different environment (DEV,UAT,PROD ... ) , include a versioning mechanism.
- <b>Quiz_B : </b> What’s the method/tool(s) will you choose to manage container and monitor mechanism.
- <b>Quiz_C : </b> Please write a Shell Script (check_IP_range.sh) for below description

## Quiz_C 
> Pre-required:
>>1. 透過 grepcidr 套件 (https://formulae.brew.sh/formula/grepcidr)
```
    brew install grepcidr (Mac)
    apt-get install grepcidr (ubuntu)
```

>>2. How to (如何使用)
    ./check_IP_range.sh -c "subnet/mask" -f {file path of ip list }
    如果IP_list 中ip 有隸屬指定subnet 時：
```
    ./check_IP_range.sh -c "10.0.1.0/24" -f ./IP_list
    ===================
    The ip belong specifc subnet (10.0.1.0/24) as below : 
    10.0.1.23
```

如果IP_list 中ip 無隸屬指定subnet 時：
```
    ./check_IP_range.sh -c "10.0.99.0/24" -f ./IP_list
    There are no any ip list in (./IP_list) in the 10.0.99.0/24
```

    如果缺少指定參數時：
```
    ./check_IP_range.sh -c "10.0.99.0/24"             
    Some or all of the parameters are empty
    Usage: $0 check_IP_range.sh -c "10.0.2.0/24" -f ./IP_list 
            -f: Your IP_list Path
            -c: Your Checking Subnet

```