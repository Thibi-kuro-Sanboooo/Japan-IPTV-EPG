# Japan-IPTV-EPG

日本向け IPTV 用の自動生成 EPG（XMLTV）公開リポジトリです。

生成プログラム本体は別リポジトリ `Japan-IPTV-EPG-Generator` で管理し、このリポジトリには検証を通過した生成物だけを公開します。

## 完成版 guides.xml

```text
https://raw.githubusercontent.com/Thibi-kuro-Sanboooo/Japan-IPTV-EPG/main/guides.xml
```

karenda-jp の基準EPGに含まれる **244チャンネル** の `tvg-id`・チャンネル名・アイコン互換を維持する方針です。

## 対応系統

- ABEMA
- JCOM系
- Rチャンネル
- Fast TV
- SkyPerfect / Bangumi系
- NHK World Premium
- BS10プレミアム
- TVerリアルタイム

各系統の単独XMLTVと比較レポートも公開しています。

## 更新

GitHub Actionsで毎日自動生成します。

- 実行時刻: **08:30 JST**
- 基本取得範囲: **2日分**
- 各取得元の生成・XMLTV検証・244局統合・互換比較がすべて成功した場合のみ更新

失敗した生成物で正常な公開版を上書きしないフェイルセーフ構成です。

## 主なファイル

```text
guides.xml                 244局を統合した本命EPG
guides-parity.md           karenda-jp基準との全体比較

abema.xml                  ABEMA
jcom.xml                   JCOM系
rakuten.xml                Rチャンネル
fasttv.xml                 Fast TV
skyperfect.xml             SkyPerfect / Bangumi系
nhkworldpremium.xml        NHK World Premium
bs10premium.xml            BS10プレミアム
tver.xml                   TVerリアルタイム
```

## 方針

- karenda-jp互換の `tvg-id` を維持
- 他者の完成済みEPGをコピーせず、可能な限り公式API・公式番組表・公式公開データから自前取得
- 現在の公式データを優先するため、karenda-jp側との更新時刻やタイトル表記の差が出る場合あり
- XMLTV検証や244局チェックに失敗した場合は公開しない
- 生成処理と公開データを別リポジトリで管理
