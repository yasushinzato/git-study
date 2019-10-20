# Gitの勉強
# git
Gitはコマンドラインツールを指す。

## インストール
`sudo apt-get update`
`sudo apt-get install git`

## 設定
- sshの公開鍵と秘密鍵の作成
`ssh-keygen`
ファイル名はデフォルトでEnter
パスフレーズを聞かれるので、2回入力


- 鍵が「~/.ssh」の中に保存されている。
`ls ~/.ssh`

- 公開鍵情報をコンソールに表示
`cat ~/.ssh/id_rsa.pub

- GitHubを開いて、右上のアイコンからSettingsを開く
- 「SSH and GPG keys」からNew SSH Keyボタンをクリック
- Titleには末尾にあるもの？を指定する？「vagrant@ubuntu-xenial」今回はこれ。
- コンソールに表示されたものをコピペする。
ssh-rsa hogehogehogehohgehogheohgoehgoehgoeWbTpxrEEV1VSOD2MlNYlCWbTpxrEEV1VSOD2MlNYlC+PTy/Et0ydFNKdoSvOVkYi8cNSXfHkNbiYwYbBN26W/OSwJlyhRcyhdCrCsWTQKOkgMsYGglxZ58xqOvhWbUf8QEpMZ1YhofGzNkMwgTCzNQcKntU8jnqKKKB9EinCUcz/E6yv75SAWsUd24WJ/Ni4eIbepTO3XOuJF5uOq2tyb5Uidtu30e+Se0S6cdyiKffhLqdH1+KF9AyeGYjJxtv vagrant@ubuntu-xenial


## GitHubからクローン
- repositoryを選択して、Clone or DownloadかUse SSHを選択するとURLが切り替わるので、コピー
- Linuxのコンソール上からcloneを実行
`cd workspace`
`git clone git@github.com:yasushinzato/assessment.git`
- クローンして作成されたフォルダに移動して、最新版を取得する。
`git pull origin gh-pages`


## Gitに自分の情報登録
```
git config --global user.name "yasushinzato"
git config --global user.mail "hogehoge@gmail.com"
git config --global core.editor "vim"
git config -l
```

## Gitでrepository(リポジトリ)を作成
ローカルにフォルダを作成し、対象フォルダにて以下コマンドを実行
`git init`
README.mdファイルを作成して、リポジトリのトップページを作成しておく。
`git add README.md`
addコマンドでは、まだコミットされていない状態。コミット前の状態はステージングという。
ステージングは以下のコマンドにて確認する。
`git status`
以下のコマンドでリポジトリへコミット!!
`git commit -m "初めてのGitでのコミット"`
ユーザ情報がないよって怒られた。ちゃんとconfigの確認してたけど、作業したままの別のリポジトリでコマンド実行したのが行けなかったっぽい。
その証拠に、リポジトリが違うところのconfigファイルの中身確認したら見事にユーザ情報がなかった。
ログを確認してコミットが成功しているか確認する。
`git log`

GitHub上から、同じ名前のリポジトリを作成する。
そうするとGitHub上へ反映するためのコマンドが紹介されるので、実行する。
```
git remote add origin git@github.com:yasushinzato/git-study.git
git push -u origin master
```


