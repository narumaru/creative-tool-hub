# CREATIVE DESK

日本語の制作ツール入口ページ。静的HTML/CSSで動作し、外部フォント・アクセス解析は不要です。公開時にGitHub Actionsが公式PhotoCraftを取得して静的サイトを組み立てます。

## 入口

- **JIZURA**: [公式サイト](https://852wa.github.io/JIZURA/)に移動する文字アニメーション制作ツール。
- **PhotoCraft**: `./photocraft/` に置いた公式配布版 v0.2.0。公式配布物・ライセンス・NOTICEを保ったまま利用します。PC推奨。初回読み込み約27MB。
- **Video Ideas**: [awesome-opus5-5-videos の prompts](https://github.com/yihui-dev/awesome-opus5-5-videos/tree/main/prompts) を開く参考資料。動画生成機能はありません。作例・第三者素材の無制限な商用利用を保証するものではありません。

GitHubの公開リポジトリで `main` ブランチと `prompts/` の存在を2026-10-05に確認しました。

## ファイル

- `index.html`: 入口・使い方・トラブル時のヒント
- `style.css`: レスポンシブレイアウト、キーボードフォーカス、動きを減らす設定への対応
- `favicon.svg`: オリジナルのシンプルなデスクマーク
- `404.html`: 見つからないページ。GitHub PagesのプロジェクトサイトではURLの第1階層をホームとして扱います
- `.nojekyll`: GitHub PagesによるJekyll処理を無効化
- `.github/workflows/pages.yml`: GitHub Pagesへの公開。公式ZIPのSHA-256を確認してから配置
- `PHOTOCRAFT-PROVENANCE.json`: 公式配布元・バージョン・検証用ハッシュ。必要なNOTICEと素材ライセンスは同じ上流コミットから公開時に取得
- `photocraft/`: 公開時に公式配布版から生成されます。アプリ本体は改変しません

## ローカル確認

入口ページだけのローカル確認は、このフォルダをHTTPサーバーのルートとして配信してください。例:

```sh
python3 -m http.server 8000
```

`http://localhost:8000/` を開きます。PhotoCraftも確認する場合は、ワークフローと同じ公式ZIPを検証・展開し、`photocraft/` に配置します。WASM読み込みにはHTTP配信が必要です。

## 注意

- 全ての制作ツールと外部資料は、新しいタブで開きます。
- 入口ページはアップロード・保存・分析用の通信を実装していません。ホスティングと外部リンク先には各サービスの条件が適用されます。
- PhotoCraftの動作・保存・書き出し可否は端末とブラウザに依存します。このREADMEは実機での書き出し成功を保証するものではありません。
- トラブル時の選択肢として、v0.2.0のソースで確認した `?webgl` と `?cpu` の起動リンクを掲載しています。CPUモードでもUIにはWebGPU / WebGL2が必要です。
- 未保存の作業を失わないよう、閉じる前に保存・書き出しを確認してください。
- 楽曲、歌詞、写真、フォント、参考作例などの権利は、それぞれ確認が必要です。

## PhotoCraft配布物

- 公式配布ページ: https://getartcraft.com/apps/photocraft
- バージョン: v0.2.0
- 上流コミット: `ad863217386440ca968fccc9bfff65ba24e61142`
- ZIP SHA-256: `a03e6118beed115eac25e6f0d11d3a3b3a3624538bf8a77dbaebf2352bf48e5f`
- 公式HTML/JavaScript/WebAssemblyは無改変。補足のNOTICEと素材ライセンスのみ追加
- ブランド表記はPhotoCraftの制作者を示すためのもので、この入口ページへの推奨・提携を意味しません
