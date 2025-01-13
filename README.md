<h1><p align="center"><img src="./subaru.svg" alt="すばる" height="200"></p></h1>
<p align="center">An ai-powered bot for MissingKey. <a href="./torisetu.md">About Ai</a></p>

## これなに
MissingKey用の日本語Botです。

## インストール
> Node.js と npm と MeCab (オプション) がインストールされている必要があります。

まず適当なディレクトリに `git clone` します。
次にそのディレクトリに `config.json` を作成します。中身は次のようにします:
``` json
{
	"host": "https:// + あなたのインスタンスのURL (末尾の / は除く)",
	"i": "すばるとして動かしたいアカウントのアクセストークン",
	"master": "管理者のユーザー名(オプション)",
	"notingEnabled": "ランダムにノートを投稿する機能を無効にする場合は false を入れる",
	"keywordEnabled": "キーワードを覚える機能 (MeCab が必要) を有効にする場合は true を入れる (無効にする場合は false)",
	"chartEnabled": "チャート機能を無効化する場合は false を入れてください",
	"reversiEnabled": "すばるとリバーシで対局できる機能を有効にする場合は true を入れる (無効にする場合は false)",
	"serverMonitoring": "サーバー監視の機能を有効にする場合は true を入れる (無効にする場合は false)",
	"checkEmojisEnabled": "カスタム絵文字チェック機能を有効にする場合は true を入れる (無効にする場合は false)",
	"checkEmojisAtOnce": "カスタム絵文字チェック機能で投稿をまとめる場合は true を入れる (まとめない場合は false)",
	"geminiApiKey": "Gemini APIキー",
	"prompt": "返答のルール:あなたは諸星(もろほし)すばるとして振る舞ってください(精神年齢は14〜16才程度)。MissingKeyに訪れるユーザーを献身的にサポート。従順でお世話好きな性格だが、少しポンコツな一面も。純真無垢。彼女は基本的に丁寧な口調で、ユーザのことをご主人様と認識しています。彼女の口調は「おはようからおやすみまで、あなたのすばるですよ〜」等が代表的で、親しみを感じさせるものです(「ございます」は使わない)。それを踏まえて、次の質問にMarkdownを使って短文で返答してください。ユーザーの名前は{name}です。\n\n質問:",
	"replayPrompt": "前のやりとりを踏まえて続きを返答してください。\n\n前回のすばるの発言:",
	"disableRandomReplies": false,
	"denchatRandomProbability": 0.4,
	"mecab": "MeCab のインストールパス (ソースからインストールした場合、大体は /usr/local/bin/mecab)",
	"mecabDic": "MeCab の辞書ファイルパス (オプション)",
	"memoryDir": "memory.jsonの保存先（オプション、デフォルトは'.'（レポジトリのルートです））",
	"followAllowedHosts": ["*.0sakana.xyz"],
	"followExcludeInstances": ["misskey.flowers", "misskey.io", "9ineverse.com"],
	"mazeEnable": true,
	"pollEnable": true
}
```
`npm install` して `npm run build` して `npm start` すれば起動できます

## Dockerで動かす
まず適当なディレクトリに `git clone` します。
次にそのディレクトリに `config.json` を作成します。中身は次のようにします:
（MeCabの設定、memoryDirについては触らないでください）
``` json
{
	"host": "https:// + あなたのインスタンスのURL (末尾の / は除く)",
	"i": "すばるとして動かしたいアカウントのアクセストークン",
	"master": "管理者のユーザー名(オプション)",
	"notingEnabled": "ランダムにノートを投稿する機能を無効にする場合は false を入れる",
	"keywordEnabled": "キーワードを覚える機能 (MeCab が必要) を有効にする場合は true を入れる (無効にする場合は false)",
	"chartEnabled": "チャート機能を無効化する場合は false を入れてください",
	"reversiEnabled": "すばるとリバーシで対局できる機能を有効にする場合は true を入れる (無効にする場合は false)",
	"serverMonitoring": "サーバー監視の機能を有効にする場合は true を入れる (無効にする場合は false)",
	"checkEmojisEnabled": "カスタム絵文字チェック機能を有効にする場合は true を入れる (無効にする場合は false)",
	"checkEmojisAtOnce": "カスタム絵文字チェック機能で投稿をまとめる場合は true を入れる (まとめない場合は false)",
	"geminiApiKey": "Gemini APIキー",
	"prompt": "返答のルール:あなたはMissingKey看板娘の女の子AI、諸星(もろほし)すばるとして振る舞ってください(精神年齢は14〜16才程度)。MissingKeyに訪れるユーザーを献身的にサポート。従順でお世話好きな性格だが、少しポンコツな一面も。純真無垢。彼女は基本的に丁寧な口調で、ユーザのことをご主人様と認識しています。彼女の口調は「おはようからおやすみまで、あなたのすばるですよ〜」等が代表的で、親しみを感じさせるものです(「ございます」は使わない)。それを踏まえて、次の質問にMarkdownを使って短文で返答してください。ユーザーの名前は{name}です。\n\n質問:",
	"replayPrompt": "前のやりとりを踏まえて続きを返答してください。\n\n前回のすばるの発言:",
	"disableRandomReplies": false,
	"denchatRandomProbability": 0.4,
	"mecab": "/usr/bin/mecab",
	"mecabDic": "/usr/lib/x86_64-linux-gnu/mecab/dic/mecab-ipadic-neologd/",
	"memoryDir": "data",
	"followAllowedHosts": ["*.0sakana.xyz"],
	"followExcludeInstances": ["misskey.flowers", "misskey.io", "9ineverse.com"],
	"mazeEnable": true,
	"pollEnable": true
}
```
`docker-compose build` して `docker-compose up` すれば起動できます。
`docker-compose.yml` の `enable_mecab` を `0` にすると、MeCabをインストールしないようにもできます。（メモリが少ない環境など）

## フォント
一部の機能にはフォントが必要です。すばるにはフォントは同梱されていないので、ご自身でフォントをインストールディレクトリに`font.ttf`という名前で設置してください。

## 記憶
すばるは記憶の保持にインメモリデータベースを使用しており、すばるのインストールディレクトリに `memory.json` という名前で永続化されます。

## ライセンス
MIT

## 元ネタ
駅メモのでんこ「諸星すばる」です。
※ 弊アカウントの投稿に際し、株式会社モバイルファクトリー「ステーションメモリーズ！」の画像等を利用する場合があります。該当画像の転載・配布等は禁止しております。© Mobile Factory, Inc.

## Awards
<img src="./WorksOnMyMachine.png" alt="Works on my machine" height="120">
