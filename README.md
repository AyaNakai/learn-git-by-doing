# learn-git-by-doing

初心者向けのGit/GitHub体験型チュートリアルです。
HTMLファイルを実際に編集しながら、コミット・プッシュ・マージ・競合解決・変更の取り消しを段階的に学べます。

高度なHTMLの知識は必要ありません。
練習用のリポジトリなので、失敗もOK!
ぜひ試してみてください!

### 事前準備

以下を用意してください。

- [Git](https://git-scm.com/)
- コードエディタ（[Visual Studio Code](https://code.visualstudio.com/) など）
- [GitHubアカウント](https://github.com/)

### 学習開始

1. このリポジトリを自分のGitHubアカウントにForkします。
2. Forkしたリポジトリをローカル環境にcloneします。
3. ルートの `index.html` をブラウザで開きます。
4. `lesson-00/index.html` をエディタで開き、手順に沿って進めます。

コマンドはすべてリポジトリのルートで実行します。`yourname` は自分の識別名に、`<URL>` や `<過去のID>` などは実際の値に置き換えてください。山括弧は入力しません。GitHubへのpushには認証が必要です。

## レッスン

| フォルダ | 内容 |
| --- | --- |
| [lesson-00](lesson-00/index.html) | 環境確認・Fork・clone・専用ブランチ |
| [lesson-01](lesson-01/index.html) | status・diff・add・最初のcommit |
| [lesson-02](lesson-02/index.html) | 変更を分けてコミット・log・show |
| [lesson-03](lesson-03/index.html) | push・fetch・pull |
| [lesson-04](lesson-04/index.html) | branch・switch・merge |
| [lesson-05](lesson-05/index.html) | PRの作成とマージ（任意） |
| [lesson-06](lesson-06/index.html) | 競合の発生・解決・中断 |
| [lesson-07](lesson-07/index.html) | restore・revert |
| [lesson-08](lesson-08/index.html) | HEAD・過去の確認・過去から分岐 |
| [lesson-09](lesson-09/index.html) | cherry-pick |
| [lesson-10](lesson-10/index.html) | 先祖返りの再現・確認・取り消し |

## 課題の読み方

フォルダ名は `lesson-NN`、課題番号は `チュートリアルN-1`、`チュートリアルN-2` の形式です。

```html
<!--
  【チュートリアル1-1】課題名
  1. ここに書かれた手順を実行します。
-->
<section>最初の課題のソース</section>

<!--
  【チュートリアル1-2】課題名
  1. 指示されたタイミングで、下のソースを囲むコメントを解除します。
-->
<!--
<section>次の課題のソース</section>
-->
```

手順のコメントは残し、表示用ソースを囲む開始・終了のコメントだけを外します。HTMLコメントは入れ子にできません。次の課題のソースは画面には表示されませんが、エディタでは読めます。

コメント解除もGitの変更に含まれます。各課題の指示に沿ってコミットしてください。ブランチ切り替え・pull・mergeの前は `git status` で作業ツリーがクリーンであることを確認します。未完了の編集がある場合は、先に現在の課題を終えて記録します。

## ブランチの使い方

- 自分専用の統合先：`practice/yourname`
- 作業ブランチ：`feature/yourname-lesson-NN`（競合演習のみ末尾に `-a` / `-b`）
- 教材の `develop` / `main` には直接コミット・マージしません。
- 教材はすべてこの版のフォルダに含まれています。旧 `tutorial/Lesson01` ブランチへ切り替える必要はありません。
- lesson-00以降は順番に取り組みます。lesson-05のみ省略できます。

## 詰まったとき・再開するとき

各課題の「完了条件」を確認し、`git status` と `git log --oneline -5` で現在位置を調べます。途中から再開するときは、すでに作ったブランチを `git switch <ブランチ名>` で開きます。同じ名前で `git switch -c` を繰り返さないでください。

マージの競合を解決する前なら `git merge --abort`、cherry-pick中なら `git cherry-pick --abort`、revert中なら `git revert --abort` で開始前に戻せます。

やり直し用には、別フォルダへ自分のForkをcloneし、教材の開始コミットから別名の練習ブランチを作る方法もあります。`reset --hard` やforce pushは本編では使いません。未コミットの編集を破棄する操作はlesson-07で対象ファイルを確認して行います。

## 発展学習

本編終了後に、stash（一時退避）、.gitignore（追跡しないファイル）、rebase（コミットの積み直し）、resetとreflog、タグなどを学ぶと実務につながります。
