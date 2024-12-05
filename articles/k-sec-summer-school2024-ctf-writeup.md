---
title: "K-SEC サマースクール2024 CTF writeup"
emoji: "⛳"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["CTF", "writeup", "K-SEC"]
published: false
---

[K-SEC(KOSENサイバーセキュリティ教育推進センター)](https://www.kosen-k.go.jp/Portals/0/K-SEC/)のサマースクール(9/11-12)で行われた「CTF超入門講座」に参加しました。

# 結果

![](/images/K-SEC-summer-school-2024/result.png)

1日目終了時点, 2日目終了時点で共に全問正解の1st placeで終えることが出来ました。

(ユーザー名がFlourite(蛍石)なのはちょうど手元に飾ってあったからです。)

# 問題/解答

いくつかの問題をピックアップします。

### Crypto/transform

CyberChefのMagic機能を有効活用出来た問題。

最初の`102, 108, 97, 103`が`flag`に対応すると考えた。

そのため、`input: 102`、`Magic -> Crib (known plaintext string or regex): f`とした。

![](/images/K-SEC-summer-school-2024/cyberchef-magic.png)

その結果、UTF-8のDecであることが分かりました。

### Web/【Attack】3. 防御の回避

SQLインジェクション攻撃の問題

`=`, `>`, `<`などが制限されていたため、`1' or '1' = '1';--` を`1' or TRUE;--` に書き換えた。

# 完走した感想

ほぼ初めてのCTFであったので、多くの新しい学びがありました。

その中でも重要だと感じたのが「とりあえずトライしてみる」ことです。
「違うだろうな...」と思った解法でも、それが正解であったり、重要な手がかりとなったりしたことが何度もありました。

また、時間内に問題を解くという部分は競技プログラミングに似ていると感じました。
問題が解けたときの達成感など、競プロと似たような楽しさもありましたが、競プロにはない楽しさや難しさもありました。
