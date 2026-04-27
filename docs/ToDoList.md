# ToDoList.md

プロジェクト実施予定リスト

## 実施予定


### 1.0.2 Google Drvieを開く機能の追加
- [ ] 「 生成音声を Google Drive に保存」の右側に、Google Drvieを開くためのアイコン（音声ファイルをイメージできるようなアイコン）を追加する。
- [ ] Google Drvie のWebサイトにアクセスし、 `/content/drive/MyDrive/MioTTS/outputs/` を自動で開く




## 実施済み

### 1.0.0 動作環境構築
- [x] このコードを動作させるために必要なものをリストアップする (2026-04-07)

### 1.0.1 バージョン番号管理
- [x] バージョン番号のハードコーディングを廃止して、package.jsonから読み込むようにする
- 例：
```python
with gr.Blocks(
    title="MioTTS ゆうぷろカスタム_V1.0.0",
    theme=gr.themes.Soft(),
) as app:

    gr.Markdown("# 🎙️ MioTTS ゆうぷろカスタム_V1.0.0")
・・・
print("🎙️ MioTTS ゆうぷろカスタム_V1.0.0")

```

## 文末