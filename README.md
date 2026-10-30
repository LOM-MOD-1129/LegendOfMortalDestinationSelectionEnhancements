# 活俠傳 Destination Selection Enhancements

Steam版『活俠傳 / Legend of Mortal』の移動先選択を補助する非公式MODです。

現在の配布版：**1.0.2**

## 主な機能

- 移動先と消費行動力を一覧で確認し、施設名から移動先を選択。
- ゲーム標準の一覧画面に合わせた外枠・巻物・半透明背景・選択表示。
- マウス、キーボード、ゲームパッドに対応。
- F2で通常のマップ選択／一覧モードを切替。モードは次回起動にも引継ぎ。

## 対応環境・注意

- Steam版『活俠傳 / Legend of Mortal』、Windows、BepInEx 6。
- ゲーム更新により画像や内部構造が変わると、簡易表示になる、または通常操作へ戻る場合があります。
- 現行1.0.2の実ゲーム確認と性能実測は未実施です。自動検証とビルド確認は実ゲームでの動作保証ではありません。
- 移動条件・消費行動力・イベントはゲーム本来の処理に従います。他MODとの組合せで正常に動かない場合があります。

## ダウンロード・導入

このリポジトリの **Releases → Latest**（URL末尾`/releases/latest`）のAssetsから、
`LegendOfMortalDestinationSelectionEnhancements.zip`をダウンロードして展開してください。

1. BepInEx 6を導入し、ゲームを終了。
2. 展開した`LegendOfMortalDestinationSelectionEnhancements`フォルダーをゲームの`BepInEx/plugins/`へコピー。
3. 更新時は同名のDLLを上書き。同じDLLを複数フォルダーへ重複配置しないでください。

```text
BepInEx/plugins/LegendOfMortalDestinationSelectionEnhancements/LegendOfMortalDestinationSelectionEnhancements.dll
```

詳しい操作はZIP内README_JP.txtを、更新内容は[変更履歴](CHANGELOG.md)を参照してください。
SHA-256は同じリリースのSHA256.txtに記載しています。
GitHubが表示するSource code (zip/tar.gz)はこの案内用リポジトリの自動アーカイブで、MODの配布ZIPではありません。

## 操作と設定

一覧の行をホバーしてクリック、または上下入力で選びゲームの決定ボタンで確定します。
11件を超える場合は上下移動でページを切り替えます。F2で通常操作へ戻せます。

初回起動後にゲームを終了し、`BepInEx/config/lom.jp.destination.selection.enhancements.cfg`を編集します。

| セクション | 項目 | 初期値 | 説明 |
|---|---|---|---|
| General | Enabled | true | MOD全体の有効／無効。 |
| General | ListModeEnabled | true | 一覧モードの有効／無効。F2の変更も保存。 |
| Input | ToggleKey | F2 | モード切替キー。 |
| Debug | EnableDiagnosticLogging | false | 不具合調査用の診断ログ。通常は無効で使用。 |
| Debug | DiagnosticLogLevel | Info | Error／Info／Trace。後のものほど詳細な診断を含む。診断有効時に適用。 |

診断はBepInEx/LogOutput.logへ出力します。共有前にログ内容を確認してください。
ログ・状態・システム画面やイベント処理中は一覧を休止します。

## 削除

ゲーム終了後に`BepInEx/plugins/LegendOfMortalDestinationSelectionEnhancements`を削除してください。

## ライセンス

[MIT License](LICENSE)。配布ZIPにも同内容のLICENSE.txtを同梱しています。
ゲーム本体と第三者の著作物へ本MODのライセンスが適用されるものではありません。
