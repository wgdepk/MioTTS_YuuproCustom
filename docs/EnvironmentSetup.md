# MioTTS ゆうぷろカスタム v1.0.0 動作環境構築ガイド

MioTTS ゆうぷろカスタムを動作させるために必要な環境と、セットアップの手順をまとめます。
現在は **Google Colab (GPU)** での動作を前提としています。

## 1. ハードウェア要件

- **GPU**: NVIDIA GPU (VRAM 4GB以上)
  - Google Colab では「T4 GPU」ランタイムで動作確認済みです。
  - 推奨モデル（1.7B）の場合、VRAM 約4GB を使用します。

## 2. 外部サービス・連携

- **Google Drive**:
  - 辞書データ、カスタムプリセット、生成音声の保存に使用します。
  - 初回実行時にマウント（アクセス許可）が必要です。

## 3. 必要なシステムツール (Linux/Colab)

以下のツールがプリインストールされているか、実行時にインストールされる必要があります。

- **Ollama**: LLM 推論エンジン（内部で llama.cpp を使用）。
- **ffmpeg**: 音声の話速調整（WSOLA方式）に使用。
- **zstd, pciutils**: Ollama のインストールやシステム情報の確認に使用。

## 4. Python ライブラリ要件

主要なライブラリは以下の通りです。

- **推論・演算**: `torch`, `numpy`, `ninja`, `Cython`, `accelerate`
- **音声処理**: `miocodec`, `pyopenjtalk`, `g2p_en`, `soundfile`, `nltk`
- **WebUI / API**: `gradio`, `fastapi`, `uvicorn`, `httpx`, `python-multipart`

## 5. モデルデータ

以下のモデルが自動的にダウンロード・使用されます。

- **TTSモデル**: `MioTTS-GGUF` (Aratako 氏提供)
  - サイズオプション: `0.1B`, `0.4B`, `0.6B`, `1.2B`, `1.7B` (推奨), `2.6B`
- **コーデック**: `MioCodec-25Hz-44.1kHz-v2`

## 6. セットアップ手順（Colab の場合）

1. **ランタイムのタイプを変更**: `GPU (T4)` を選択。
2. **すべてのセルを実行**: セルを順番に実行すると、以下の処理が自動で行われます。
   - Google Drive のマウント。
   - システムツール (Ollama 等) のインストール。
   - 依存 Python パッケージのインストール。
   - MioTTS-Inference リポジトリのクローン。
   - モデルのダウンロード。
   - API サーバおよび Gradio WebUI の起動。
3. **公開 URL にアクセス**: 実行完了後に表示される `gradio.live` のリンクをクリックして WebUI を開きます。
