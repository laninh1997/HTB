# Grandpa-windows

- enumerate

chỉ dùng p80, show các method allowed

![https://lh7-us.googleusercontent.com/Jvqd5Rkspo2Nth7eLtxk_Bi_v2N0sqLaYV0Tg0k7ROsm1dMDEVY_eDzzVCCrbMTdI6DM6jB-mJzjkrtcniJ5SHMVae6y1EsDB5i2FMIVs4a0TEbHYkroF71mYFtd2mHfh6cp1JQbXUCA](https://lh7-us.googleusercontent.com/Jvqd5Rkspo2Nth7eLtxk_Bi_v2N0sqLaYV0Tg0k7ROsm1dMDEVY_eDzzVCCrbMTdI6DM6jB-mJzjkrtcniJ5SHMVae6y1EsDB5i2FMIVs4a0TEbHYkroF71mYFtd2mHfh6cp1JQbXUCA)

PUT có thể upload file tùy ý

MOVE có thể rename file

các path ẩn not interesting

![https://lh7-us.googleusercontent.com/KxRWnPoj0Dc9YmpmuvXCsOCLBZv8_2y-Zc9ngc3VDtq3-Q_Swz9tpV1VnNgWJqgfwGyZZ75M4r8_VSKPg1MnjjhNiyg_VVy1V4oKvr-raW-u5MJQs7swFvf1eoyK1y43Q3i3GlDtP_3Y](https://lh7-us.googleusercontent.com/KxRWnPoj0Dc9YmpmuvXCsOCLBZv8_2y-Zc9ngc3VDtq3-Q_Swz9tpV1VnNgWJqgfwGyZZ75M4r8_VSKPg1MnjjhNiyg_VVy1V4oKvr-raW-u5MJQs7swFvf1eoyK1y43Q3i3GlDtP_3Y)

kiểm tra các extension có thể upload -> ko có cái nào allowed

![https://lh7-us.googleusercontent.com/cBWcMOMUP9wyf2a2j-Rt-wgxdRxL9926z0y3yGUrpXnaUtDUlMvyVwPwWFzKjprD1oP9XeThCLTQto1YntReaUuCAAM0bj7133JjRnq_cvrW8ADDn2kfZu-B4ApfLZajBrGbjftNDe-I](https://lh7-us.googleusercontent.com/cBWcMOMUP9wyf2a2j-Rt-wgxdRxL9926z0y3yGUrpXnaUtDUlMvyVwPwWFzKjprD1oP9XeThCLTQto1YntReaUuCAAM0bj7133JjRnq_cvrW8ADDn2kfZu-B4ApfLZajBrGbjftNDe-I)

- exploit

tìm kiếm Microsoft IIS httpd 6.0 exploit 
[https://github.com/g0rx/iis6-exploit-2017-CVE-2017-7269](https://github.com/g0rx/iis6-exploit-2017-CVE-2017-7269)

thực thi và có đc reverse shell của network service

![https://lh7-us.googleusercontent.com/3oyB7M5uVNYmZLjh5chMB4dSQ0U6KXu6kPzAFeq4Olq8P1ZmJGEO4v8S3oE16JwA-2mKtpoabi4s6sKltUnsG8NTnCagzKEAar_xbJEcS_BN0NCxq30Jm58iWMHGkSNi8l1GMtlF0UTv](https://lh7-us.googleusercontent.com/3oyB7M5uVNYmZLjh5chMB4dSQ0U6KXu6kPzAFeq4Olq8P1ZmJGEO4v8S3oE16JwA-2mKtpoabi4s6sKltUnsG8NTnCagzKEAar_xbJEcS_BN0NCxq30Jm58iWMHGkSNi8l1GMtlF0UTv)

nhưng ko được phép truy cập thư mục của user

![https://lh7-us.googleusercontent.com/g5LGuG_I8iBtSfV82GV6c-DM-I62-WDCnbIEV2K0CYVCNvihCgylnS01qgKpTmb4SkLQ5MglN-aRI4HYG7apJXM0MWE1IWebTQ_WABRu7X2pk7TEKKXcN-lDoTh0dBAgmd3LDZsbxK23](https://lh7-us.googleusercontent.com/g5LGuG_I8iBtSfV82GV6c-DM-I62-WDCnbIEV2K0CYVCNvihCgylnS01qgKpTmb4SkLQ5MglN-aRI4HYG7apJXM0MWE1IWebTQ_WABRu7X2pk7TEKKXcN-lDoTh0dBAgmd3LDZsbxK23)

![https://lh7-us.googleusercontent.com/drqTqqtrskq7HkeIxeMKaEpCoZ3NYU7SK8_6Jh9u0pqO3iKr5GeWDUNG1m9jVkSsw-tz0zbplrMuY5jvayek3QecBm64ipsTDMrQougmJVOfJqWu5i2Cd_eyW7O-2HSyx21_2JE_LKx-](https://lh7-us.googleusercontent.com/drqTqqtrskq7HkeIxeMKaEpCoZ3NYU7SK8_6Jh9u0pqO3iKr5GeWDUNG1m9jVkSsw-tz0zbplrMuY5jvayek3QecBm64ipsTDMrQougmJVOfJqWu5i2Cd_eyW7O-2HSyx21_2JE_LKx-)

Since the **SeImpersonatePrivilege** is enabled. This may be vulnerable to [Rotten Potato](https://foxglovesecurity.com/2016/09/26/rotten-potato-privilege-escalation-from-service-accounts-to-system/) exploit. But since we are not using metasploit, let’s try [JuicyPotato](https://github.com/ohpe/juicy-potato).

Then, I remembered that we mostly use a powershell payload for JuicyPotato, but since we do not have powershell here (as it is Windows XP), let’s try [Churrasco](https://github.com/Re4son/Churrasco/) here.

- pe

dùng churrasco để có được quyền root

![https://lh7-us.googleusercontent.com/CwZkZwLt-qSsbfL6SiF4lNGAJObBfll4jBVteShkPsUqvhkTScsQpHat552UPMPTpXnXJGQYMzqlRJoUMzALUnKF6Zrf25TiZr8NMIYaXfd1MwgXW4BQGXjvKw__U4zmCGgt3R2Do1Ap](https://lh7-us.googleusercontent.com/CwZkZwLt-qSsbfL6SiF4lNGAJObBfll4jBVteShkPsUqvhkTScsQpHat552UPMPTpXnXJGQYMzqlRJoUMzALUnKF6Zrf25TiZr8NMIYaXfd1MwgXW4BQGXjvKw__U4zmCGgt3R2Do1Ap)

tạo payload để có reverse shell

![https://lh7-us.googleusercontent.com/DkcmgLgf7-GUv_fmLkJjtTMhBOfXoEIj-rJ2j42HQfVQ6XnTTXOKGLtLjsvUPZ1SXEingJigKUL5Sui951UB1Log3BZ2-yfRXwpg15PSx666MgI3K3AkUjFA4hIFP1URa4MZfVEyA8x-](https://lh7-us.googleusercontent.com/DkcmgLgf7-GUv_fmLkJjtTMhBOfXoEIj-rJ2j42HQfVQ6XnTTXOKGLtLjsvUPZ1SXEingJigKUL5Sui951UB1Log3BZ2-yfRXwpg15PSx666MgI3K3AkUjFA4hIFP1URa4MZfVEyA8x-)

![https://lh7-us.googleusercontent.com/kN3Q8dq4uSh3qGWCP8N-wCg9SiZSWDUiysQWcFbDh8BcFEY6p5SKcmy-MEvjmUPMe3TVEG3lyNpy078B0Y2IfgZUiZBMkcfNYy9J3UE5XYDJvIKMgiXfqjusa512b_kpKOC0eJCGOFUq](https://lh7-us.googleusercontent.com/kN3Q8dq4uSh3qGWCP8N-wCg9SiZSWDUiysQWcFbDh8BcFEY6p5SKcmy-MEvjmUPMe3TVEG3lyNpy078B0Y2IfgZUiZBMkcfNYy9J3UE5XYDJvIKMgiXfqjusa512b_kpKOC0eJCGOFUq)

netcat và thực thi payload

![https://lh7-us.googleusercontent.com/hG_AguyIvmLuOJNDO3rQAUTjIhmHmpD9NPO2dzSNUTLIGyla6eZiL862wgdeG6R0_4nehZlpasR9c0OJJmRLez5KrTwg9iTjOXpC0rSSJ51TTKUH8XAXevpsV7KElAOnVIvQAEAGOz2a](https://lh7-us.googleusercontent.com/hG_AguyIvmLuOJNDO3rQAUTjIhmHmpD9NPO2dzSNUTLIGyla6eZiL862wgdeG6R0_4nehZlpasR9c0OJJmRLez5KrTwg9iTjOXpC0rSSJ51TTKUH8XAXevpsV7KElAOnVIvQAEAGOz2a)

có được quyền system

![https://lh7-us.googleusercontent.com/kSuah40Cjf8n7b9urya9TqpXTfqF6ZiuwZyRwcS06p6Qy9sVddnJiTnq1Yh63zTgsery4QqtgRedpyK3zA2dzxFy7XDpcHfcjYJKRzTrTahnnTxYB9NEytg5QoyQPpEEYuuZuJv5vScf](https://lh7-us.googleusercontent.com/kSuah40Cjf8n7b9urya9TqpXTfqF6ZiuwZyRwcS06p6Qy9sVddnJiTnq1Yh63zTgsery4QqtgRedpyK3zA2dzxFy7XDpcHfcjYJKRzTrTahnnTxYB9NEytg5QoyQPpEEYuuZuJv5vScf)

lấy flag

![https://lh7-us.googleusercontent.com/p-kR5XGKmpLEKYbSGJSNCa0oDTs7N5g0DdtlDMPZgQkk8pkFb85Gx1ZyZgdnVnp-wf_NAkP87UoqfRwmNpxmv7OMQH_PABPKV9pyGVk5v7nWGtFPH7BbXioTG5EOwid4cE-QFnc7muUB](https://lh7-us.googleusercontent.com/p-kR5XGKmpLEKYbSGJSNCa0oDTs7N5g0DdtlDMPZgQkk8pkFb85Gx1ZyZgdnVnp-wf_NAkP87UoqfRwmNpxmv7OMQH_PABPKV9pyGVk5v7nWGtFPH7BbXioTG5EOwid4cE-QFnc7muUB)

![https://lh7-us.googleusercontent.com/lQi5bwytWz3iUtDPV-NziGur4IFfhLvAgTFjfz0gnOqLKWgIHeVtLpT9MexXw7UgauhjoFzyytd2BcvQ5prNBVSS27tcmyrWDw7DkIv7qKGkdSF14KzZv5XO2bJrYm2KpdAgWpf4wqIx](https://lh7-us.googleusercontent.com/lQi5bwytWz3iUtDPV-NziGur4IFfhLvAgTFjfz0gnOqLKWgIHeVtLpT9MexXw7UgauhjoFzyytd2BcvQ5prNBVSS27tcmyrWDw7DkIv7qKGkdSF14KzZv5XO2bJrYm2KpdAgWpf4wqIx)