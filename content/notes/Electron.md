---
title: Electron
feed: show
---
## 環境構築

### nvmのインストール
[nvm-windows](https://github.com/coreybutler/nvm-windows#node-version-manager-nvm-for-windows)リポジトリから最新のインストーラーをダウンロードします。  
![](https://storage.googleapis.com/zenn-user-upload/8s0w223dty7me35cxcegakdqkos1)

zipファイルを展開してインストーラーを起動。nvmをインストールします。  
![](https://storage.googleapis.com/zenn-user-upload/nlixmf2m1bdrd9ef43p86gg50zt4)

`nvm ls`コマンドが叩けるか確認します。
```
$ nvm ls

No installations recognized.
```

Node.jsの~~最新バージョン~~ではなく、Electronのホームページにあるverを今回はインストールします。
![](./Img/Pasted-image-20220827213104.png)
```
$ nvm install 16.15.0
```

この時点では
```
$ nvm list

    16.15.0
```
となっており、まだバージョンが選択されていない。

そのため、使用するバージョンを選択。
```
$ nvm use 16.15.0
exit status 1: �A�N�Z�X�����ۂ����܂����B
```
しかし上のように文字化けしてしまうので
https://askne.blog/2021/09/19/nvm-for-windows%E3%81%A7node-js%E3%82%92%E4%B8%8A%E6%89%8B%E3%81%8F%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A7%E3%81%8D%E3%81%AA%E3%81%84/
を参考に
コマンドプロンプトを管理者として実行して同じコマンドを打つとうまく行く。

このuseコマンドがうまく行くと
```
$ nvm list

  * 16.15.0 (Currently using 64-bit executable)
```
というふうになる。


### vue側のインストール
以下のコマンドでVue CLI 4をインストールする。(10分くらいはかかりそう)(2回目のインストールではタイムオーバーして3回分に分けてインストールした。)
バージョンが4なのは、vue/cliと連携する[vue-cli-plugin-electron-builder](https://github.com/nklayman/vue-cli-plugin-electron-builder) がまだ4までしか対応していないから。
```
$ npm install -g @vue/cli@4.3.0
```

```
? Please pick a preset: Manually select features
? Check the features needed for your project: Babel, TS, Router, Vuex, CSS Pre-processors, Linter   
? Use class-style component syntax? Yes
? Use Babel alongside TypeScript (required for modern mode, auto-detected polyfills, transpiling JSX
)? Yes
? Use history mode for router? (Requires proper server setup for index fallback in production) No   
? Pick a CSS pre-processor (PostCSS, Autoprefixer and CSS Modules are supported by default): Sass/SC
SS (with node-sass)
? Pick a linter / formatter config: Standard
? Pick additional lint features: Lint on save
? Where do you prefer placing config for Babel, ESLint, etc.? In package.json
? Save this as a preset for future projects? No
```

```
reify:typescript: http fetch GET 200 https://registry.npmjs.org/typescript/-
```
でめっちゃ止まる。

python2.7のインストール
今回はchocoというwindows用の？バージョン管理ツールを使った。

npm config の設定…


今度は
```
Error: Cannot find module 'fs/promises'
```
というログが出て止まる。

node のバージョンを最新にして事なきを得る。

electronは13.0.0

## SQLite3を入れる

色々バグってるので
`node-addon-api`をダウングレードすることに。
ではなく、nodeのバージョンを14.11.0にダウングレードすることで、NAPI_VERSIONが多分7になってこの問題を回避することに成功。
## 構築後
起動`npm run electron:serve`

デベロッパーツールの開き方は`ctrl + shif + I`
