# imanyu_slide

[shiryo-slides-kit](https://github.com/code4biz/shiryo-slides-kit) の資料作成スキルを
このリポジトリに同梱しています。

## 使い方

このリポジトリを開いた Claude Code / Codex で、そのまま依頼するだけです。

- 「この議事録から提案資料を作って」
- 「勉強会向けに図解多めのスライドにして」
- 「このスライドを PDF にして」

16:9 の単一 HTML スライドが生成されます（PowerPoint ではありません）。

## スキルの置き場所

`.claude/skills/shiryo-slides/` — プロジェクト同梱のため、このリポジトリを
clone した環境ではセットアップ不要でそのまま使えます。

個人の全プロジェクトで使いたい場合は、ホーム配下にもコピーしてください。

```bash
mkdir -p ~/.claude/skills
cp -R .claude/skills/shiryo-slides ~/.claude/skills/
```

Codex CLI の場合は `~/.claude` を `~/.codex` に読み替えます。

## 前提ツール

- Node.js（LTS）
- Playwright + chromium — スライドを撮影して見た目を自己検証するために使います

```bash
npm install -g playwright
npx playwright install chromium   # 約 400MB
```

`npm -g` が権限エラーになる場合は、作業フォルダ内で `npm install playwright`
でも動作します（スキルはローカル / グローバル両方を探します）。

未導入でもスライド生成自体は可能ですが、視覚検証がスキップされます。

## 注意：Google Fonts が届かない環境

このキットは書体を Google Fonts から読み込みます。プロキシで塞がれた環境や
オフラインでは代替フォントで表示され、撮影時に警告が出ます。

**その状態でレイアウトを調整しないでください。** 代替フォントに合わせて文字サイズや
改行を直すと、フォントが届く環境では逆に崩れます。詳細は
[本家 README §7](https://github.com/code4biz/shiryo-slides-kit#readme) を参照してください。

## 由来

`.claude/skills/shiryo-slides/` は上流リポジトリの `skills/shiryo-slides/` を
無改変でコピーしたものです。

- 取得元: https://github.com/code4biz/shiryo-slides-kit
- コミット: `c29c35bc5fc2c719bdf44cbd3d71d807c47707ef`
- ライセンス: 上流リポジトリの LICENSE に従います

更新する場合は上流から取り直して差し替えてください（手を入れない運用が前提です）。
