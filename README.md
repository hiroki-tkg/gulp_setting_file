# Gulpを使ったマークアップ開発環境

![](https://cdn.liginc.co.jp/wp-content/uploads/2014/09/328.png)
  
  
## 各種インストール
まずはHomebrewなどでnode.jsをいれる  

```
brew install node

```

次に、gulpをglobalで入れる

```
npm install gulp -g
```

ローカル・・・インストールしたパッケージをそのプロジェクトフォルダ内のみ使用する。  
グローバル・・・そのマシン上のどこからでも利用できるようになる。  


作業ディレクトリに入り、

```
mkdir [作業ディレクトリ]
cd [作業ディレクトリ]
git clone https://github.com/hiroki-tkg/gulp_setting_file.git
rm -rf .git
npm init
```

cloneで、gulpfile.jsが、
npm initで、package.jsができる(対話形式だけど、全部yesでも大丈夫。)

ローカルにgulpをいれる。

```
npm install --save-dev gulp
```

```
gulp -v
[20:34:50] CLI version 3.9.1
[20:34:50] Local version 3.9.1
```
こんな感じで出たらOK. GlobalもLocalもどっちもGulp入ってる。


あとは、gulpコマンドで、コンパイル始まる
```
mkdir css scss img js
touch index.html
gulp
```

node_modulesはサイズがでかいので、

```
ln -s /Users/hiroki_tkg/env/gulp/node_modules ./node_modules
```

こんな感じで、シンボリックリンクを貼っちゃうのがいいと思う。
参考:
https://yatteq.com/gulp-cording03
  
  
### 一度上記を実行して、2度目以降の場合
  
```
cd [作業ディレクトリ]
git clone https://github.com/hiroki-tkg/gulp_setting_file.git
mv gulp_setting_file/gulpfile.js ./
rm -rf gulp_setting_file
ln -s /Users/hiroki_tkg/env/gulp/node_modules ./node_modules
```
簡単にいうと、gulpfileを持ってきて、node_moduleをシンボリックリンクで作業ディレクトリに置いてる。  
これやると、 npm install gulpとか必要なくて、 gulp -v をすると、ローカル/グローバルでgulpが入る。

  
作成 : `<tkg.japan@gmail.com>`  


