# Sophia Discord Bot ドキュメント

## 概要
Sophiaは高機能なDiscord Botです。AI会話、RPGゲーム、音楽再生、家電制御、情報収集など、多彩な機能を提供します。

## 📊 プロジェクト統計
- **総ファイル数**: 31個
- **主要機能システム**: 8システム
- **Discordコマンド**: 76個（Slash Commands: 71個、Context Menus: 5個）
- **RPG装備組み合わせ**: 80,000通り以上
- **敵キャラクター**: 76種類

## 🚀 主要機能

### 🤖 メインシステム
- **AI会話機能**: Gemini 2.5 Flashを使用した自然言語処理
- **画像認識・解析**: マルチメディア対応
- **会話履歴管理**: ユーザー別応答調整

### 🎮 RPGシステム
- **レベルシステム**: メッセージ送信でEXP獲得
- **装備システム**: 7段階レアリティ（common〜unique）
- **戦闘システム**: ランダム敵とのバトル
- **ガチャシステム**: 3種類のガチャ（junk/influencer/vip）
- **インベントリ管理**: ソート・ページング機能

### 🎵 音楽システム
- **YouTube・Spotify対応**: URL/検索両対応
- **プレイリスト自動展開**: バックグラウンド処理
- **高品質音声ストリーミング**: FFmpeg使用
- **ループ再生**: 曲・キュー両対応

### 🏠 家電・環境監視システム
- **SwitchBot API連携**: PC電源・エアコン制御
- **環境センサー監視**: 温度・湿度・CO2・電力監視
- **自動アラート**: しきい値超過時の段階的警告

### 📰 情報収集システム ⚠️
- **RSSフィード監視**: 📰 **sophia_feed_monitor_cog.py [停止中]**
- **自発会話機能**: 💬 **sophia_proactive_cog.py [停止中]**
- **おみくじ機能**: AI生成運勢回答

### 📋 コンテキストメニュー
- **AI要約機能**: マルチメディア対応
- **スティッキーメッセージ**: チャンネル最下部固定表示
- **時間指定削除**: 6/12/24時間後削除
- **Embed変換**: リッチな埋め込み形式

## ⚠️ 現在の状況

### 停止中の機能
以下の機能は現在停止しています：

1. **📰 sophia_feed_monitor_cog.py**
   - RSSフィード監視機能
   - 10分間隔での自動フィード更新チェック
   - 新着記事の自動通知

2. **💬 sophia_proactive_cog.py**
   - 自発的会話機能
   - 1日1回のランダム時刻での投稿（12-20時）
   - 最もアクティブなチャンネルの自動選択

## 🛠️ 技術仕様

### 開発環境
- **言語**: Python 3.x
- **フレームワーク**: discord.py
- **AI API**: Google Gemini API
- **データベース**: SQLite
- **音声処理**: FFmpeg, yt-dlp

### 主要依存関係
- discord.py
- google-generativeai
- yt-dlp
- feedparser
- requests
- aiohttp

## 📝 設定

### 環境変数
```
# 必須
GOOGLE_API_KEY=          # Gemini AI API
DISCORD_BOT_TOKEN6=      # Discord Bot Token
SWITCH_BOT_TOKEN=        # SwitchBot API Token
SWITCH_BOT_CLIENT=       # SwitchBot Client Secret

# 音楽機能用
FFMPEG_PATH=             # FFmpeg実行パス
SPOTIFY_CLIENT_ID=       # Spotify API ID
SPOTIFY_CLIENT_SECRET=   # Spotify API Secret
```

### デバイス設定
```python
DEVICE_IDS = {
    "pc": "DEVICE_PC_ID",
    "ac": "DEVICE_AC_ID",
    "co2_meter": "DEVICE_CO2_ID",
    "plug_mini": "DEVICE_PLUG_ID"
}
```

## 📖 詳細ドキュメント

詳細な機能説明とファイル構造については、以下をご覧ください：
- [ファイル構造詳細](https://0rnot.github.io/SophiaDocument/FILE_STRUCTURE_VIEWER.html)

## 📈 コマンド一覧

### 主要コマンド
- `/restart4` - ソフィア再起動（開発者専用）
- `/switch_model` - AIモデル切り替え
- `/vlevel` - RPGレベル・ゴールド表示
- `/play <query>` - 音楽再生
- `/hv meter` - 環境センサー値表示
- `/q add <name> <url> <channel>` - RSSフィード監視追加

詳細なコマンド一覧は[ファイル構造詳細ページ](https://0rnot.github.io/SophiaDocument/FILE_STRUCTURE_VIEWER.html)をご参照ください。

## 🔄 更新履歴
- **2025-07-12**: ファイル構造ドキュメント更新
- **停止機能**: sophia_feed_monitor_cog.py, sophia_proactive_cog.py

---

*Sophia Discord Bot - 高機能Discord Botプロジェクト*
