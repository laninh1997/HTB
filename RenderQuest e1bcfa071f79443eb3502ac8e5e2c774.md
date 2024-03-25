# RenderQuest

ngrok: [https://henri-demanou.medium.com/htb-renderquest-3fa19d67f58d](https://henri-demanou.medium.com/htb-renderquest-3fa19d67f58d)

[https://medium.com/@tanish.saxena26/hackthebox-renderquest-cf6c493d7b83](https://medium.com/@tanish.saxena26/hackthebox-renderquest-cf6c493d7b83)

[Webhook.site - Test, process and transform emails and HTTP requests](https://webhook.site/#!/view/f20f94fc-67c6-4440-aa8e-477efa765ecf)

edit content(chèn payload), nhưng vẫn giữ nguyên url

phân tích code: trong main.go có 2 end point /render và /static

chú ý xử lý các request đến /render có hàm getTpl()

![https://lh7-us.googleusercontent.com/YjpXKkl2NV782alSGc3bHtBwEvoo65gweVOYHvy8gq-Odt8qqP79ltM7jOOa0hupB2MhEQiTomJidhwe4YM0G7lJ72lxzkgdUwkjVXiIlzxr5Uu9lnL-PEK_nxiugpykWr6o_X1IQ-nZ](https://lh7-us.googleusercontent.com/YjpXKkl2NV782alSGc3bHtBwEvoo65gweVOYHvy8gq-Odt8qqP79ltM7jOOa0hupB2MhEQiTomJidhwe4YM0G7lJ72lxzkgdUwkjVXiIlzxr5Uu9lnL-PEK_nxiugpykWr6o_X1IQ-nZ)

hàm getTpl có 2 tham số page và use_remote

![https://lh7-us.googleusercontent.com/zqd877fEDDMvPCDgfnRth0WmleI9oUGkbRJuv49g43WHn7AI92bWavLNIpsGCN4eS-d1tXeHMWtOy1sBPAmemQNknOVYibcyHo2yii8Pbo8UbVfZPqE5qKxer_NomNUQSHW1OQrPTxmM](https://lh7-us.googleusercontent.com/zqd877fEDDMvPCDgfnRth0WmleI9oUGkbRJuv49g43WHn7AI92bWavLNIpsGCN4eS-d1tXeHMWtOy1sBPAmemQNknOVYibcyHo2yii8Pbo8UbVfZPqE5qKxer_NomNUQSHW1OQrPTxmM)

trong đó tìm nạp tài nguyên mà ko làm sạch hay kiểm tra gì từ tham số page~ đọc nd file từ xa

![https://lh7-us.googleusercontent.com/PmxRWGJvt45HIEmdM3vffSNnZw5kXM_b1vQRkPq1qhAlMqUAE1TDNISQW0GwHsARSuzRoilRjkLZ0sPfZvZ9xcp-g4mO8vHl9rHRRq5flBJ6Wz7cPJBRR7oX8vq4V05BvIdZ8aMbqk71](https://lh7-us.googleusercontent.com/PmxRWGJvt45HIEmdM3vffSNnZw5kXM_b1vQRkPq1qhAlMqUAE1TDNISQW0GwHsARSuzRoilRjkLZ0sPfZvZ9xcp-g4mO8vHl9rHRRq5flBJ6Wz7cPJBRR7oX8vq4V05BvIdZ8aMbqk71)

sau đó tạo mới template từ tham số page

![https://lh7-us.googleusercontent.com/siGXSD6a3X5_fwla-lJLnM9yCbX9gUzFMd5PjhP5u7C88lusaZAgJKlj8IQrvdutR9RbvIT7gDik323BnxcoXZFU67ACw0O2w_cPbe4n_cn1ysoSN1FkcMr2mFq8SmDoo6nPWHvd_a_e](https://lh7-us.googleusercontent.com/siGXSD6a3X5_fwla-lJLnM9yCbX9gUzFMd5PjhP5u7C88lusaZAgJKlj8IQrvdutR9RbvIT7gDik323BnxcoXZFU67ACw0O2w_cPbe4n_cn1ysoSN1FkcMr2mFq8SmDoo6nPWHvd_a_e)

→ ssti

trong main.go có hàm FetchServerInfo() có thể thực thi lệnh

![https://lh7-us.googleusercontent.com/Y6NXjHPypsFcwMJEQy4mWuYhHVl3Mpuj9_tijGM2i5FGsoxdnKSJ4QZq84cFFI_y28QQf-lIW2BaDc1-rvBhA61Rq0vToBKNZJxKArZnUYiBCGJkWXw2vGlrk7Njopv0B2fVf82tAS89](https://lh7-us.googleusercontent.com/Y6NXjHPypsFcwMJEQy4mWuYhHVl3Mpuj9_tijGM2i5FGsoxdnKSJ4QZq84cFFI_y28QQf-lIW2BaDc1-rvBhA61Rq0vToBKNZJxKArZnUYiBCGJkWXw2vGlrk7Njopv0B2fVf82tAS89)

dùng hàm này trong payload

**c1:** dùng ngrok

tại thư mục tạo file chứa payload

tạo 1 web server với p1234

![https://lh7-us.googleusercontent.com/aYfxjoQYNR-DNV0rHQ0cnsZUhsMaZkxL7c7IvgGUsv99f253jUJlr7hKx6O1fd1EiWPVjVn7mMGDYj9qK1-hSq_UoYvIEW2y00lUFKWiPGR8i2qg72WPtnXp-ONjBc8tos35OAyj1wg6](https://lh7-us.googleusercontent.com/aYfxjoQYNR-DNV0rHQ0cnsZUhsMaZkxL7c7IvgGUsv99f253jUJlr7hKx6O1fd1EiWPVjVn7mMGDYj9qK1-hSq_UoYvIEW2y00lUFKWiPGR8i2qg72WPtnXp-ONjBc8tos35OAyj1wg6)

chạy Ngrok tạo url và tunnel đến p1234 ngrok http http://localhost:1234

![https://lh7-us.googleusercontent.com/PJV749afshGW9gqtiwvYIprn2tDedHgttJ4w0Fhi_qJs3fF49oSjlq3HRElh1Vz-_IUmlErNGoqPOPZiCMeRmWivpQqcKML4GjC2MCfYUNvov-s9nW9A---Dq5s0Y46MGemw993kxKso](https://lh7-us.googleusercontent.com/PJV749afshGW9gqtiwvYIprn2tDedHgttJ4w0Fhi_qJs3fF49oSjlq3HRElh1Vz-_IUmlErNGoqPOPZiCMeRmWivpQqcKML4GjC2MCfYUNvov-s9nW9A---Dq5s0Y46MGemw993kxKso)

cung cấp link để gửi yêu cầu đến Ngrok và thực thi payload

![https://lh7-us.googleusercontent.com/I08fVvKeyGSFSn8446LZBk5o_ps7SlvwVjsUuKCl4R9MR8ylPLCGHVqeOWDiDoqIjumfcdAT1mmU5srEAiyp3y2aleYr0ffvg2aedzeYnGCrTTS060HN4OqvV8ZJgt9c4uyYnXckQZiH](https://lh7-us.googleusercontent.com/I08fVvKeyGSFSn8446LZBk5o_ps7SlvwVjsUuKCl4R9MR8ylPLCGHVqeOWDiDoqIjumfcdAT1mmU5srEAiyp3y2aleYr0ffvg2aedzeYnGCrTTS060HN4OqvV8ZJgt9c4uyYnXckQZiH)

sau đó chỉ cần thay đổi payload để lấy đc flag(gửi request ko cần thay đổi url)

![https://lh7-us.googleusercontent.com/5h2msmSu-29YoFJGvCevU1Iwmz-SPrvOBQID4jJC0PYsjggStjBnYcJZEQm3Vaf4wk_XCfnx0Q0IFhricK0QUm66afSsBNZ89kEb1DkncNLoFDIhJKWwNm-NFSMWvSvuWcnYYr07HGwU](https://lh7-us.googleusercontent.com/5h2msmSu-29YoFJGvCevU1Iwmz-SPrvOBQID4jJC0PYsjggStjBnYcJZEQm3Vaf4wk_XCfnx0Q0IFhricK0QUm66afSsBNZ89kEb1DkncNLoFDIhJKWwNm-NFSMWvSvuWcnYYr07HGwU)

![https://lh7-us.googleusercontent.com/xL7KaT_nG-VJrhvGAXM0A-abi6oqkyYX9zhis2KmiXFwIck7g8MeKcW2BzVJintu-6T177YEo0FiA3He3-aRItdZr1CVQ0xacF3xexDHUCI2np-KzXnpiQwJz8jpI4ITazzHxk8lkuGe](https://lh7-us.googleusercontent.com/xL7KaT_nG-VJrhvGAXM0A-abi6oqkyYX9zhis2KmiXFwIck7g8MeKcW2BzVJintu-6T177YEo0FiA3He3-aRItdZr1CVQ0xacF3xexDHUCI2np-KzXnpiQwJz8jpI4ITazzHxk8lkuGe)

![https://lh7-us.googleusercontent.com/NdSNzNXe67VuU2DvcWDKwSWX3hDo824slX7HtcmBvam9-8Leby0b4XQV3nuSCsIejc8h4N05H4oDOjXAYE0dbC7uqB4rdxhPtO18ZOeFB-ZFKNxZzpcQN7beebppRFSX4rH5PER6gsgB](https://lh7-us.googleusercontent.com/NdSNzNXe67VuU2DvcWDKwSWX3hDo824slX7HtcmBvam9-8Leby0b4XQV3nuSCsIejc8h4N05H4oDOjXAYE0dbC7uqB4rdxhPtO18ZOeFB-ZFKNxZzpcQN7beebppRFSX4rH5PER6gsgB)

![https://lh7-us.googleusercontent.com/j7Y9XY8kzvm8Vkk1mpScgyXazLa1rsN-7izC53HoeY3GJ8oBKoG0Vf6V15a9yCo_mPwNbVmDT7jv3jEawq5PKVlFjSU-R8B6tK8mdxQChkxpjhAgK7SeVrlFets0Slp6ri3OOrYeDyRE](https://lh7-us.googleusercontent.com/j7Y9XY8kzvm8Vkk1mpScgyXazLa1rsN-7izC53HoeY3GJ8oBKoG0Vf6V15a9yCo_mPwNbVmDT7jv3jEawq5PKVlFjSU-R8B6tK8mdxQChkxpjhAgK7SeVrlFets0Slp6ri3OOrYeDyRE)

log localhost và Ngrok ghi lại

![https://lh7-us.googleusercontent.com/ReWPZexG8AXoWaHzWvIJlulVYMQOFCnXwCPa3Xu8wxQADeOJw0nJC_jzeW9DsioUTpM5HRBUJYouOZ8vCRSoxWnw8duR7zTkouiPvnjPWus4MLF2QfoxV_pVCVfd2CU1-cPe4BwMJAjf](https://lh7-us.googleusercontent.com/ReWPZexG8AXoWaHzWvIJlulVYMQOFCnXwCPa3Xu8wxQADeOJw0nJC_jzeW9DsioUTpM5HRBUJYouOZ8vCRSoxWnw8duR7zTkouiPvnjPWus4MLF2QfoxV_pVCVfd2CU1-cPe4BwMJAjf)

**c2:** dùng webhook.site

thử render 1 trang như google

![https://lh7-us.googleusercontent.com/Nxp-BSEOxD8iu1-t4qkPPF5_P9HNyp_Fvhshs0EVoa1XQ6J8gs12ZcMPnejBL6CvF97kgX1E1lLaZ88FQhoLYbANGkdZaWYiRDWdE5lIQpHT5Z7laGhA8aq1qvG6VEA10py_3Nlq26ra](https://lh7-us.googleusercontent.com/Nxp-BSEOxD8iu1-t4qkPPF5_P9HNyp_Fvhshs0EVoa1XQ6J8gs12ZcMPnejBL6CvF97kgX1E1lLaZ88FQhoLYbANGkdZaWYiRDWdE5lIQpHT5Z7laGhA8aq1qvG6VEA10py_3Nlq26ra)

trong main.go có hàm FetchServerInfo() có thể thực thi lệnh

![https://lh7-us.googleusercontent.com/Y6NXjHPypsFcwMJEQy4mWuYhHVl3Mpuj9_tijGM2i5FGsoxdnKSJ4QZq84cFFI_y28QQf-lIW2BaDc1-rvBhA61Rq0vToBKNZJxKArZnUYiBCGJkWXw2vGlrk7Njopv0B2fVf82tAS89](https://lh7-us.googleusercontent.com/Y6NXjHPypsFcwMJEQy4mWuYhHVl3Mpuj9_tijGM2i5FGsoxdnKSJ4QZq84cFFI_y28QQf-lIW2BaDc1-rvBhA61Rq0vToBKNZJxKArZnUYiBCGJkWXw2vGlrk7Njopv0B2fVf82tAS89)

sử dụng webhook.site để tạo url chứa payload

![https://lh7-us.googleusercontent.com/w8IEBJF6U3Mk-jK_97HJIWDZnT6A4NAzvlt3GiX_urv6Uhy_i-Tmib-qiTsenPXChPouhlxVJG6FKDmV68qweJ2sPJ4HSn0Ak_N-y6EbWC3RKEqXLCVs1snF9DgMUtRSaz3zbfv3To0v](https://lh7-us.googleusercontent.com/w8IEBJF6U3Mk-jK_97HJIWDZnT6A4NAzvlt3GiX_urv6Uhy_i-Tmib-qiTsenPXChPouhlxVJG6FKDmV68qweJ2sPJ4HSn0Ak_N-y6EbWC3RKEqXLCVs1snF9DgMUtRSaz3zbfv3To0v)

![https://lh7-us.googleusercontent.com/fprrtg7UbjpbdtGLIJIeOGCbt5-e9pYtgzIJlNjcH7azey-TkyO2QC3qRN1wub5nt07CfCGuiuSGlHtPZyXAvKl2pMa5deLQoLtjt--orlne6da6qChu47_F2agu097DTPk1VoSsQz39](https://lh7-us.googleusercontent.com/fprrtg7UbjpbdtGLIJIeOGCbt5-e9pYtgzIJlNjcH7azey-TkyO2QC3qRN1wub5nt07CfCGuiuSGlHtPZyXAvKl2pMa5deLQoLtjt--orlne6da6qChu47_F2agu097DTPk1VoSsQz39)

![https://lh7-us.googleusercontent.com/uidub1XV3wLZXh7MCDLbkxRDU_QM8vdGISeycN-TMwg5aw14vr6qYUk0UEp990h22Ys2bGpn1bel_BTYZsq4mmh0yEHGQecYmJaIO2S832QfFywCTD3Mn9R22r6xO7G1lkiJb3_PeGHt](https://lh7-us.googleusercontent.com/uidub1XV3wLZXh7MCDLbkxRDU_QM8vdGISeycN-TMwg5aw14vr6qYUk0UEp990h22Ys2bGpn1bel_BTYZsq4mmh0yEHGQecYmJaIO2S832QfFywCTD3Mn9R22r6xO7G1lkiJb3_PeGHt)

{{.FetchServerInfo "ls -la ../"}}

sửa content nhưng url được cung cấp vẫn giữ nguyên

![https://lh7-us.googleusercontent.com/hdg70_gCbRPShWLq7_cIx8rvS_VTMdFtDfDxCebXBtg-vFfIMbjKI9YM8SS5wTsUJ7nWRW9-V1wIYY9HOwhQEglMrzsJIGktvafpFOM1jiy3up3PVNEj7mC6AJT5iCpduCF9UtECqQbw](https://lh7-us.googleusercontent.com/hdg70_gCbRPShWLq7_cIx8rvS_VTMdFtDfDxCebXBtg-vFfIMbjKI9YM8SS5wTsUJ7nWRW9-V1wIYY9HOwhQEglMrzsJIGktvafpFOM1jiy3up3PVNEj7mC6AJT5iCpduCF9UtECqQbw)

{{.FetchServerInfo "cat ../flag6ab8c70350.txt"}}

![https://lh7-us.googleusercontent.com/VcE_U46yg8RRb6sIOrOcNv7GU57LOFv3My5zWCqbp5QSa_m18BRK2hHbUmf7Yk8nGVpVOAEkiMEZnaVhVo8K0d-Wyajy9HUuH-d8M9HTsbIJee3_jSTuCUl719NfjSahQ6tQ-JnqlRxV](https://lh7-us.googleusercontent.com/VcE_U46yg8RRb6sIOrOcNv7GU57LOFv3My5zWCqbp5QSa_m18BRK2hHbUmf7Yk8nGVpVOAEkiMEZnaVhVo8K0d-Wyajy9HUuH-d8M9HTsbIJee3_jSTuCUl719NfjSahQ6tQ-JnqlRxV)