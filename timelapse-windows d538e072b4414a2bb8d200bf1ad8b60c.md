# timelapse-windows

liệt kê các port mở, tìm thấy hầu hết là windows port. có các dịch vụ Kerberos, LDAP, DNS,SMB -> gợi ý đây gần như là 1 Domain Controller. host: DC01

![https://lh7-us.googleusercontent.com/_i_03FnUHvx0cJLZHNx4wKrmO7SyLsQ-j0eNjwzfFLuAhRK2p82Sr1ppGFR6ldpvfKjwBskiQslTNiNlNODqwtUz2alMfa909M3yBuMmVc3Fw6X9NzeUdgAt_t1K3oYYs0jWQzuzluAh](https://lh7-us.googleusercontent.com/_i_03FnUHvx0cJLZHNx4wKrmO7SyLsQ-j0eNjwzfFLuAhRK2p82Sr1ppGFR6ldpvfKjwBskiQslTNiNlNODqwtUz2alMfa909M3yBuMmVc3Fw6X9NzeUdgAt_t1K3oYYs0jWQzuzluAh)

kiểm tra dịch vụ smb (-L to list shares and -N for null authentication)

![https://lh7-us.googleusercontent.com/1zvOiTF4ENZoleIlxphdRPN-n8bsllk1eYjSRQr5wZqXY7FtqAQbdzGTQFoPiPYUJZ39Z_JmFX30xa9kdgCoppiPnkIiFJE0TDlSzYBmlAAwqS7lnI9xWg-2dbBdbR1Kn0KbPCiCcle-](https://lh7-us.googleusercontent.com/1zvOiTF4ENZoleIlxphdRPN-n8bsllk1eYjSRQr5wZqXY7FtqAQbdzGTQFoPiPYUJZ39Z_JmFX30xa9kdgCoppiPnkIiFJE0TDlSzYBmlAAwqS7lnI9xWg-2dbBdbR1Kn0KbPCiCcle-)

ngoại trừ 3 folder đầu kết thúc bằng $ là default và yêu cầu có quyền admin

kiểm tra 3 folder dưới

thấy file zip khá thú vị -> tải xuống

![https://lh7-us.googleusercontent.com/cI3PPOboFVUfWIMx5LGViTw-t8-dWsEcSJukPy8JhrIuIVJGiIS4hZhRTy9mRMYvS0DNQPdjdyes7srxwi5qMvfRPw1vM4wvhiSVCL2jBgzw2U3AhiBGrQ59-SJ8vzdBz67y2qMIjjw8](https://lh7-us.googleusercontent.com/cI3PPOboFVUfWIMx5LGViTw-t8-dWsEcSJukPy8JhrIuIVJGiIS4hZhRTy9mRMYvS0DNQPdjdyes7srxwi5qMvfRPw1vM4wvhiSVCL2jBgzw2U3AhiBGrQ59-SJ8vzdBz67y2qMIjjw8)

unzip yêu cầu pw

dùng zip2john chuyển sang định dạng hash và dùng john để crack

![https://lh7-us.googleusercontent.com/ETwSeKhMnmCw1OzZJ7Kr-pLilN1bZmi9hDwhllDZF70elcxSyovKZJYoR1JmKPk3yG9FgjAD3WTi9VSxmM02UA2EAL8yE9iHZg75FljiSkP82Yz5CcTlxSt024J7-qKa6YfXBbMI_ipn](https://lh7-us.googleusercontent.com/ETwSeKhMnmCw1OzZJ7Kr-pLilN1bZmi9hDwhllDZF70elcxSyovKZJYoR1JmKPk3yG9FgjAD3WTi9VSxmM02UA2EAL8yE9iHZg75FljiSkP82Yz5CcTlxSt024J7-qKa6YfXBbMI_ipn)

![https://lh7-us.googleusercontent.com/qvVT6FcKA5qEcm0Zo1jgsy3pd1mrdQ-ItBVIwe1eN1xO6OxTu1MXZ6HywVY2n2zJmSljeZkspA_UBavo-b057Wui7FWtpC8cxOjDyVz1IGxanEzb6hCsecjhwAb4RV1QbVDT52_n6ieL](https://lh7-us.googleusercontent.com/qvVT6FcKA5qEcm0Zo1jgsy3pd1mrdQ-ItBVIwe1eN1xO6OxTu1MXZ6HywVY2n2zJmSljeZkspA_UBavo-b057Wui7FWtpC8cxOjDyVz1IGxanEzb6hCsecjhwAb4RV1QbVDT52_n6ieL)

unzip vào thư mục rỗng winrm_backup/

![https://lh7-us.googleusercontent.com/aHGof0ifdE6gim3XBaPKRuyapZRmDYDArtYNEeiOrS5zy5j8AMF8j_RFjA5JZSmLDEjJWJY4IN7EN7TwJAQfboVAi-IaOTT6ZXXfOBZRhHBbwWhrfrYDp8i2OkN7PYTK5j6wHYsWlcFW](https://lh7-us.googleusercontent.com/aHGof0ifdE6gim3XBaPKRuyapZRmDYDArtYNEeiOrS5zy5j8AMF8j_RFjA5JZSmLDEjJWJY4IN7EN7TwJAQfboVAi-IaOTT6ZXXfOBZRhHBbwWhrfrYDp8i2OkN7PYTK5j6wHYsWlcFW)

A .pfx file typically represents the [PKCS#12 format](https://www.ibm.com/docs/en/arl/9.7?topic=certification-extracting-certificate-keys-from-pfx-file), containing both a public and private key for a user

dùng openssl để extract private key và certificate (public key) từ .pfx nhưng lại yêu cầu pw

dùng crackpkcs12 để crack

![https://lh7-us.googleusercontent.com/vH43ruxGOg-kCldiUQw5RjpKiQu2bJAE07U21M1iYvdIO8N6uZPH9TTGNV38FHp6v1Kdst08viig8CwKAmPNwoVePYyt1u_otoJetP9ldzl97XSouSsqNIkEgQYzzHXSc7RO0_6i_s_9](https://lh7-us.googleusercontent.com/vH43ruxGOg-kCldiUQw5RjpKiQu2bJAE07U21M1iYvdIO8N6uZPH9TTGNV38FHp6v1Kdst08viig8CwKAmPNwoVePYyt1u_otoJetP9ldzl97XSouSsqNIkEgQYzzHXSc7RO0_6i_s_9)

gen private and public key from .pfx

openssl pkcs8 -topk8 -inform PEM -in sample_private.key -outform PEM -nocrypt

openssl pkcs8 -topk8 -inform PEM -in sample_private.key -outf

dùng winrm connect remote machine -> có shell của legacyy

-S - Enable SSL, because I’m connecting to 5986

![https://lh7-us.googleusercontent.com/LqH5Vp_KPTASKwnrG3ru7vMS2xQPTyuLdC5LKyb5wjTWIqpQBMvfZWQGJ7D3uon12vDFx0m_Ey2JWXtMd-H0MUuX_sSBAgOYhOVEeTjN0N9npIEqF62_INyHo3VZnP7dZLGOa7YnbA9k](https://lh7-us.googleusercontent.com/LqH5Vp_KPTASKwnrG3ru7vMS2xQPTyuLdC5LKyb5wjTWIqpQBMvfZWQGJ7D3uon12vDFx0m_Ey2JWXtMd-H0MUuX_sSBAgOYhOVEeTjN0N9npIEqF62_INyHo3VZnP7dZLGOa7YnbA9k)

lấy user flag

![https://lh7-us.googleusercontent.com/vy0juAbmy9QO0tG9Qc04kdT54Q8od_zVWSWzed0qXc3Y4EMXmP32KtNTMS9zH5ea3pXH0ROGg8NHAR4-w7VI2LOjoj9QJmPzC1V528am6ANpt0C9i0cQ1CViEefjHxIaepz_glH5mAsn](https://lh7-us.googleusercontent.com/vy0juAbmy9QO0tG9Qc04kdT54Q8od_zVWSWzed0qXc3Y4EMXmP32KtNTMS9zH5ea3pXH0ROGg8NHAR4-w7VI2LOjoj9QJmPzC1V528am6ANpt0C9i0cQ1CViEefjHxIaepz_glH5mAsn)

xem các tài khoản trong AD

get-aduser -filter * | select samaccountname

![https://lh7-us.googleusercontent.com/B8eS7qrCxAv0G4RTXWmfK_E92ldnkR8fe7tGETtxvWjxKzXKWuxBBE4jcYu8s1xAvznjN4ukwrwOwclnxX2tXOzrRxVXpxKSrKQhMMfy79plHq46ji4khWLYRNn6_gI__v9pQtOeLg3W](https://lh7-us.googleusercontent.com/B8eS7qrCxAv0G4RTXWmfK_E92ldnkR8fe7tGETtxvWjxKzXKWuxBBE4jcYu8s1xAvznjN4ukwrwOwclnxX2tXOzrRxVXpxKSrKQhMMfy79plHq46ji4khWLYRNn6_gI__v9pQtOeLg3W)

kiểm tra quyền thấy ko có gì đặc biệt

![https://lh7-us.googleusercontent.com/2McRsZ4MaNVFwVHJanZwCYgZc-8ou4nQH9htkQ4kG-6lBOmXlRZO54wfj9MDXNJJ0XFibOjBwsFrQ1VIESma95qOcvtAqqrKWyb_OhnmDjbjyuawjDKKSfDG0GpuYcx-222MDrO_fz7N](https://lh7-us.googleusercontent.com/2McRsZ4MaNVFwVHJanZwCYgZc-8ou4nQH9htkQ4kG-6lBOmXlRZO54wfj9MDXNJJ0XFibOjBwsFrQ1VIESma95qOcvtAqqrKWyb_OhnmDjbjyuawjDKKSfDG0GpuYcx-222MDrO_fz7N)

legacyy nằm trong các group:

![https://lh7-us.googleusercontent.com/2-HjuLTGulrBfD7wiLzCFKdPwXkggdgMq7b710aq-QHZq_G7RorOIohujjfnVaDVebrXRr6RGLVFBJdm1rOetzPjG2Z0XPriN2vtJM0bC2qEGAWM9cmLA-qsODyrdY1njCRjyZUgG89J](https://lh7-us.googleusercontent.com/2-HjuLTGulrBfD7wiLzCFKdPwXkggdgMq7b710aq-QHZq_G7RorOIohujjfnVaDVebrXRr6RGLVFBJdm1rOetzPjG2Z0XPriN2vtJM0bC2qEGAWM9cmLA-qsODyrdY1njCRjyZUgG89J)

dùng winPEAS tìm điểm yếu

do có Antimalware Scan Interface (AMSI) được dành để hỗ trợ Antimalware Scan Interface của Microsoft. nên ko thể dùng netcat hoặc winpeas (ofs hoặc đổi tên, đổi ext cũng ko chạy đc)

tìm kiếm where history file of powershell stored in windows

[PowerShell Command History: A Comprehensive Guide - SharePoint Diary](https://www.sharepointdiary.com/2020/11/powershell-command-history.html#:~:text=PowerShell%20Persistent%20History%20File%20Location,-PowerShell%20doesn%27t&text=Enter%20%E2%80%9C%25userprofile%25%5CAppData%5C,to%20get%20to%20this%20location.)

C:\Users\![UserName]\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt

![https://lh7-us.googleusercontent.com/eCJWz5SKp_oLcVFRIQnSeDJn5m_RnYzfehfJlMcr9wIeeWx5z9dtvCiO0NwzxuqN7P4W-KTuu69tvG6jpYYyIpcjEa-S9DZJmu3Z_xj0objzXCyxqRdCdvr21fZH96CPjoUKM7mWiflF](https://lh7-us.googleusercontent.com/eCJWz5SKp_oLcVFRIQnSeDJn5m_RnYzfehfJlMcr9wIeeWx5z9dtvCiO0NwzxuqN7P4W-KTuu69tvG6jpYYyIpcjEa-S9DZJmu3Z_xj0objzXCyxqRdCdvr21fZH96CPjoUKM7mWiflF)

có pw của svc_deploy

tiếp tục dùng winrm để có shell svc_deploy

![https://lh7-us.googleusercontent.com/slR2QMyPxkzDrtsyCecgDffJGi95miWx16Hu1F1DEtw3tNnVWQKlIf9VB310O2-BLgNhOeygeAw5zXoOdSHwy3Qg-INUKc2ogHSxdekTgaM4XPbhuufhXT1Ez5gunO2J7ccxidAGmf9V](https://lh7-us.googleusercontent.com/slR2QMyPxkzDrtsyCecgDffJGi95miWx16Hu1F1DEtw3tNnVWQKlIf9VB310O2-BLgNhOeygeAw5zXoOdSHwy3Qg-INUKc2ogHSxdekTgaM4XPbhuufhXT1Ez5gunO2J7ccxidAGmf9V)

![https://lh7-us.googleusercontent.com/gkhkipK6xyJ5HlXTZ9BaVlQpDKdVRwgki3EMPgQ4CijnXM4ztwVVIDONkYvYdccBK3UNqakcHCZULCzLfuEENLkC8-KZKcqUt62FwgPdxmEk4SRCynlVUwv8rhNcUn6gRSEv7McvKkMn](https://lh7-us.googleusercontent.com/gkhkipK6xyJ5HlXTZ9BaVlQpDKdVRwgki3EMPgQ4CijnXM4ztwVVIDONkYvYdccBK3UNqakcHCZULCzLfuEENLkC8-KZKcqUt62FwgPdxmEk4SRCynlVUwv8rhNcUn6gRSEv7McvKkMn)

ko có quyền gì đặc biệt

![https://lh7-us.googleusercontent.com/KwVXel0M7_GXT--oIc6kiKKzfxbJeqb_dfLEkphwa7Z--LDNTAhUJREUcbEB60n5CCp0eJDXpuAbs23FcyADbWJSJpGJmWOgILQ-Wv5jboNqTetSARgEqqFabZCAdcoWksBWGCAN1K_E](https://lh7-us.googleusercontent.com/KwVXel0M7_GXT--oIc6kiKKzfxbJeqb_dfLEkphwa7Z--LDNTAhUJREUcbEB60n5CCp0eJDXpuAbs23FcyADbWJSJpGJmWOgILQ-Wv5jboNqTetSARgEqqFabZCAdcoWksBWGCAN1K_E)

![https://lh7-us.googleusercontent.com/4OIN9mFO2wgGAqIxDZGBXBBHH3ESzWk7FK77JMKFB-typfYbcq-ctvBoyU92xl_sm3AgD5VGJgTJ5LgUm5Rb2xf6hl-6bIBn63mQYjpAT1QYj_TMu60N4wVx2dgdnztqkSRDxTTxjY56](https://lh7-us.googleusercontent.com/4OIN9mFO2wgGAqIxDZGBXBBHH3ESzWk7FK77JMKFB-typfYbcq-ctvBoyU92xl_sm3AgD5VGJgTJ5LgUm5Rb2xf6hl-6bIBn63mQYjpAT1QYj_TMu60N4wVx2dgdnztqkSRDxTTxjY56)

user svc_deploy có trong group LAPS_readers -> có thể truy cập và đọc thông tin từ laps

With LAPS, the DC manages the local administrator passwords for computers on the domain. It is common to create a group of users and give them permissions to read these passwords, allowing the trusted administrators access to all the local admin passwords.

dùng Get-ADComputer với thuộc tính  ms-mcs-admpwd để đọc laps pw

Get-ADComputer DC01 -property 'ms-mcs-admpwd'

![https://lh7-us.googleusercontent.com/PG5Op6oIn9zZwJUOpO3jVC3yaSDMSXka5aASAxmb_x4jNXs6QUvMoIwpBO2wy013nqXHNLWqbbPvXePZ-HdPOlbxythhvSE2GSFnJJhqcsk4StMGYikr6f_BbdcSgC3-c5aX7IbIHiH_](https://lh7-us.googleusercontent.com/PG5Op6oIn9zZwJUOpO3jVC3yaSDMSXka5aASAxmb_x4jNXs6QUvMoIwpBO2wy013nqXHNLWqbbPvXePZ-HdPOlbxythhvSE2GSFnJJhqcsk4StMGYikr6f_BbdcSgC3-c5aX7IbIHiH_)

![https://lh7-us.googleusercontent.com/0VkWxFe69WjJPUy-7sSvjiavrIZzsl8Bk0IOfNrFZvEMZBuCwucMXpmURZ9enXRRk66XcziczLuVvxkqa6Bu-7gBRQKGIMhhi-qYoOA9B-1KZhtizO70EJ0vGO8QYvlqCSMeg3V72TUk](https://lh7-us.googleusercontent.com/0VkWxFe69WjJPUy-7sSvjiavrIZzsl8Bk0IOfNrFZvEMZBuCwucMXpmURZ9enXRRk66XcziczLuVvxkqa6Bu-7gBRQKGIMhhi-qYoOA9B-1KZhtizO70EJ0vGO8QYvlqCSMeg3V72TUk)

lấy flag root

![https://lh7-us.googleusercontent.com/fbdIzNEgJFLiTmL65szVgMK_k2dIK9JOPZTEFQ4gsoCylBSMxSqOHaE66CgvxHeCCVbw3_9FApaPDwuqOlAHrDhImv09cJ-dGduckJ9UT8ua2xBfWJD3NMD9ewtKOJRzBxPoZbZ_xcCC](https://lh7-us.googleusercontent.com/fbdIzNEgJFLiTmL65szVgMK_k2dIK9JOPZTEFQ4gsoCylBSMxSqOHaE66CgvxHeCCVbw3_9FApaPDwuqOlAHrDhImv09cJ-dGduckJ9UT8ua2xBfWJD3NMD9ewtKOJRzBxPoZbZ_xcCC)