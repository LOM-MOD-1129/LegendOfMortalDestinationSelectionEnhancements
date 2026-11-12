# 活俠傳 移動先選択画面拡張MOD

Steam版『活俠傳 / Legend of Mortal』の移動先選択を補助する非公式MOD。

バージョン：**1.1.0**

## 主な機能

- 移動先と消費行動力を一覧で確認し、施設名から移動先を選択。
- ゲーム標準の一覧画面に合わせた外枠・巻物・半透明背景・選択表示。
- マウス、キーボード、ゲームパッドに対応。
- F2で通常のマップ選択／一覧モードを切替。モードは次回起動にも引継ぎ。
- 選択表示を5種類から選択。F6で切り替え、次回起動にも引継ぎ。
- 「崆峒の日常」「青城の日常」「唐門会議」「休憩」「外出」の標準一覧にも同じ選択表示を適用。
- 移動先一覧の選択変更時に、標準の行動選択と同じ効果音を再生。
- ゲーム内の設定画面から、一覧モード・選択表示を変更。

## 対応環境

- ゲーム：Steam版『活俠傳 / Legend of Mortal』 v1.0.6001.0
- OS：Windows（確認環境：Windows 11）
- BepInEx：6.0.0-be.692（32-bit Mono）

## ダウンロード・導入

このリポジトリの **Releases → Latest**（URL末尾`/releases/latest`）のAssetsから、
`LegendOfMortalDestinationSelectionEnhancements.zip`をダウンロードして展開。

1. BepInEx 6を導入し、ゲームを終了。
2. 展開した`LegendOfMortalDestinationSelectionEnhancements`フォルダーをゲームの`BepInEx/plugins/`へコピー。
3. 更新時は同名のDLLを上書き。同じDLLを複数フォルダーへ重複配置しないこと。

```text
BepInEx/plugins/LegendOfMortalDestinationSelectionEnhancements/LegendOfMortalDestinationSelectionEnhancements.dll
```

ZIP内の`README_JP.txt`にも導入・基本操作・主な設定を記載。更新内容は[変更履歴](CHANGELOG.md)を参照。
配布ZIPのSHA-256は同じリリースに添付された`SHA256.txt`を参照。
Assetsの`Source code (zip)`・`Source code (tar.gz)`はリポジトリの自動アーカイブで、MODの配布ZIPとは別物。

## 操作と設定

一覧の行をホバーしてクリック、または上下入力で選びゲームの決定ボタンで確定。
11件を超える場合は上下移動でページを切替。F2で通常操作へ切替可能。
F6で従来表示・行背景・左線・三角マーカー・行枠を切替。文字の縁取りと選択中の移動先・ページは維持。
標準の対象一覧でも表示方式を共有。施設内のアイコン付き行動選択、通常の会話選択肢、ダイス画面は対象外。
選択音の音量はゲームの効果音設定に従う。

ゲームの環境設定画面で、「MOD設定」の「移動先選択画面拡張」を選択。
「選択項目の強調」を選ぶと、下の表示例で見た目を確認可能。
変更は自動保存され、F2・F6での変更とも共通。「戻る」またはキャンセル操作で元の設定画面へ戻る。
右上の「×」をクリックすると、MOD設定とゲーム本体の設定画面をまとめて閉じる。
対応する他のMODを導入すると、その設定ボタンも同じ場所に並ぶ。

キー割り当てなどを変更する場合は、初回起動後にゲームを終了し、`BepInEx/config/lom.jp.destination.selection.enhancements.cfg`を編集。

`true`は有効、`false`は無効。変更後にゲームを起動。

| セクション | 項目 | 初期値 | 説明 |
|---|---|---|---|
| `[General]` | `Enabled` | `true` | MOD全体の有効／無効。 |
| `[General]` | `ListModeEnabled` | `true` | 一覧モードの有効／無効。F2の変更も保存。 |
| `[Input]` | `ToggleKey` | `F2` | モード切替キー。 |
| `[Appearance]` | `SelectionStyle` | `Original` | Original（従来）／RowBackground（行背景）／LeftLine（左線）／TriangleMarker（三角マーカー）／RowOutline（行枠）。F6の変更も保存。 |
| `[Input]` | `CycleSelectionStyleKey` | `F6` | 表示切替キー。F1～F12、Noneで無効。モード切替キーとの重複は不可。 |

F2と`ListModeEnabled`はマップの一覧化だけに適用。標準一覧の追加表示も停止する場合は`Enabled`を`false`へ変更。
MOD全体の有効／無効は設定ファイルだけで変更可能。再び有効にする場合は、ゲーム終了中に`[General] Enabled`を`true`へ戻す。

### 不具合調査用

| セクション | 項目 | 初期値 | 説明 |
|---|---|---|---|
| `[Debug]` | `EnableDiagnosticLogging` | `false` | 不具合調査用の診断ログ。通常は無効で使用。 |
| `[Debug]` | `DiagnosticLogLevel` | `Info` | Error／Info／Trace。後のものほど詳細な診断を含む。診断有効時に適用。 |

診断ログは`BepInEx/LogOutput.log`へ出力。共有前にログ内容を確認すること。

## 注意・削除

- ゲーム更新により画像や内部構造が変わると、簡易表示になる、または通常操作へ戻る場合がある。
- 移動条件・消費行動力・イベントはゲーム本来の処理に従う。他MODとの組み合わせで正常に動作しない場合がある。
- ログ・ステータス・システム画面やイベント処理中は一覧を休止。

ゲーム終了後に`BepInEx/plugins/LegendOfMortalDestinationSelectionEnhancements`を削除。
設定も不要なら`BepInEx/config/lom.jp.destination.selection.enhancements.cfg`を削除可能。

## ライセンス

[MIT License](LICENSE)。配布ZIPにも同内容の`LICENSE.txt`を同梱。
ゲーム本体と第三者の著作物へ本MODのライセンスが適用されるものではない。
