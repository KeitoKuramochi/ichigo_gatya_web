# ICHIGOガチャガチャ 紹介ページ(story)

`negotiate/index.html`とは別に、来場者が仕組み・あそびかた・制作秘話・制作動画を読める1ページ紹介サイト。デザイントークン・キャラクター画像は`negotiate/index.html`と共通(コピーして流用、共有パッケージ化はしていない)。

## 構成

```
story/
├── index.html   # 唯一のページ本体
├── assets/      # negotiate/assets/ から流用した画像
└── video/       # 制作動画(making-of.mp4)
```

## あとで差し替える場所

### 制作秘話・スタッフ紹介の写真
`.photoBox`の`<div>`プレースホルダー(「写真準備中」表示、`<!-- TODO -->`コメント付き)を、同じ`.photoBox`クラスを持つ`<img>`タグに置き換えるだけでよい(`aspect-ratio`/`object-fit`は`.photoBox`側で固定されているため崩れない)。

## 新規に生成すると良い画像素材(任意、`VISUAL_DESIGN_PROMPTS.md`と同じGoogle AI Studio運用)

「仕組み解説」のフロー図は現在SVGで手描きしているため無くても成立するが、他の素材と同じ手描きポスター風イラストにしたい場合は、`negotiate/assets/ichigoban-greet.png`を生成した同じ会話の続きで以下を依頼すると一貫性が保てる:

- `mechanism-diagram.png`: 送金→確認→カプセル排出の3場面を1枚にまとめた横長イラスト(文字なし)
- `video-poster.png`: 動画セクションの`poster`用、暖簾に「準備中」の正方形イラスト

## デプロイについて

このフォルダは別リポジトリ `https://github.com/KeitoKuramochi/ichigo_gatya_web.git`(Vercelデプロイ想定)に持っていく前提で、`ichigo`フォルダ内で作成・確認している。持っていく際はこの`story/`の中身をリポジトリのルートに配置する。
