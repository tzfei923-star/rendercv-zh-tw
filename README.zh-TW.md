# RenderCV 繁體中文工作台

基於 [RenderCV](https://github.com/rendercv/rendercv) 的非官方繁體中文延伸專案，面向台灣求職者、研究生及生醫研究人員。目前提供中文說明與虛構履歷範例；仍以 YAML 編輯內容、由 RenderCV 生成 PDF。

## 已完成與規劃中

| 狀態 | 內容 |
| --- | --- |
| 已完成 | 保留上游歷史與 MIT 授權、建立 v2.8 中文開發基準 |
| 已完成 | 繁體中文入門、Noto Sans TC / A4 範例及維護紀錄 |
| 規劃中 | 中文表單、段落排序、YAML 匯入匯出介面 |
| 規劃中 | PDF 預覽、另存職缺版本、Windows 啟動流程 |

目前沒有獨立中文網站。生成、驗證與排版引擎來自上游；本 fork 現階段新增中文說明、範例與維護流程。

## 快速開始

安裝 Python 3.12 以上與 [uv](https://docs.astral.sh/uv/getting-started/installation/)。以下指令使用官方 2.8 套件，不會安裝本 fork 尚在開發的功能。

```powershell
git clone --branch zh-tw https://github.com/tzfei923-star/rendercv-zh-tw.git
cd rendercv-zh-tw
uvx --from "rendercv[full]==2.8" rendercv render examples/zh-TW/Example_CV.yaml
```

輸出位於 `examples/zh-TW/rendercv_output/`。若缺少中文字型，先安裝 Noto Sans TC 再生成。

自己的履歷請放在 Git 忽略的 `private-cvs/`：

```powershell
New-Item -ItemType Directory -Force private-cvs
Copy-Item examples/zh-TW/Example_CV.yaml private-cvs/My_CV.yaml
uvx --from "rendercv[full]==2.8" rendercv render private-cvs/My_CV.yaml
```

修改 `My_CV.yaml` 後再次生成。`cv` 是內容、`design` 是排版、`locale` 是語系、`settings` 是輸出設定。語系設定不會自動翻譯履歷內容。

範例中的人物、機構、經歷及數字均為虛構，電子郵件使用 `example.com`。請替換為自己的真實經歷；本 fork 新增檔案不包含維護者的私人履歷或公司研究資料。

## 版本基準與差異（2026-09-14）

- 中文分支 `zh-tw` 基於官方 `v2.8`：`2eba248100726dc2f75e634bea6b77654e951d0d`。
- 建立時上游 `main`：`1d4b87bc427e4cf61c0ef49623c971b0e2224708`。
- 上游 main 比 v2.8 多 52 個提交：76 個檔案異動、3,171 行新增、1,597 行刪除。
- 差異包含日期驗證、bold_keywords、placeholder 處理、測試及依賴調整。
- 目前未合併這 52 個提交；中文範例以正式發布的 2.8 驗證，不代表已驗證上游 main 的所有功能。

## 維護方式

`origin` 指向本 fork；`upstream` 指向原作者。新功能從 `zh-tw` 建立獨立分支，優先新增設定、範例及周邊介面。保留套件原作者資訊，不以官方套件名稱將 fork 發布至 PyPI。

```powershell
# 首次 clone 後設定一次
git remote add upstream https://github.com/rendercv/rendercv.git
# 檢查上游更新
git fetch upstream --tags
git log --oneline zh-tw..upstream/main
git diff --stat zh-tw upstream/main
# 僅在審查分支試合併
git switch zh-tw
git switch -c maintenance/review-upstream
git merge upstream/main
```

處理衝突並驗證後，透過指向自己 fork 的 `zh-tw` 分支之 PR 合併。不 force push 已發布分支，也不移動上游版本標籤。

範例與文件修改需生成範例、檢查中文排版並執行 `git diff --check`；引擎或依賴異動另需執行上游檢查與相關測試。提交前確認清單不含個資。生成輸出與 `private-cvs/` 已加入 `.gitignore`。

## 原作者與授權

原作者為 Sina Atalay 與各貢獻者。本專案不是官方繁體中文版，也不代表原作者背書。保留原始 [MIT LICENSE](LICENSE) 及版權聲明；新增內容亦採 MIT 授權。原始英文說明保留於 [README.md](README.md)。
