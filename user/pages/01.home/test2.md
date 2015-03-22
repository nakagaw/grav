---
title: TEST2
slug: test2
template: post
---

超軽量テンプレートエンジン<a href="http://getgrav.org/" target="_blank">Grav</a>というのをさわってみました。


# インストール

サーバー（もしくはローカル環境）には PHP 5.4以上がインストールされている必要があります。

インストールは、git cloneして
```
git clone https://github.com/getgrav/grav.git
```

```
cd grav
bin/grav install
```

するとビルド的なことが起こって、

```
php -S localhost:8000
```

というコマンドを打つと、

<a href="http://localhost:8000/" target="_blank">http://localhost:8000/</a>

でローカルサーバーが立ち上がって確認できます。

最初に表示されているページがどこにあるかというと、

/grav/user/pages/01.home/default.md

というマークダウンファイルです。


# 新規ページの作成

/grav/user/pages/以下にある01.homeというディレクトリをまるごと複製して「02.about」といったディレクトリ名にリネーム。
それだけでグローバルに「about」というメニューが追加され、02.about以下にあるdefault.mdの内容がページとして生成されます。

参考：<a href="http://learn.getgrav.org/content/content-pages#folders" target="_blank">Pages | Grav Documentation</a>

参考：<a href="http://learn.getgrav.org/content/markdown" target="_blank">Markdown Syntax | Grav Documentation</a>


# ブログのシステム設定

/grav/user/config/system.yaml

このYAMLファイルで、ホームディレクトリの設定、一覧の表示数や、年月日の表示形式、CSS&JSのコンパイル方法、など、サイトのもろもろの設定ができます。

参考：<a href="http://learn.getgrav.org/basics/grav-configuration" target="_blank">Configuration | Grav Documentation</a>


# サイトの設定

/grav/user/config/site.yaml

サイトのタイトル、管理者の名前、メールアドレス、メタ、ブログのルート設定などができます。

参考：<a href="http://learn.getgrav.org/basics/grav-configuration#site-configuration" target="_blank">Configuration | Grav Documentation</a>


# テーマの変更

テーマファイルは下記の場所にzipをダウンロードして置いたり、テーマによってはコマンドでインストールとかもできそうです。

/grav/user/themes

2015年3月現在で、公式に提供されている<a href="http://getgrav.org/downloads/themes" target="_blank">テーマ</a>は16個です。

変更の方法は

/grav/user/config/system.yaml

を開いて

theme: notepad

のところをテーマの名前に変更、キャッシュをクリアしないとうまく動かないテーマもあるようです。

```
cd grav
bin/grav clear-cache
```

これで変更はされるのですが、テーマごとにディレクトリの構成とか作りが違うので、WordPressのようにテーマを変えたからといって、サイトが一瞬で変わるような感じではない。



# ページの種類


### 通常のページ

参考：<a href="http://learn.getgrav.org/content/content-pages#standard-page" target="_blank">Pages | Grav Documentation</a>

### ブログっぽいページ

参考：<a href="http://learn.getgrav.org/content/content-pages#listing-page" target="_blank">Pages | Grav Documentation</a>


### シングルコンテンツページ

パーシャルディレクトリ

参考：<a href="http://learn.getgrav.org/content/modular" target="_blank">Modular Pages | Grav Documentation</a>


# Grav is Running!
## You have installed **Grav** successfully

Congratulations! You have installed the **Base Grav Package** that provides a **simple page** and the default **antimatter** theme to get you started.

>>>>> If you want a more **full-featured** base install, you should check out [**Skeleton** packages available in the downloads](http://getgrav.org/downloads).

### Find out all about Grav

* Learn about **Grav** by checking out our dedicated [Learn Grav](http://learn.getgrav.org) site.
* Download **plugins**, **themes**, as well as other Grav **skeleton** packages from the [Grav Downloads](http://getgrav.org/downloads) page.
* Check out our [Grav Development Blog](http://getgrav.org/blog) to find out the latest goings on in the Grav-verse.

### Edit this Page

To edit this page, simply navigate to the folder you installed **Grav** into, and then browse to the `user/pages/01.home` folder and open the `default.md` file in your [editor of choice](http://learn.getgrav.org/basics/requirements).  You will see the content of this page in [Markdown format](http://learn.getgrav.org/content/markdown).

### Create a New Page

Creating a new page is a simple affair in **Grav**.  Simply follow these simple steps:

1. Navigate to your pages folder: `user/pages/` and create a new folder.  In this example, we will use [explicit default ordering](http://learn.getgrav.org/content/content-pages) and call the folder `02.mypage`.
2. Launch your text editor and paste in the following sample code:

        ---
        title: My New Page
        ---
        # My New Page!

        This is the body of **my new page** and I can easily use _Markdown_ syntax here.

3. Save this file in the `user/pages/02.mypage/` folder as `default.md`. This will tell **Grav** to render the page using the **default** template.
4. That is it! Reload your browser to see your new page in the menu.

>>> NOTE: The page will automatically show up in the Menu after the "Home" menu item. If you wish to change the name that shows up in the Menu, simple add: `menu: My Page` between the dashes in the page content. This is called the YAML front matter, and it is where you configure page-specific options.
