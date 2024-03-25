# ProxyAsService

this web là 1 proxy giữa bạn và reddit.com

khi khởi chạy web lần đầu sẽ bị chuyển hướng đến 1 subreddit random. tuy nhiên url chỉ ra rằng vẫn trên web của proxy, không hoàn toàn được chuyển hướng đến reddit. ngoài ra , có thể sửa tham số url

từ source thấy

flag đc lưu ở biến môi trường

![https://lh7-us.googleusercontent.com/k3DmriuTjU2NLxCJLz2b5DBAt2a8EnBRG9viAno3Iumti9_gLdUXhDSMMi8zjpzgCopftwXuEjj5TtL8UMsgV74DsxqIKmpa9ps444nqqsbAAfXHweKMv3RoD0lDbYwyrTe6hMyfpWTJ](https://lh7-us.googleusercontent.com/k3DmriuTjU2NLxCJLz2b5DBAt2a8EnBRG9viAno3Iumti9_gLdUXhDSMMi8zjpzgCopftwXuEjj5TtL8UMsgV74DsxqIKmpa9ps444nqqsbAAfXHweKMv3RoD0lDbYwyrTe6hMyfpWTJ)

có hàm cho phép show all biến môi trường

![https://lh7-us.googleusercontent.com/KKuPozm7voZfBFG6m7WQjuQrHbPMQCfLFMDwA5_LOOXFCIlrAromYpuIqISfKqYvIVUOXoZ5eg9FjW24RiaW6pGZnIoeQppfIm287FWmCcAv9W-Ei4FIDvJz_XkF6MkGf611J0qspsdx](https://lh7-us.googleusercontent.com/KKuPozm7voZfBFG6m7WQjuQrHbPMQCfLFMDwA5_LOOXFCIlrAromYpuIqISfKqYvIVUOXoZ5eg9FjW24RiaW6pGZnIoeQppfIm287FWmCcAv9W-Ei4FIDvJz_XkF6MkGf611J0qspsdx)

nhưng để truy cập /environment yêu cầu phải truy cập từ localhost, nhưng lại lọc 127 và ‘localhost’

![https://lh7-us.googleusercontent.com/wXmEZN3VAyTLV2YgPBvgD4CcQ38-DN_SSmiaUBrYnqRae3dM_8rcH58B1qGw5a-Xw7p7OSlY8dStV9XK8FdlM3ygG72yyfNMEqSRTxSOB2rs8GKZ2KkZjEJuXJbroWMby5OyC38XIadd](https://lh7-us.googleusercontent.com/wXmEZN3VAyTLV2YgPBvgD4CcQ38-DN_SSmiaUBrYnqRae3dM_8rcH58B1qGw5a-Xw7p7OSlY8dStV9XK8FdlM3ygG72yyfNMEqSRTxSOB2rs8GKZ2KkZjEJuXJbroWMby5OyC38XIadd)

sử dụng [PayloadsAllTheThings/Server Side Request Forgery/README.md at master · swisskyrepo/PayloadsAllTheThings (github.com)](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Server%20Side%20Request%20Forgery/README.md#payloads-with-localhost) để bypass

lắng nghe ở p1337

![https://lh7-us.googleusercontent.com/APQSo5hLenm4Q7YayyZNMHfN9lUc_uXXTrkml0uihgdPb8_fqI5pv9VHYmUXPbY_C9nzDjKAlwqL4TnFW2xID-mBu4EHMBLVZQIlpr6YJXQf8uPRfyYNvE8eQy2rAVY9D-tmOvwMhzHZ](https://lh7-us.googleusercontent.com/APQSo5hLenm4Q7YayyZNMHfN9lUc_uXXTrkml0uihgdPb8_fqI5pv9VHYmUXPbY_C9nzDjKAlwqL4TnFW2xID-mBu4EHMBLVZQIlpr6YJXQf8uPRfyYNvE8eQy2rAVY9D-tmOvwMhzHZ)

và có thể thay đổi giá trị tham số url

cố gắng redirect /environment nhưng chỉ có thể được chuyển hướng đến reddit.

- > how redirect to localhost

![https://lh7-us.googleusercontent.com/GyJg-y2qQw8kCSZlLV5k8Ne3Uvna3UVQXEX3cUd9RKwjMIY7K-k2XqjhIZjrjEPI4aj-Qj-6R-KravZfl3NzNmIOyZYTEixUbyyQ1ws8MY9vuEIAqZWlS9aR-8Mjc0gob_WUOYdiRDDf](https://lh7-us.googleusercontent.com/GyJg-y2qQw8kCSZlLV5k8Ne3Uvna3UVQXEX3cUd9RKwjMIY7K-k2XqjhIZjrjEPI4aj-Qj-6R-KravZfl3NzNmIOyZYTEixUbyyQ1ws8MY9vuEIAqZWlS9aR-8Mjc0gob_WUOYdiRDDf)

nhận thấy có thể thay đổi giá trị cho biến url, và sitename không bao gồm / ở cuối nên có thể thay đổi thành http://1.1.1.1@2.2.2.2 ==> http://2.2.2.2

dùng @ để vô hiệu hóa phần phía trước nó

![https://lh7-us.googleusercontent.com/0w8rcJV_S0C6YWK1GBkXe103azR7byD38U5jDJIoRNJTA3Lzj3X61ZxYD4Sn1ZHSdZlxUi_HBHuP14dIGwCQMxfrwlNKGg8wCLnooTnNJw3hTJoN55ndvigDXONEvcPPRHpR3THc79dY](https://lh7-us.googleusercontent.com/0w8rcJV_S0C6YWK1GBkXe103azR7byD38U5jDJIoRNJTA3Lzj3X61ZxYD4Sn1ZHSdZlxUi_HBHuP14dIGwCQMxfrwlNKGg8wCLnooTnNJw3hTJoN55ndvigDXONEvcPPRHpR3THc79dY)