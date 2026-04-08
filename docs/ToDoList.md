# ToDoList.md

## 1.0.0 動作環境構築
- [x] このコードを動作させるために必要なものをリストアップする (2026-04-07)

## 1.0.1 バージョン番号管理
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