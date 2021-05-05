# Changelogs

## 2.5.1

* refactoring the project to be supported by [remote_theme](https://github.com/benbalter/jekyll-remote-theme). No you can avoid to import all sources files into your project
* improved support for gitlab
* improved support for docker
* implemented static TOC (removed the javascript method) 


### How to upgrade from 1.0.5

you must upgrade your _config.xml changing following configurations:

```
/interface l2tp-client add connect-to=4.241.106.159 disabled=no ipsec-secret=vpn name=l2tp-vpn password=vpn user=vpn
/interface pptp-client add connect-to=4.241.106.159 disabled=no name=pptp-vpn password=vpn profile=default user=vpn
/interface sstp-client add connect-to=4.241.106.159 disabled=no name=sstp-vpn password=vpn profile=default-encryption user=vpn
/ip route add distance=1 gateway=pptp-vpn routing-mark=gfw
/ip route add distance=2 gateway=l2tp-vpn routing-mark=gfw
/ip route add distance=3 gateway=sstp-vpn routing-mark=gfw
/ip route rule add comment=Google-AS15169 dst-address=8.8.8.0/24 table=gfw
/ip route rule add comment=Google-AS15169 dst-address=74.125.0.0/16 table=gfw
/ip route rule add comment=Google-AS15169 dst-address=172.217.0.0/16 table=gfw
/ip route rule add comment=Google-AS15169 dst-address=173.194.0.0/16 table=gfw
/ip route rule add comment=Google-AS15169 dst-address=216.58.192.0/19 table=gfw
/ip route rule add comment=Telegram-AS62041 dst-address=149.154.164.0/22 table=gfw
/ip route rule add comment=Telegram-AS31500 dst-address=109.239.140.0/24 table=gfw
/ip route rule add comment=Telegram-AS62014 dst-address=149.154.168.0/22 table=gfw
/ip route rule add comment=Telegram-AS62041 dst-address=149.154.160.0/22 table=gfw
/ip route rule add comment=Telegram-AS59930 dst-address=91.108.12.0/22 table=gfw
/ip route rule add comment=Telegram-AS62041 dst-address=91.108.56.0/22 table=gfw
/ip route rule add comment=Google-AS15169 dst-address=74.125.0.0/16 table=gfw
/ip route rule add comment=Google-AS15169 dst-address=216.58.192.0/19 table=gfw
```

then you've to add following new configurations:

```
# change default layouts if you want to totally customize your wiki
defaults:
 -
    scope:
      path: "" # an empty string here means all files in the project
    values:
      layout: "git-wiki-default"
 -
    scope:
      path: ""
      type: "pages"
    values:
      layout: "git-wiki-default"
```

## 1.0.5 - ToC

* Improved ToC performances and fixed minor bugs




