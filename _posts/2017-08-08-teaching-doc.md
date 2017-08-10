---
layout:     post
title:      Jekyll + Github page = Personal Website
date:       2017-08-10 20:30:00
summary:    Jekyll + Github page = Personal Website
categories: jekyll
thumbnail: jekyll
tags:
---


# Jekyll + Github page = 個人靜態網頁 (on mac)

本篇將介紹如何利用 jekyll 和 github page 做出個人的的網站

## 1.Github Page 
[Github Page](https://pages.github.com/)透過github, 可以建立起個人的靜態網頁, 也將自己的網站託管在github上, 非常簡單方便

1. 開啟或創立自己的[github](https://github.com/)帳號
2. 建立new repository, 名稱為 **username.github.io** (username為自己的帳號)
3. 按下專案上的 Set up in Desktop, 下載並安裝github desktop
4. 即可將自己的網頁透過此上傳

## 2.Jekyll 
[jekyll](http://jekyll.com.cn/)使用者就可以用 Markdown 語法來寫文章, Jekyll 會自動將你的文章自動編譯為Jekyll 規範的 HTML 網頁

#### 打開終端機, 安裝jekyll

```bash
# OSX 10.11以上
gem update ruby
sudo gem install -n /usr/local/bin/ jekyll
sudo gem install -n /usr/local/bin/ bundler
sudo gem install -n /usr/local/bin/ rdiscount

# OSX 10.11以下
gem update ruby
sudo gem install jekyll
sudo gem install bundler
sudo gem install rdiscount
```

#### jekyll 插件
(取決於個人網頁需不需用到)

1. 在網站的root, 建一個`_plugins`資料夾 <br>
2. 在`_config.yml`檔案中, 新增一行`plugins: [jekyll-coffeescript, jekyll-watch, jekyll-assets]`, 然後在終端機執行`gem install jekyll-coffeescript jekyll-watch jekyll-assets`<br>
3. 在`Gemfile`中新增
```bash 
group :jekyll_plugins do
   gem "my-jekyll-plugin"
   gem "another-jekyll-plugin"
 end
 ```
  最後在終端機`bundle install`安裝
 
 
#### 更換主題

- <http://jekyllthemes.org/>
- <https://jekyllthemes.io/>
- <http://themes.jekyllrc.org/>