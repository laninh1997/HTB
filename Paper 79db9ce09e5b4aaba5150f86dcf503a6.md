# Jerry

![https://lh7-us.googleusercontent.com/o41mVyhHg-s267WA83rLpPd0V2KghXQxg7FkbFIdjPH3ytVYsGM1jeVvu21b1VWedw_MPFPzQjqCcHAqDWgWHcXCJWqecCQ5KKxvZ7yy-39t6yKJ-JLkhzJPH5SZMZ0poOx8ZALRbXsz](https://lh7-us.googleusercontent.com/o41mVyhHg-s267WA83rLpPd0V2KghXQxg7FkbFIdjPH3ytVYsGM1jeVvu21b1VWedw_MPFPzQjqCcHAqDWgWHcXCJWqecCQ5KKxvZ7yy-39t6yKJ-JLkhzJPH5SZMZ0poOx8ZALRbXsz)

dùng curl hoặc

từ burpsuite thấy trường X-Backend-Server (ko phổ biến) có giá trị như vhost domain -> webserver sử dụng virtual host routing

![https://lh7-us.googleusercontent.com/ptRVnroJXF4jedgIlgm_DOo4XcHxu1jK86WTPIPm0SZIMaY99KvpI7SnCTuyoTScFQam4Qch3B5l1hd9tG8Ybq0tEjOmap8C-E-UvjvYTaX2mjuAqiBElvYwpVq_HgDv2rVZDlH6FnSS](https://lh7-us.googleusercontent.com/ptRVnroJXF4jedgIlgm_DOo4XcHxu1jK86WTPIPm0SZIMaY99KvpI7SnCTuyoTScFQam4Qch3B5l1hd9tG8Ybq0tEjOmap8C-E-UvjvYTaX2mjuAqiBElvYwpVq_HgDv2rVZDlH6FnSS)

→  lưu vào /etc/hosts

dùng wfuzz tìm subdomain

![https://lh7-us.googleusercontent.com/1yZQKPwZZ40mqkeLj26XhECvw-qdRtJkEcpBH-Cv8zsKUbfIANxRS5APsATkz1nJnWDpYrL_fwSCBbvkdosqHiZv0f-je7CrDD0HUpkPk51E6UnqpR2yceg3w2Jnqs_XFtMiZVkg-M62](https://lh7-us.googleusercontent.com/1yZQKPwZZ40mqkeLj26XhECvw-qdRtJkEcpBH-Cv8zsKUbfIANxRS5APsATkz1nJnWDpYrL_fwSCBbvkdosqHiZv0f-je7CrDD0HUpkPk51E6UnqpR2yceg3w2Jnqs_XFtMiZVkg-M62)

truy cập thấy link login, nhưng cần secret url ~ session mới đăng ký đc

truy cập domain gốc

![https://lh7-us.googleusercontent.com/2s9zu3EZ_LX5Nxf-wdKDjMaVz24dizVsSDVCNTpNpXRs6ukoXnu0095N2vjTb9awmwwCQHlfpFaANbiTz1HKK8EA0akEQYAD4xWz5Kg923NBsNNVruagPpArLA95xL4pqJEQs3b5bBVP](https://lh7-us.googleusercontent.com/2s9zu3EZ_LX5Nxf-wdKDjMaVz24dizVsSDVCNTpNpXRs6ukoXnu0095N2vjTb9awmwwCQHlfpFaANbiTz1HKK8EA0akEQYAD4xWz5Kg923NBsNNVruagPpArLA95xL4pqJEQs3b5bBVP)

thấy 1 comment hữu ích (có thông tin ở bản nháp cần xóa)

![https://lh7-us.googleusercontent.com/D1EpNfJR0ZrhuLvub7YGAN0O3-tr4dKohyYOsveu-80m_skfwYPNYlb41Xjv5IonISzjCDylPDabIIxUZcvEmqwXNTA2XaHAtSAQamHeTW_PJ3LhV2BpBJXu0DNHG2PYJSNvqS9sSsCx](https://lh7-us.googleusercontent.com/D1EpNfJR0ZrhuLvub7YGAN0O3-tr4dKohyYOsveu-80m_skfwYPNYlb41Xjv5IonISzjCDylPDabIIxUZcvEmqwXNTA2XaHAtSAQamHeTW_PJ3LhV2BpBJXu0DNHG2PYJSNvqS9sSsCx)

sd wappalyzer kiểm tra version của ứng dụng

![https://lh7-us.googleusercontent.com/hxYGHRAS5VvB6l6vaWVdMCsEN1jlePpq8_VPzTnUa1bPgNNXQdehhI4LSmnVTS-qMz1mnRpxLLShogXC36znW9g8aU5UILPP35NyS_bfDGWTZeOLvc4pGci5JIDJEnwkZvJFoBlYg_0M](https://lh7-us.googleusercontent.com/hxYGHRAS5VvB6l6vaWVdMCsEN1jlePpq8_VPzTnUa1bPgNNXQdehhI4LSmnVTS-qMz1mnRpxLLShogXC36znW9g8aU5UILPP35NyS_bfDGWTZeOLvc4pGci5JIDJEnwkZvJFoBlYg_0M)

[Proof of Concept for "Wordpress <=5.2.3: viewing unauthenticated posts" (CVE-2019-17671) | Sebastian Neef - 0day.work](https://0day.work/proof-of-concept-for-wordpress-5-2-3-viewing-unauthenticated-posts/)

![https://lh7-us.googleusercontent.com/pkl8fl8bnyVGrm5aoiHoiSIABM2gg34vJhPg51DCY90NIpiLf0RfBf4UOCubadqnV7MrTFyeUyC0VyqSQLh_2qS_jB-wQj_8X_j0xiy3nJ-HKRfs079jAeTh2m4tM9NPmjJVGX2QjHNu](https://lh7-us.googleusercontent.com/pkl8fl8bnyVGrm5aoiHoiSIABM2gg34vJhPg51DCY90NIpiLf0RfBf4UOCubadqnV7MrTFyeUyC0VyqSQLh_2qS_jB-wQj_8X_j0xiy3nJ-HKRfs079jAeTh2m4tM9NPmjJVGX2QjHNu)

Thêm ?static=1 -> có thể đọc bản nháp mà ko cần quyền xác thực

![https://lh7-us.googleusercontent.com/2XPg0LB9npbX3DEXjdVFkKy6cK10vtVOiVB13xUpmvhDNzGOMDnz0j5-Csaors9xVbCfZznNXUJARPSBilK8iUWzNynaVqq6l9PVwKq-KCAxmZYbHzlhikOWDSIvcBGJFmWTZ6VI8cbU](https://lh7-us.googleusercontent.com/2XPg0LB9npbX3DEXjdVFkKy6cK10vtVOiVB13xUpmvhDNzGOMDnz0j5-Csaors9xVbCfZznNXUJARPSBilK8iUWzNynaVqq6l9PVwKq-KCAxmZYbHzlhikOWDSIvcBGJFmWTZ6VI8cbU)

thấy có secret registration url -> lưu subdomain vào /etc/hosts

truy cập theo url, ứng dụng là rocketchat

đăng ký 1 tk  mới g:[g@gmail.com](mailto:g@gmail.com):g

![https://lh7-us.googleusercontent.com/K1k8PFv9HOpnSvF5_m3S0bvssEmSM6Es7u5j41k4B29F8Vz3S7Rb6Hro37_N8ZIWuBohZunOYNnYlN_ZwY5RtJU2JSevKt0YSY4wYiB7zJFBOWw9eM_4oIry8GG8EtPbocrqEvXleGK0](https://lh7-us.googleusercontent.com/K1k8PFv9HOpnSvF5_m3S0bvssEmSM6Es7u5j41k4B29F8Vz3S7Rb6Hro37_N8ZIWuBohZunOYNnYlN_ZwY5RtJU2JSevKt0YSY4wYiB7zJFBOWw9eM_4oIry8GG8EtPbocrqEvXleGK0)

đăng nhập bằng tk trên

![https://lh7-us.googleusercontent.com/dH6fjjRGBtD8IbzqE-6FvCRDkQEBZ5AwQakUQygJxaBfiQJjwKk4ENqavNYjugcIhJqeWN1bznqirh6YVAgmwVUJP8QMxHkL7GCwycfM84TCA5nby2BZ7oG4jpP8pNyfbax-UApG81S1](https://lh7-us.googleusercontent.com/dH6fjjRGBtD8IbzqE-6FvCRDkQEBZ5AwQakUQygJxaBfiQJjwKk4ENqavNYjugcIhJqeWN1bznqirh6YVAgmwVUJP8QMxHkL7GCwycfM84TCA5nby2BZ7oG4jpP8pNyfbax-UApG81S1)

nội dung đoạn chat có nhắc đến 1 con bot recyclops

![https://lh7-us.googleusercontent.com/Yn7BXmyzx93czKVOMrGnGSK0PIQgpNOCGHP3Qn6AmaJZ9qMAXxU6RRzG1q3Rs5YaNQyXZdHlpN-np8Wjc464B9Wuc4ZRPyP0rSjdpEC-DaKudEUFt5IjA567Cn7eHw5saRHCzheUJYmh](https://lh7-us.googleusercontent.com/Yn7BXmyzx93czKVOMrGnGSK0PIQgpNOCGHP3Qn6AmaJZ9qMAXxU6RRzG1q3Rs5YaNQyXZdHlpN-np8Wjc464B9Wuc4ZRPyP0rSjdpEC-DaKudEUFt5IjA567Cn7eHw5saRHCzheUJYmh)

vì kênh genaral chỉ cho đọc nên tạo chat riêng với recyclops

![https://lh7-us.googleusercontent.com/7LzAzfLXh1Jv0gzc50xCsAiFSPeZpnmrcknOCYp6lSlju3oWHBcmcMGsBMCZ6XLq_RDPiKZpJrOMX7mYZjnEPGE1PdLCzXQPMzTPQN1DdVlXrLSbeYFFYbtrpFDOXcNXc88pl8Rj71QZ](https://lh7-us.googleusercontent.com/7LzAzfLXh1Jv0gzc50xCsAiFSPeZpnmrcknOCYp6lSlju3oWHBcmcMGsBMCZ6XLq_RDPiKZpJrOMX7mYZjnEPGE1PdLCzXQPMzTPQN1DdVlXrLSbeYFFYbtrpFDOXcNXc88pl8Rj71QZ)

hd dùng lệnh help thì có thể xem được các chức năng của con bot

How to use me ? :

1. Small Talk:

You can ask me how dwight's weekend was, or did he watched the game last night etc.

eg: 'recyclops how was your weekend?' or 'recyclops did you watched the game last night?' or 'recyclops what kind of bear is the best?

2. Joke:

You can ask me Why the salesman crossed the road.

eg: 'recyclops why did the salesman crossed the road?'

<=====The following two features are for those boneheads, who still don't know how to use scp. I'm Looking at you Kevin.=====>

**For security reasons, the access is limited to the Sales folder.**

**3. Files:**

**eg: 'recyclops get me the file test.txt', or 'recyclops could you send me the file src/test.php' or just 'recyclops file test.txt'**

**4. List:**

**You can ask me to list the files**

5. Time:

You can ask me to what the time is

eg: 'recyclops what time is it?' or just 'recyclops time'

giới hạn truy cập ở folder Sales, có thể dùng lệnh list để liệt kê, file để đọc file

thử command injection mà ko ok nên thử path traversal

![https://lh7-us.googleusercontent.com/czwDbzHDUl0U-Xx2JjtYHpREORqXvL_lKH0NNKL6VJhpaCI7s8STcnl99jCm44GogBlw_KUyjgOZRk7QtunV-ZG9a1TrJzHmXqLdNi3EUhCqlSBFjxo38kYyB-qiyXDkcB6r88xNJB5P](https://lh7-us.googleusercontent.com/czwDbzHDUl0U-Xx2JjtYHpREORqXvL_lKH0NNKL6VJhpaCI7s8STcnl99jCm44GogBlw_KUyjgOZRk7QtunV-ZG9a1TrJzHmXqLdNi3EUhCqlSBFjxo38kYyB-qiyXDkcB6r88xNJB5P)

trong thư mục sales ko thấy gì có ích, thử path traversal thấy thư mục hubot khả nghi

![https://lh7-us.googleusercontent.com/twuukyqSaeE-Iff3E3HPAcA2ynGAP3opXDOyFkbNm-plOzxGJhtxnpXBVNwDyKvUqJz78w__UY9jLYEC9wpExruqyW5znI3EXDgjJbRjDhNboccLEGTo7TamOA4Q0apcWLoaZv5DYRtR](https://lh7-us.googleusercontent.com/twuukyqSaeE-Iff3E3HPAcA2ynGAP3opXDOyFkbNm-plOzxGJhtxnpXBVNwDyKvUqJz78w__UY9jLYEC9wpExruqyW5znI3EXDgjJbRjDhNboccLEGTo7TamOA4Q0apcWLoaZv5DYRtR)

user.txt chỉ có quyền dwight mới đọc đc

![https://lh7-us.googleusercontent.com/bk64EkVPIad6uaZglKQ7kLIGewhzE_c0m06QoiqSu47ZtN8Q84Nt1eLPxYHV3J_CYvCo5pi_QwBfD4-AFYJm_gbtlszNCegsp9HrGxILVepFSbA4tw692TmbtjwOW240Bhxgeb7q9qhT](https://lh7-us.googleusercontent.com/bk64EkVPIad6uaZglKQ7kLIGewhzE_c0m06QoiqSu47ZtN8Q84Nt1eLPxYHV3J_CYvCo5pi_QwBfD4-AFYJm_gbtlszNCegsp9HrGxILVepFSbA4tw692TmbtjwOW240Bhxgeb7q9qhT)

cấu hình hubot đc lưu ở .env

![https://lh7-us.googleusercontent.com/W2mYqOr0ZHFFfTRi3oKtsJ0OMgCV6WJT53jxAJjlhdBmwoEWoMyCA5MkGuYEX32mlnYmHpFS6MpLg8_ybWrgFN-nbyn6JNalnBL5hA1a6Vze9_IAsMAKgpWhEP327DZCcd2OJllE3LSq](https://lh7-us.googleusercontent.com/W2mYqOr0ZHFFfTRi3oKtsJ0OMgCV6WJT53jxAJjlhdBmwoEWoMyCA5MkGuYEX32mlnYmHpFS6MpLg8_ybWrgFN-nbyn6JNalnBL5hA1a6Vze9_IAsMAKgpWhEP327DZCcd2OJllE3LSq)

vào thư mục hubot và thấy có .env

![https://lh7-us.googleusercontent.com/7lHOHRKRig66bak8xWS2eNwhW3_zOLWY8RbmKsoyP6h4Mo9TcjxakIsDuK2L_ixj-Sp47ESwW5G1Ub2plDyizwUkd8DHCEpjhzigA7EUUZ95o6FN9U--ZtJ8AvNdwq6XvEASwxBS8Ge-](https://lh7-us.googleusercontent.com/7lHOHRKRig66bak8xWS2eNwhW3_zOLWY8RbmKsoyP6h4Mo9TcjxakIsDuK2L_ixj-Sp47ESwW5G1Ub2plDyizwUkd8DHCEpjhzigA7EUUZ95o6FN9U--ZtJ8AvNdwq6XvEASwxBS8Ge-)

đọc nó và có đc mk Queenofblad3s!23

![https://lh7-us.googleusercontent.com/y-QPziZv8pPV4T5d3O6760hwEBwaUSohRJe4iWFnvQO-E3er2Bq6cbkePFhFJaAtOE3bw2e9rGzmR_m1QtzZzTLxGZJlQqnfz_6Eilfl34mtZNVrrlH0hf5ac1y7VMUrQiXQkkBMe614](https://lh7-us.googleusercontent.com/y-QPziZv8pPV4T5d3O6760hwEBwaUSohRJe4iWFnvQO-E3er2Bq6cbkePFhFJaAtOE3bw2e9rGzmR_m1QtzZzTLxGZJlQqnfz_6Eilfl34mtZNVrrlH0hf5ac1y7VMUrQiXQkkBMe614)

tìm user trên hệ thống

![https://lh7-us.googleusercontent.com/AOJ1MMEEQcSiutlqX3MwWKL1A1j8kr0_qSJfw-zTPqzyajBlE-Zx2PgqZ5Fch-55wh2-jKTHOP4oFkJC1v7u5yQv4pDMNb0PD6ExSXo4jOxzXjNCUThflRMsbw6hKy1HIHeREYDy5aHA](https://lh7-us.googleusercontent.com/AOJ1MMEEQcSiutlqX3MwWKL1A1j8kr0_qSJfw-zTPqzyajBlE-Zx2PgqZ5Fch-55wh2-jKTHOP4oFkJC1v7u5yQv4pDMNb0PD6ExSXo4jOxzXjNCUThflRMsbw6hKy1HIHeREYDy5aHA)

![https://lh7-us.googleusercontent.com/3e1c2shxu-dTx1rvMH0qBukFadJ9c06AKX3Vb1-bXJK-bPgY5jHFKpd85DomYQk9LOtcJlkuJHmByNmqeMF6SewRMRuaYKGDg7H6allt7iMvNHEsycLNAvDKRD185EQld3XAcSV9GNGx](https://lh7-us.googleusercontent.com/3e1c2shxu-dTx1rvMH0qBukFadJ9c06AKX3Vb1-bXJK-bPgY5jHFKpd85DomYQk9LOtcJlkuJHmByNmqeMF6SewRMRuaYKGDg7H6allt7iMvNHEsycLNAvDKRD185EQld3XAcSV9GNGx)

dùng mật khẩu vừa lấy được để ssh đến 2 user thông thường là rocketchat và dwight

thấy mk thành công với dwight

![https://lh7-us.googleusercontent.com/0-VV7_Krq5adIUxnaVX4meUnmHdX-qCj-5uKPwPJuZYuUbgBUuH1wyiGCgTEDqAgXdXhJ1uM3Lj26KYTsCf16dPi3UhoQT8maoDl3Fy-0Uort9aiR8bat2iHGDdoxv8LERjllAH1WcPJ](https://lh7-us.googleusercontent.com/0-VV7_Krq5adIUxnaVX4meUnmHdX-qCj-5uKPwPJuZYuUbgBUuH1wyiGCgTEDqAgXdXhJ1uM3Lj26KYTsCf16dPi3UhoQT8maoDl3Fy-0Uort9aiR8bat2iHGDdoxv8LERjllAH1WcPJ)

![https://lh7-us.googleusercontent.com/m9eQVFMhMnOxJw2Mf19i9ECP_ae5iyeeMtrI_Zvf3LGEmHDz99-sKkGbzF1nupAC-t2bgKql-aPyLoxvyPtmW9dszT9liDJFj7_Jg6iswwXJL1tUWhxL-lhXiuKB_eBktnMtyKR-JpoE](https://lh7-us.googleusercontent.com/m9eQVFMhMnOxJw2Mf19i9ECP_ae5iyeeMtrI_Zvf3LGEmHDz99-sKkGbzF1nupAC-t2bgKql-aPyLoxvyPtmW9dszT9liDJFj7_Jg6iswwXJL1tUWhxL-lhXiuKB_eBktnMtyKR-JpoE)

LinPEAS is a script that search for possible paths to escalate privileges on Linux/Unix*/MacOS hosts.

tải linpeas.sh [Release Release refs/heads/master 20220612 · carlospolop/PEASS-ng (github.com)](https://github.com/carlospolop/PEASS-ng/releases/tag/20220612) về máy mình

file linpeas.sh ở link trên khác nd với search .sh trên google, hoặc tải peas-ng về chạy

tại thư mục chứa linpeas.sh, tạo 1 server. đồng thời bên shell dwight sử dụng wget để tải linpeas.sh từ server hacker xuống

![https://lh7-us.googleusercontent.com/YYa9uOogBOPrfxlNJ_6vMXFql9DIBT5yLxkFpiwjF5QMtslNNqM7_Dd0Gl79500HVivO0pf1UZdwJJmgRfnOywjIOwVgUqBOAq0VF0Ah8C7UdbSiBHWYRv8dMs2yEOAJ6HEC3AiZvv3p](https://lh7-us.googleusercontent.com/YYa9uOogBOPrfxlNJ_6vMXFql9DIBT5yLxkFpiwjF5QMtslNNqM7_Dd0Gl79500HVivO0pf1UZdwJJmgRfnOywjIOwVgUqBOAq0VF0Ah8C7UdbSiBHWYRv8dMs2yEOAJ6HEC3AiZvv3p)

![https://lh7-us.googleusercontent.com/qY9sxrPe31maej7jf9P9SweVsv621fGtsfBJRq0jdLaWZJ117OQHLJPyKPtZ0c0ZR6MeK-_FU0ZPpJoXN1BvcjjQjx-9XM61b10UhP2qk8dDCGtnIKyKHKWpAFzeWwjOJC4SaZXCRX1m](https://lh7-us.googleusercontent.com/qY9sxrPe31maej7jf9P9SweVsv621fGtsfBJRq0jdLaWZJ117OQHLJPyKPtZ0c0ZR6MeK-_FU0ZPpJoXN1BvcjjQjx-9XM61b10UhP2qk8dDCGtnIKyKHKWpAFzeWwjOJC4SaZXCRX1m)

![https://lh7-us.googleusercontent.com/0xflh1_ZqyULSbHXeAxsVTe0mWqTC8EHqO8hifugTWHrl6mBOwFyXyPIEjguCw7o9bdC4s-RtLQ9VR9AI9dwbnQoF8POmaLe_fTx_eoTQs1QYtyAukLj2Gmoz1o2XsLWsmAJjyp06CWI](https://lh7-us.googleusercontent.com/0xflh1_ZqyULSbHXeAxsVTe0mWqTC8EHqO8hifugTWHrl6mBOwFyXyPIEjguCw7o9bdC4s-RtLQ9VR9AI9dwbnQoF8POmaLe_fTx_eoTQs1QYtyAukLj2Gmoz1o2XsLWsmAJjyp06CWI)

Trong Linux, polkit là một dịch vụ ủy quyền được sử dụng để cho phép các quy trình không có đặc quyền giao tiếp với các quy trình đặc quyền. Khi một người dùng hoặc quy trình có đặc quyền thấp muốn truy cập các tài nguyên yêu cầu đặc quyền cao hơn, dịch vụ ủy quyền polkit sẽ đưa ra quyết định cho phép hoặc từ chối ở hậu trường hoặc nhắc hộp thoại nhận thêm ủy quyền trước khi cấp các đặc quyền cần thiết.

CVE-2021-3560 là lỗ hổng bỏ qua xác thực cho phép người dùng thông thường nâng cao đặc quyền của mình lên đặc quyền của người dùng root. Lỗ hổng này có thể được người dùng cục bộ không có đặc quyền sử dụng để tạo quản trị viên cục bộ mới, dẫn đến sự xâm phạm hoàn toàn hệ thống.

![https://lh7-us.googleusercontent.com/ItG_1LAaTqjgmU4DIXIjIG1ecx09rrnmRFNdLdF93cG4RlsksBMo9b0DfK78uf-K3pAoO7O7gmZ-8k8-WeTqbMgmWxZyonZYxk_JOKy94pCgWosrBnuPXWxysmWttlQG7lR3Y8VPXxl7](https://lh7-us.googleusercontent.com/ItG_1LAaTqjgmU4DIXIjIG1ecx09rrnmRFNdLdF93cG4RlsksBMo9b0DfK78uf-K3pAoO7O7gmZ-8k8-WeTqbMgmWxZyonZYxk_JOKy94pCgWosrBnuPXWxysmWttlQG7lR3Y8VPXxl7)

thay đổi username, passwd

![https://lh7-us.googleusercontent.com/rc7InD4otV9rLzRRCfRPKWotzxPKQGOBCJyNT8G1XYMmDxIext3VlBZ9feRa-1qs3FYMN8dURyG-3VR8Bhp4yL6XxfSVDqWtcDLhWK9AyCwsjnbjioJGZWOebNvB0glnYRVqMowoxnWj](https://lh7-us.googleusercontent.com/rc7InD4otV9rLzRRCfRPKWotzxPKQGOBCJyNT8G1XYMmDxIext3VlBZ9feRa-1qs3FYMN8dURyG-3VR8Bhp4yL6XxfSVDqWtcDLhWK9AyCwsjnbjioJGZWOebNvB0glnYRVqMowoxnWj)

chạy bash poc.sh nhiều lần, và kiểm tra xem user đã được tạo chưa

![https://lh7-us.googleusercontent.com/RZBFpVNaFKz888Q9vKjsyirwqAyHu0Npfwc11rOXiJpfw5G6X3zcGHfsNdJNsBUOwtHhplUcApAXtiUI9fRGVaAMEJZz7OCkPdcPJ7VC4iyLbBYNyJgI356e5K4Oqek2-dgcItJxvWYg](https://lh7-us.googleusercontent.com/RZBFpVNaFKz888Q9vKjsyirwqAyHu0Npfwc11rOXiJpfw5G6X3zcGHfsNdJNsBUOwtHhplUcApAXtiUI9fRGVaAMEJZz7OCkPdcPJ7VC4iyLbBYNyJgI356e5K4Oqek2-dgcItJxvWYg)

tạo đc và rất nhanh bị xóa

This attack is a timing attack against polkit, and by killing the process at the right time, it ends up skipping the authentication and allow actions such as creating an account with sudo privs and setting the password..

![https://lh7-us.googleusercontent.com/lc67__PQ5JzrwklMnoy_m9IpN0Ss_QRm9EC8F2JUzPhq7Mho63kN58Im3R14EqWPeJ2OyrYpRa31zfS1B0ohJPbGP7ouoYGADP0tZfuQILtzIn1KE1Ix9oc7F-1Pz2yqeVjnG1vt2gyE](https://lh7-us.googleusercontent.com/lc67__PQ5JzrwklMnoy_m9IpN0Ss_QRm9EC8F2JUzPhq7Mho63kN58Im3R14EqWPeJ2OyrYpRa31zfS1B0ohJPbGP7ouoYGADP0tZfuQILtzIn1KE1Ix9oc7F-1Pz2yqeVjnG1vt2gyE)

![https://lh7-us.googleusercontent.com/fKGg1fGoURNzhwIAzdWaxnnrZ-UIup2Royf81nPt_G3we_wd7hmQAonQZIQ_RVzgM1vfmK972yrsuWd8sGoOA3jbPFvpsXU05BewqB19ZhIBLskA-ShClHt7mOZNeNAUxWPSrEP4fS-n](https://lh7-us.googleusercontent.com/fKGg1fGoURNzhwIAzdWaxnnrZ-UIup2Royf81nPt_G3we_wd7hmQAonQZIQ_RVzgM1vfmK972yrsuWd8sGoOA3jbPFvpsXU05BewqB19ZhIBLskA-ShClHt7mOZNeNAUxWPSrEP4fS-n)

![https://lh7-us.googleusercontent.com/24u7Wk8NvNj6Oxix7nigOHuMF90N2DcMXVm5Jt66pIsEi1JOc4ucn4ahFL_bOfwL2k2AaeMzOdP9ItczXFi55QouzMIl0lFvdSghTqGb278zlWgcARKHYYU7tJ07RWrXS2qgkQnfqJLI](https://lh7-us.googleusercontent.com/24u7Wk8NvNj6Oxix7nigOHuMF90N2DcMXVm5Jt66pIsEi1JOc4ucn4ahFL_bOfwL2k2AaeMzOdP9ItczXFi55QouzMIl0lFvdSghTqGb278zlWgcARKHYYU7tJ07RWrXS2qgkQnfqJLI)

![https://lh7-us.googleusercontent.com/QY5v9QbgvHGLkOKcfCI47ccXTDSDiWosmgjzRxzrh56BsbP8dkPt32wIDU-5vUfuzSB6XxsEAiuYI_vNDUbid0dgphR5rc_jbavDxdTv-6YDpRoyGBSVuzGGFIGUZ8Ol6YGJmN2niBmW](https://lh7-us.googleusercontent.com/QY5v9QbgvHGLkOKcfCI47ccXTDSDiWosmgjzRxzrh56BsbP8dkPt32wIDU-5vUfuzSB6XxsEAiuYI_vNDUbid0dgphR5rc_jbavDxdTv-6YDpRoyGBSVuzGGFIGUZ8Ol6YGJmN2niBmW)