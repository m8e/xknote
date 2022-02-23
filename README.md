# XK-Note

> - Cloud Notes with Various Magical Functions

![Version](https://img.shields.io/github/release/syfxlin/xknote.svg?label=Version&style=flat-square) ![Author](https://img.shields.io/badge/Author-Otstar%20Lin-blue.svg?style=flat-square) ![PHP](https://img.shields.io/badge/php-7.0%2B-green.svg?style=flat-square) ![Lincense](https://img.shields.io/github/license/syfxlin/xknote.svg?style=flat-square)

## 目录 Contents

- [XK-Note](#xk-note)
  - [目录 Contents](#%e7%9b%ae%e5%bd%95-contents)
  - [简介 Introduction](#%e7%ae%80%e4%bb%8b-introduction)
  - [特性 Feature](#%e7%89%b9%e6%80%a7-feature)
  - [演示 Demo](#%e6%bc%94%e7%a4%ba-demo)
  - [安装 Install](#%e5%ae%89%e8%a3%85-install)
    - [一键安装 Key Installation](#%e4%b8%80%e9%94%ae%e5%ae%89%e8%a3%85)
    - [升级 Upgrade](#%e5%8d%87%e7%ba%a7)
    - [手动安装 Manual Installation](#%e6%89%8b%e5%8a%a8%e5%ae%89%e8%a3%85)
  - [文档 Doc](#%e6%96%87%e6%a1%a3-doc)
  - [维护者 Maintainer](#%e7%bb%b4%e6%8a%a4%e8%80%85-maintainer)
  - [许可证 License](#%e8%ae%b8%e5%8f%af%e8%af%81-license)
  - [渲染 Render](#%e6%b8%b2%e6%9f%93-render)

## 简介 Introduction

`XK-Note` = `Laravel` . `Vue2.0` . `XK-Editor`;
Cloud Notes with Various Magical Functions

## 特性 Features

- [Cloud Storage] Write notes in the cloud, save them at any time, and synchronize with multiple terminals.
- [Cross-Platform] Multi-platform support, only one browser is needed for writing and viewing, no fear of any incompatibilities.
- [Responsive] All pages are responsively designed to maintain a good experience even on extremely small size devices.
- [Online Browsing] With an independent browsing mode, viewing notes is no longer troublesome.
- [Historical Version] Notes support historical version viewing and rollback, you can switch to any submitted historical version without fear of accidental deletion. (based on Git)
- [Git Sync Support] Unique Git support, support version control, no fear of misoperation, restore notes from the old version at any time.
- [Temporary Browser Save] The unique browser-side save function allows you to write with peace of mind even if the network is disconnected, without fear of any network fluctuations.
- [Post to Blog] Notes can be pushed to WordPress, Hexo and other blog systems with one click after editing.
- [Multiple notes open at the same time] Notes can be opened at any time, you don't need to close previously opened notes while editing other notes.
- [Multi-user] Notes are mainly for personal use, but multiple users are also supported at the same time. Each user's notes are stored in isolation from each other, so there is no need to worry about note leakage.
- [Export Notes] Support a variety of export formats, save as MD files, html files, and generate them locally without any tedious operations.
- [Multiple Modes] With multiple modes, writing, previewing, reading, to meet the needs of all kinds of people.
- There are also a variety of magical functions waiting for you to discover.

## 演示 Demo
[XK-Note](https://note.ixk.me)

**账号：** demo@ixk.me / demo

**密码：** demodemo

## 安装 Install

> Currently XK-Note v2 is still in the testing stage, so there may be bugs. If you encounter bugs or suspected bugs during use, please submit an issue or contact me so that you can get the fix as soon as possible.

### 一Key Installation

1. Install Dependencies:
```bash
# Ubuntu/Debian 其他系统请自行查阅
# 鉴于不同用户安装PHP的方法不同，这里就不写PHP的安装方法了
sudo apt-get install curl git
curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/local/bin/composer
# 安装NodeJS和yarn/npm
sudo apt install npm
sudo npm i -g npm
sudo npm i -g yarn
sudo npm i -g n
sudo n stable
```
2. clone this repository:
```
git clone https://github.com/m8e/xknote.git
```
1. Copy `.env.example` file, rename it to `.env`, modify the corresponding information, and turn off the debug mode
```
APP_DEBUG=false
APP_ENV=production
APP_ADMIN_ID=1 #一般来说第一位注册的用户自动升级为管理员，也就是id为1的用户，如果发现不是可以修改这个参数，改成你的id
APP_URL=you url
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=xknote
DB_USERNAME=you mysql username
DB_PASSWORD=you mysql password
MAIL_DRIVER=smtp
MAIL_HOST=smtp.example.com
MAIL_PORT=465
MAIL_USERNAME=you mail username
MAIL_PASSWORD=you main password
MAIL_ENCRYPTION=ssl
MAIL_FROM_ADDRESS=i@example.com
MAIL_FROM_NAME=XK-Note
```
4. Install
```
composer xknote-install
```

### Upgrade

> If you are using manual installation, please confirm whether the remote of xknote-github exists in git. 
> If not, please add it and run the following command

```
composer xknote-update
```

### Manual Installation

1. Install Dependencies
```bash
# Ubuntu/Debian 
# This assumes you have already installed PHP on your machine

sudo apt-get install curl git
curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/local/bin/composer
# Install NodeJS and yarn/npm
sudo apt install npm
sudo npm i -g npm
sudo npm i -g yarn
sudo npm i -g n
sudo n stable
```
2. clone this repository
```
git clone https://github.com/syfxlin/xknote.git
```
3. Install the module
```
composer install
yarn
```
4. Copy `.env.example` file, rename it to `.env`, modify the corresponding information, turn off the debug mode, and run the following command to generate app key
```
APP_DEBUG=false
APP_ENV=production
APP_ADMIN_ID=1 #Generally speaking, the first registered user is automatically upgraded to an administrator, that is, the user whose id is 1. If you find that this parameter is not available, you can modify this parameter and change it to your id.
APP_URL=you url
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=xknote
DB_USERNAME=InsertYourMySQLusername
DB_PASSWORD=InsertYourMySQLPassword
MAIL_DRIVER=smtp
MAIL_HOST=smtp.example.com
MAIL_PORT=465
MAIL_USERNAME=InsertYourMailUsername
MAIL_PASSWORD=InsertYourMailPassword
MAIL_ENCRYPTION=ssl
MAIL_FROM_ADDRESS=i@example.com
MAIL_FROM_NAME=XK-Note
```
```
php artisan key:generate
```
5. Go to the root directory of the website and execute the following command
```bash
php artisan storage:link
php artisan migrate
php artisan db:seed
```
6. Compile Vue
```bash
yarn prod
```
7. Modify the running directory of the website to `public`
8. Open the website, register an account, and confirm whether the account `id` is `1`, if not, you need to modify the `.env file`
9. enjoy

## Documentation

None yet...

## Creator: 

XK-Note 由 [Otstar Lin](https://ixk.me/)和下列[贡献者](https://github.com/syfxlin/xknote/graphs/contributors)的帮助下撰写和维护。

> Otstar Lin - [Personal Website](https://ixk.me/) · [Blog](https://blog.ixk.me/) · [Github](https://github.com/syfxlin)

## 许可证 License

![license](https://img.shields.io/github/license/syfxlin/xknote.svg?style=flat-square)

根据 Apache License 2.0 许可证开源。

## 渲染 Render

![ScreenShot-1](https://raw.githubusercontent.com/m8e/xknote/master/screenshot-1.png)
![ScreenShot-2](https://raw.githubusercontent.com/m8e/xknote/master/screenshot-2.png)
![ScreenShot-3](https://raw.githubusercontent.com/m8e/xknote/master/screenshot-3.png)
![ScreenShot-4](https://raw.githubusercontent.com/m8e/xknote/master/screenshot-4.png)
