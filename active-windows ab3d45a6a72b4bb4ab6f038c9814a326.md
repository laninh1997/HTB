# active-windows

dùng nmap liệt kê các port mở thấy có kerberos, ldap, smb

![https://lh7-us.googleusercontent.com/_OsMjQAgI38x5tH1Mq3W1gE_PUGiY0tEffVomYOr8rGb7mno75Q7U2e1ZPt-fPblY9X1ejaRfgNCHAkLflx8Tb2s4vrqMqzVYo5d2jnT5FeHK7ivcNrzWM4Gq3mBR-kCC3ciWgExHMTC](https://lh7-us.googleusercontent.com/_OsMjQAgI38x5tH1Mq3W1gE_PUGiY0tEffVomYOr8rGb7mno75Q7U2e1ZPt-fPblY9X1ejaRfgNCHAkLflx8Tb2s4vrqMqzVYo5d2jnT5FeHK7ivcNrzWM4Gq3mBR-kCC3ciWgExHMTC)

![https://lh7-us.googleusercontent.com/qxrCL8X1fX2NO0u9A7hZ_76AWAqLEDlPnp0nfzdQVsJ2vPgZ6jJSL0yyi32wOgM9e9jOoPEvmrnlWo2zwjUnA51_qijNTosiHFpFbDsQc5jcjI_2xrdIWKirgLTMOpoTf9mMq2oXlJQp](https://lh7-us.googleusercontent.com/qxrCL8X1fX2NO0u9A7hZ_76AWAqLEDlPnp0nfzdQVsJ2vPgZ6jJSL0yyi32wOgM9e9jOoPEvmrnlWo2zwjUnA51_qijNTosiHFpFbDsQc5jcjI_2xrdIWKirgLTMOpoTf9mMq2oXlJQp)

khai thác smb as anonymous

ngoại trừ các thư mục share mặc định và yêu cầu quyền của admin thì có thể truy cập Replication

![https://lh7-us.googleusercontent.com/SDjgviIBfAsYWNabrX4FWN8gwpciDrAP-WEIxwZXsxqY42RI8hFHu7x29LemNVlm5_8N27XpuPvTiVHGx67xGdzlvOyZTi6eXLZ_iMh2tp371sgl2U4zSeYIRrzkXo6jNn_RLEE6-fUv](https://lh7-us.googleusercontent.com/SDjgviIBfAsYWNabrX4FWN8gwpciDrAP-WEIxwZXsxqY42RI8hFHu7x29LemNVlm5_8N27XpuPvTiVHGx67xGdzlvOyZTi6eXLZ_iMh2tp371sgl2U4zSeYIRrzkXo6jNn_RLEE6-fUv)

truy cập thư mục share có thể đọc

![https://lh7-us.googleusercontent.com/Di-OvrneUIHO20USrCof1DACspc6HEq1Dr28Ql0t7VecvdD5HG8PQ8mbJdTTW1x4fc1mE__syjWdloPb1HgvYeAXvcVWOTUyrm-LbNx-nEqAscKuudkoDr_nrEunBZ7WLDjWA1HVe8T2](https://lh7-us.googleusercontent.com/Di-OvrneUIHO20USrCof1DACspc6HEq1Dr28Ql0t7VecvdD5HG8PQ8mbJdTTW1x4fc1mE__syjWdloPb1HgvYeAXvcVWOTUyrm-LbNx-nEqAscKuudkoDr_nrEunBZ7WLDjWA1HVe8T2)

thu thập các file trên smb

![https://lh7-us.googleusercontent.com/VwKId-pdFt3lYJmoCrHP1AIkmuPnrfIu7bkDYp4DOUO5x7Jyx4uqGao8gzJwneCWwYawbx7EQHgxYOghHcPxso0wf37-t_QX50067kspZItRxJxhCYEcy5HsW5FK5Q21kUYdaWjl5vOy](https://lh7-us.googleusercontent.com/VwKId-pdFt3lYJmoCrHP1AIkmuPnrfIu7bkDYp4DOUO5x7Jyx4uqGao8gzJwneCWwYawbx7EQHgxYOghHcPxso0wf37-t_QX50067kspZItRxJxhCYEcy5HsW5FK5Q21kUYdaWjl5vOy)

tìm thấy pw và user

![https://lh7-us.googleusercontent.com/tmR6Glz7OxujZHW7Hs1XYay8521_41CW9wz1yKtQDRvxZS8Kul4_jSQ7AIsBryY-uDa5p4FtZspKBNo5LNMObZGiJWiP3OVqr1AtI-iR2HIVXVxe4RYvVfBejff86gUU1nQVbf6Vd5tP](https://lh7-us.googleusercontent.com/tmR6Glz7OxujZHW7Hs1XYay8521_41CW9wz1yKtQDRvxZS8Kul4_jSQ7AIsBryY-uDa5p4FtZspKBNo5LNMObZGiJWiP3OVqr1AtI-iR2HIVXVxe4RYvVfBejff86gUU1nQVbf6Vd5tP)

active.htb\SVC_TGS

edBSHOwhZLTjt/QS9FeIcJ83mjWA98gw9guKOhJOdcqh+ZGMeXOsQbCpZ3xUjTLfCuNH8pG5aSVYdYw/NglVmQ

![https://lh7-us.googleusercontent.com/iluwcAXpsVj-KvYJiqI3RMckET9581rIX-oE90WSk7iWJdHb13XVTDtASctVULC9swZmBJthIGWylAUKkE46XJdrKoqoz9auzU1WjhsP3BGCCb0pMPorukQjH1medbPYc0L5sg-ZWwf8](https://lh7-us.googleusercontent.com/iluwcAXpsVj-KvYJiqI3RMckET9581rIX-oE90WSk7iWJdHb13XVTDtASctVULC9swZmBJthIGWylAUKkE46XJdrKoqoz9auzU1WjhsP3BGCCb0pMPorukQjH1medbPYc0L5sg-ZWwf8)

Whenever a new Group Policy Preference (GPP) is created, there’s an xml file created in the SYSVOL share with that config data, including any passwords associated with the GPP. For security, Microsoft AES encrypts the password before it’s stored as cpassword. But then Microsoft published the key on MSDN!

Microsoft issued a patch in 2014 that prevented admins from putting passwords into GPP. But that patch doesn’t do anything about any of these breakable passwords that were already there, and from what I understand, pentesters still find these regularly in 2018. For more details, check out this AD Security post.

![https://lh7-us.googleusercontent.com/zvDRiS9M164Qj-8ei3n8Gn_EQgMHbyw-IOERv3CdbSfrU8T8uAaO13gf13Q78aijkoBiX9cFkwWH43D_3hNSSN930Un8CSow8jvi-mtQ1ppuiFG3bQ9gDW5SelTkMkvsOz5T7trE7D5Z](https://lh7-us.googleusercontent.com/zvDRiS9M164Qj-8ei3n8Gn_EQgMHbyw-IOERv3CdbSfrU8T8uAaO13gf13Q78aijkoBiX9cFkwWH43D_3hNSSN930Un8CSow8jvi-mtQ1ppuiFG3bQ9gDW5SelTkMkvsOz5T7trE7D5Z)

khai thác smb as SVC_TGS

dùng smbmap tìm thấy flag user

```powershell
smbmap -H 10.10.10.100 -d active.htb -u SVC_TGS -p GPPstillStandingStrong2k18 -R
```

![https://lh7-us.googleusercontent.com/9SiC6OYO4qQcFmWq37nmP_s-F1W9YEgkRMr2CqR4A7pCQGei1FHGanuJd68jQQvLGSe-yuQ12mcVuN2bpte9r2Jqa_J554uIVm2183GBgA89w34lKp61u_hOoGu5_ikreTJJAF-G38tA](https://lh7-us.googleusercontent.com/9SiC6OYO4qQcFmWq37nmP_s-F1W9YEgkRMr2CqR4A7pCQGei1FHGanuJd68jQQvLGSe-yuQ12mcVuN2bpte9r2Jqa_J554uIVm2183GBgA89w34lKp61u_hOoGu5_ikreTJJAF-G38tA)

kết nối và tải xuống

![https://lh7-us.googleusercontent.com/s5ETaOilBDw6ot9Duws50h06nIFwLK2xj8kbsLqS0U94Xe04-tAA8HX4Wd5RFA-MzM006_hY7LfzLAkx0VxsuJ4LSrgzw5kSQrpNtz_i3iuaHnTNP-I6aFZALJsPXDaBxIcS6U6UDyEF](https://lh7-us.googleusercontent.com/s5ETaOilBDw6ot9Duws50h06nIFwLK2xj8kbsLqS0U94Xe04-tAA8HX4Wd5RFA-MzM006_hY7LfzLAkx0VxsuJ4LSrgzw5kSQrpNtz_i3iuaHnTNP-I6aFZALJsPXDaBxIcS6U6UDyEF)

![https://lh7-us.googleusercontent.com/KVkIpG00XbFkvOzmPcSSXj_qtBHdUBSuCee-_cQUlMdxR7xMmiqKZuDwZ804WnK5Fd5R0e-Ir85SUGzD3UGd8Qr5yf8yIX1fZZQwE5h5TisMri5CLT8H0QTO4QuYnA9Xe54DBBHGDBJe](https://lh7-us.googleusercontent.com/KVkIpG00XbFkvOzmPcSSXj_qtBHdUBSuCee-_cQUlMdxR7xMmiqKZuDwZ804WnK5Fd5R0e-Ir85SUGzD3UGd8Qr5yf8yIX1fZZQwE5h5TisMri5CLT8H0QTO4QuYnA9Xe54DBBHGDBJe)

![https://lh7-us.googleusercontent.com/14QE3VpENDLWeVUcty_WyGGRpI5RaeakMW5iG6C7sKmdx82r43Z_hA2oOV5GknWYlPoWO-cUS7PsQVYUqV3jQfR0iu5yDp2kP7_spOtyZZGcgq56rVSmOx4d2VURs2Zac8z3gGpZeOjo](https://lh7-us.googleusercontent.com/14QE3VpENDLWeVUcty_WyGGRpI5RaeakMW5iG6C7sKmdx82r43Z_hA2oOV5GknWYlPoWO-cUS7PsQVYUqV3jQfR0iu5yDp2kP7_spOtyZZGcgq56rVSmOx4d2VURs2Zac8z3gGpZeOjo)

dùng getuserspns để lấy pw hash của user liên kết với Service Principal Name (SPN).

A service principal name (SPN) is a unique identifier of a service instance. Kerberos authentication uses SPNs to associate a service instance with a service sign-in account. Doing so allows a client application to request service authentication for an account even if the client doesn't have the account name.

![https://lh7-us.googleusercontent.com/Ut5bzlAW6nq9BoJC8dZwtQRr3Db2zCmfzeASEHxjte5rloeMNLeJFcPkTqXufdeNQqPOkie4POybk7LCjovrJCM-CTvEuSlNjUkWORVh-VqvZWN8i4IRnx_WLAEzrqFqOmt4X_PmoXOL](https://lh7-us.googleusercontent.com/Ut5bzlAW6nq9BoJC8dZwtQRr3Db2zCmfzeASEHxjte5rloeMNLeJFcPkTqXufdeNQqPOkie4POybk7LCjovrJCM-CTvEuSlNjUkWORVh-VqvZWN8i4IRnx_WLAEzrqFqOmt4X_PmoXOL)

nhập pw: GPPstillStandingStrong2k18

![https://lh7-us.googleusercontent.com/GLeBCNa9MsXCvmjgGC10olTDEdAGR69SSjP7bMVEDuyti8RhZwObeC1VFpLiMp2pJsjax2c420dR4K6E7Nqt1767XdDFwsDzF261v2fPgJwp9RI0pVOgsBwuBaTE3ugIIES0vThazDGf](https://lh7-us.googleusercontent.com/GLeBCNa9MsXCvmjgGC10olTDEdAGR69SSjP7bMVEDuyti8RhZwObeC1VFpLiMp2pJsjax2c420dR4K6E7Nqt1767XdDFwsDzF261v2fPgJwp9RI0pVOgsBwuBaTE3ugIIES0vThazDGf)

![https://lh7-us.googleusercontent.com/i81EpsSOI5l_6_vM6dy9JGyUb0zdSwbNVeEI_Xb2cJDkbKBK3yOExFF1ldwDqA_HPDeYL0UREIlbZBJ_J5shEPjy413f6V6i_5CrIMXtykwkm0tspyHiCbuT4IHpyZmVih3-ITeGC2ja](https://lh7-us.googleusercontent.com/i81EpsSOI5l_6_vM6dy9JGyUb0zdSwbNVeEI_Xb2cJDkbKBK3yOExFF1ldwDqA_HPDeYL0UREIlbZBJ_J5shEPjy413f6V6i_5CrIMXtykwkm0tspyHiCbuT4IHpyZmVih3-ITeGC2ja)

kiểm tra loại hash

![https://lh7-us.googleusercontent.com/Ni6smzw0dLigxvZ4J97AYF0zj03Rg2MlvFypJ-kh90aqx1Pyek6Mvz47dup99C4SLP9l0PcZZ5PkR_IPsNFjXRp97gExhVAqUDwAgsrMtgReJMKjHY_5u_7zqcOTCaJ_EhjBhfTBio3r](https://lh7-us.googleusercontent.com/Ni6smzw0dLigxvZ4J97AYF0zj03Rg2MlvFypJ-kh90aqx1Pyek6Mvz47dup99C4SLP9l0PcZZ5PkR_IPsNFjXRp97gExhVAqUDwAgsrMtgReJMKjHY_5u_7zqcOTCaJ_EhjBhfTBio3r)

hashcat mode

![https://lh7-us.googleusercontent.com/6YgW_gxKBHC1le2ieyfznRJjusEzcTY789U_OSsG7KE_6SvvzlZzccCH0DBEnKAacVpcl4SK_CIgDhlhvMheYse3dceqtcbLxd_7KuTHH0sFh_XXM0PRzO5eDlllEtTo4DmBVcg7VhA7](https://lh7-us.googleusercontent.com/6YgW_gxKBHC1le2ieyfznRJjusEzcTY789U_OSsG7KE_6SvvzlZzccCH0DBEnKAacVpcl4SK_CIgDhlhvMheYse3dceqtcbLxd_7KuTHH0sFh_XXM0PRzO5eDlllEtTo4DmBVcg7VhA7)

![https://lh7-us.googleusercontent.com/TH5fJuBjQ2AOpYciI9AGR6TKpVbp4Tq4VSPS0UQPAmAXzYY4FQFsMO6G9zWA3mucKNMEtabieWYISWMYL5S4qjYQUyjCk30QdekkAe0kpR6iUp926d3BPaG3gn39Plf_4OZQflSKovj9](https://lh7-us.googleusercontent.com/TH5fJuBjQ2AOpYciI9AGR6TKpVbp4Tq4VSPS0UQPAmAXzYY4FQFsMO6G9zWA3mucKNMEtabieWYISWMYL5S4qjYQUyjCk30QdekkAe0kpR6iUp926d3BPaG3gn39Plf_4OZQflSKovj9)

```powershell
hashcat -m 13100 -a 0 GetUserSPNs.out /home/kali/Documents/wordlist/ry.txt --force
```

![https://lh7-us.googleusercontent.com/EvlRYG2Xy5gg9ZML05VZCXUIvjUSaUX46unuOCH5xb3IjbpBFryiGU0j-vE2qEEO-PSGyYuILoLS2ECOIz_LLIjztfe8Aszv_s3IUwIF8chvgoPW-QO3I_-rs6pr3NHfWzO6VJNdbOSA](https://lh7-us.googleusercontent.com/EvlRYG2Xy5gg9ZML05VZCXUIvjUSaUX46unuOCH5xb3IjbpBFryiGU0j-vE2qEEO-PSGyYuILoLS2ECOIz_LLIjztfe8Aszv_s3IUwIF8chvgoPW-QO3I_-rs6pr3NHfWzO6VJNdbOSA)

khai thác smb as administrator

![https://lh7-us.googleusercontent.com/LAtbfxdiiJZt_medidr0oOvLtLJ2p7D9vTKxaDmkxQOGbu-6-5mNVw1pUNhodqeEziQQMRtI8qZc_Ra6oGSuWzvn3BXIBfX90RAqn6Bj3mK8IzE50Zvt7wofDac_16Dy5b4d8Je3iyyr](https://lh7-us.googleusercontent.com/LAtbfxdiiJZt_medidr0oOvLtLJ2p7D9vTKxaDmkxQOGbu-6-5mNVw1pUNhodqeEziQQMRtI8qZc_Ra6oGSuWzvn3BXIBfX90RAqn6Bj3mK8IzE50Zvt7wofDac_16Dy5b4d8Je3iyyr)

![https://lh7-us.googleusercontent.com/mn8mwR2AHAY1U5xPmbbfawA9ut1ZmrnFLQMtp5PV8anfg8epRIVQOE05zMCWS-K81Fe-yV7vdQLJZCiSdhXgCKxs85pqpG5DbU7StJHMkc5q7lXqhumA1AC8nm7wJ93LepckdfB4P2W2](https://lh7-us.googleusercontent.com/mn8mwR2AHAY1U5xPmbbfawA9ut1ZmrnFLQMtp5PV8anfg8epRIVQOE05zMCWS-K81Fe-yV7vdQLJZCiSdhXgCKxs85pqpG5DbU7StJHMkc5q7lXqhumA1AC8nm7wJ93LepckdfB4P2W2)

lấy flag root

![https://lh7-us.googleusercontent.com/y5yp5WGsrk_i9xRfkDquv435ggvlbBl5rg74UqZWJfxaW3w-tfiIf5-CzR1MX3pnQlIn2982WKBM3FEmZtCGyCxD0ZyxrtU2j0A1PYNgnnXvUP4RTA3Kvi8EtMv77SDs9tXy-Y-iWuNI](https://lh7-us.googleusercontent.com/y5yp5WGsrk_i9xRfkDquv435ggvlbBl5rg74UqZWJfxaW3w-tfiIf5-CzR1MX3pnQlIn2982WKBM3FEmZtCGyCxD0ZyxrtU2j0A1PYNgnnXvUP4RTA3Kvi8EtMv77SDs9tXy-Y-iWuNI)