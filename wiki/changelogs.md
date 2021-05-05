# Changelogs

## 2.5.1

* refactoring the project to be supported by [remote_theme](https://github.com/benbalter/jekyll-remote-theme). No you can avoid to import all sources files into your project
* improved support for gitlab
* improved support for docker
* implemented static TOC (removed the javascript method) 

## 2.3.0

Changed #toc div, now it's called #git-wiki-toc. You've to change it too if you are using a totally custom theme.

New theme: github

Various fixes

## 2.2 - External Links

* Implemented external links icon (wikipedia style)

## 2.1.16 - Search with steroids

* Improved search engine with new async js data loading
* fixed page list

## 2.1.12 - Mobile Header
* Implemented collapsible responsive header

## 2.1.11 - Blog fixes

* various critical fixes to new blog system
* added "permalink" in config dist 

## 2.1.0 - Blog Refactoring

* Blog
* New search engine
* Button to add wiki page and post
* Page and post list in sidebar
* other minor fixes
* Improved SEO

See the list of changes here: [Article](../_posts/2018-12-17-blog-refactoring-v2.1.0.md)

## 2.0.3

* fixed bug on logo visualization
* fixed united and lux theme unwanted character

## 2.0.1 - Themed Wiki

* Created new themes from "united" and "lux" bootstrap styles
* minor fix to 404 page, fixed build warning

## 2.0.0 - Wiki Modules

* Splitted default layout in reusable partial files and modular architecture
* Created configurable including hooks to extend git-wiki theme
* Fixed some deprecation
* Crated Gemfile for local installations
* removed not used configurations
* compress css
* minor fixes


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

## 1.0.4 - Red

* Implemented red links for non-existing pages
* various style fixes

## 1.0.2

First public version of git-wiki with following features:

* Action buttons to edit page, see the history and search in wiki
* You can customize your wiki as you want with style sheets and even changing the layout.
* Improvements in the cooperative aspect: forks, pull-requests and roles.
* No databases! Only static files that can be downloaded in a few seconds.
* Markdown and html mixed together!
* History, revision comparison and everything you need from a wiki platform.
* You can edit your pages with the standard git editor, prose.io (integrated) or any kind of editor you prefer.



