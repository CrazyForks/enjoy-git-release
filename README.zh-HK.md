<p align="center">
  <img width="150" src="https://enjoygit.com/images/logo.png">
</p>

[English](./README.md) | [簡體中文](./README.zh-CN.md) | 繁體中文（香港）

# [官網](https://enjoygit.com) · [私隱政策](https://enjoygit.com/privacyPolicy.html) · [官網源碼](./website/)

# Enjoy Git - 簡易高效的 Git 客戶端

一款現代化的 Git 圖形客戶端，採用 Electron、Vue 3 與 TypeScript 構建。支援多倉庫分頁並行、行級暫存與差異審閱、視覺化提交圖，以及完整的分支、遠端、標籤與貯藏管理。

---

## 支援平台

| 平台 | 版本 / 形態 | 架構 | Git |
|------|-------------|------|-----|
| **Windows** | Windows 10、Windows 11 | x64、arm64 | **內建**（dugite-native），開箱即用 |
| **macOS** | macOS 10.15 及以上 | x64（Intel 舊款 Mac）、arm64（Apple Silicon M1 及較新機型） | **內建**（dugite-native），開箱即用 |
| **Linux** | Debian 系（`.deb`）、Red Hat 系（`.rpm`） | x64、arm64 | 使用**系統環境**中的 Git，需預先安裝 |

> **Git 說明**：Windows 與 macOS **已內建 Git**（dugite-native），安裝後即可使用。Linux 需使用系統環境中的 Git，請提前安裝（例如 `sudo apt install git`、`sudo dnf install git`），並確保終端可執行 `git` 指令。

---

## 支援的語言

應用程式介面支援以下三種語言，可在選單列 **Language** 中切換：

1. **簡體中文**
2. **繁體中文**（應用程式內選項）
3. **English（英語）**

---

## 支援的主題

1. **深色模式**
2. **淺色模式**

---

## 選單列

應用程式提供完整的選單列，常用操作均可透過選單或快捷鍵完成（以下為 macOS 範例，Windows / Linux 選單位置可能略有不同）。

### Enjoy Git（應用程式選單）

![應用程式選單](docs/images/menu-app.png)

| 選單项 | 說明 |
|--------|------|
| About Enjoy Git | 檢視版本與關於資訊 |
| Quit Enjoy Git | 結束應用程式（`⌘Q`） |

### File（檔案）

![檔案選單](docs/images/menu-file.png)

| 選單项 | 快捷鍵 | 說明 |
|--------|--------|------|
| Create New Repository | `⌘N` | 在本機新建空倉庫 |
| Open Repository | `⌘O` | 開啟已有本機倉庫 |
| Clone Repository | `⇧⌘O` | 複製遠端倉庫 |
| Add All Repositories in Local Directory | — | 批次新增指定目錄下的所有 Git 倉庫 |

### View（檢視）

![檢視選單](docs/images/menu-view.png)

| 選單项 | 快捷鍵 | 說明 |
|--------|--------|------|
| Show Local Changes | `⌘1` | 切換到本機變更檢視 |
| Show Commit History | `⌘2` | 切換到提交歷史檢視 |
| Show Tag List | `⌘3` | 切換到標籤列表檢視 |
| Reset Zoom | `⌘0` | 重設介面縮放（顯示目前比例，如 110%） |
| Zoom In / Zoom Out | `⌘=` / `⌘-` | 放大 / 縮小介面 |
| Switch to Dark Mode / Light Mode | — | **切換深色 / 淺色主題** |
| Toggle Developer Tools | `⌥⌘I` | 開啟開發者工具 |

### Repository（倉庫）

![倉庫選單](docs/images/menu-repository.png)

| 選單项 | 快捷鍵 | 說明 |
|--------|--------|------|
| Push | `⇧⌘P` | 推送到遠端 |
| Pull | `⇧⌘L` | 從遠端拉取 |
| Fetch | `⇧⌘T` | 取得遠端更新 |
| Quick Switch Repository | `⌘P` | 快速切換已開啟的倉庫 |
| Refresh Repository Status | `⌘U` | 重新整理倉庫狀態 |
| Open in Terminal | `⌃\`` | 在終端機中開啟目前倉庫 |
| Reveal in Finder | `⇧⌘F` | 在Finder / 檔案總管中顯示倉庫 |
| Edit .gitignore | `⌘I` | 編輯 `.gitignore` |
| Close Repository | `⌘⌫` | 關閉目前倉庫標籤 |

### Language（語言）

![語言選單](docs/images/menu-language.png)

在 **Language** 選單中勾選一種介面語言，立即生效：

- 簡體中文
- 繁體中文
- English

### Help（說明）

![說明選單](docs/images/menu-help.png)

| 選單项 | 說明 |
|--------|------|
| Configure External Open Program | 設定外部開啟程式（見下文） |
| View Today's Log | 檢視當日日誌 |
| Open Logs Directory | 開啟日誌目錄 |
| View Config File | 檢視設定檔案 |
| Open Config Directory | 開啟設定目錄 |
| SSH Key Management | SSH 金鑰管理（見下文） |
| AI Commit | AI 提交訊息設定（見下文） |
| Report Issue | 意見問題 |
| Contact Me | 聯絡開發者 |
| Release Notes | 檢視發行說明 |

---

## 設定與工具

以下功能均從 **Help** 選單進入。

### 外部開啟程式

可將 Cursor、VS Code、Trae 等編輯器註冊為外部程式，在檔案右鍵 **開啟**、**透過外部程式開啟** 時使用；支援設定一個**預設**程式。

![管理外部程式](docs/images/settings-external-programs.png)

| 能力 | 說明 |
|------|------|
| 新增外部程式 | 選擇本機已安裝的應用（`.app` / 可執行檔案） |
| 編輯 / 刪除 | 维护名稱與路徑 |
| 設為預設 | 勾選 Default，作為「開啟」時的首選 |
| 使用場景 | 工作區檔案、歷史版本、提交快照中的檔案均可外部開啟 |

### SSH 金鑰管理

便於設定存取 Git 遠端倉庫（GitHub、GitLab 等）所需的 SSH 公鑰，無需手動編輯 `~/.ssh`。

![SSH 金鑰管理](docs/images/settings-ssh-keys.png)

| 能力 | 說明 |
|------|------|
| Create Key | 在應用程式內產生新的 SSH 金鑰對 |
| Import Key | 匯入本機已有金鑰 |
| 金鑰列表 | 顯示公鑰檔案名與路徑（如 `id_rsa.pub`） |
| 快捷操作 | 開啟所在檔案夹、複製公鑰內容、刪除金鑰 |

### AI 提交訊息

接入大模型，根據暫存變更**自動產生提交說明**，減少手寫 commit message 的時间。

![AI Commit 設定](docs/images/settings-ai-commit.png)

| 設定项 | 說明 |
|--------|------|
| Reply language | 產生說明的語言（如 `English`、`zh-CN`；留空則跟隨應用程式介面語言） |
| AI 模型列表 | 可新增多個模型，勾選一個作為目前使用 |
| Add AI Model | 新增模型設定 |

![新增 AI 模型](docs/images/settings-add-ai-model.png)

新增模型時需填寫：

| 欄位 | 說明 |
|------|------|
| Provider | 選擇 AI 服務商（必填） |
| Model | 模型名稱，如 `deepseek-chat`（必填） |
| API Key | 對應服務的 API 金鑰 |

設定完成後，在提交區域即可使用 AI 產生提交說明（具體入口以應用程式內按鈕為準）。

---

## 功能概覽

| 模組 | 核心能力 |
|------|----------|
| 選單列 | File / View / Repository / Language / Help 完整選單與快捷鍵 |
| 多倉庫 | 分頁同時開啟多個本機倉庫，各自保留檢視狀態 |
| 工作區 | 已暫存 / 未暫存分区、**列表 / 檔案樹**切換檢視、關鍵字篩選、檔案右鍵操作 |
| 差異審閱 | 統一 / 雙欄檢視、語法高亮、行級暫存、上下文摺疊、圖片 diff |
| 提交 | 摘要與詳情、Amend、跳過鉤子、提交並推送、**AI 產生說明** |
| 歷史 | 提交圖、搜尋篩選、提交詳情、變更**列表 / 檔案樹**檢視、目錄快照、多選批次操作 |
| 分支 / 遠端 | 檢出、合併、變基、追蹤、重新命名、遠端 Fetch / 編輯 / 批次檢出 |
| 標籤 / 貯藏 | 標籤檢出與刪除、貯藏應用 / 弹出 / 重新命名 |
| 設定 | **外部程式**、**SSH 金鑰**、**AI 提交**、日誌與設定目錄 |
| 進階 | Cherry-pick、Squash、Revert、Blame、視覺化衝突解決 |

---

## 功能詳解

### 一、主介面與多倉庫管理

深色與淺色主題下的三栏布局：左侧導覽、中间檔案列表、右側 diff 與提交区。

| 主題 | 预览 |
|------|------|
| 深色模式 | ![主介面 - 深色模式](docs/images/main-interface-dark.png) |
| 淺色模式 | ![主介面 - 淺色模式](docs/images/main-interface-light.png) |

#### 頂部工具栏

| 操作 | 說明 |
|------|------|
| **取得（Fetch）** | 從遠端拉取最新引用，不自動合併到目前分支 |
| **拉取（Pull）** | 拉取並整合遠端變更（支援普通 / Rebase 模式） |
| **推送（Push）** | 開啟 [推送對話框](#推送對話框)，設定分支、遠端與推送选项 |
| **貯藏（Stash）** | 開啟 [貯藏對話框](#貯藏對話框)，貯藏全部或部分檔案 |
| **新建分支** | 從 HEAD、標籤、提交或遠端分支建立分支 |
| **新增本機倉庫** | 將本機已有 Git 倉庫加入工作區 |

#### 推送對話框

點擊工具栏 **Push**、選單 **Repository → Push**（`⇧⌘P`）或分支右鍵 **推送到遠端倉庫**，開啟推送設定對話框。

![推送對話框](docs/images/push-dialog.png)

| 元素 | 說明 |
|------|------|
| 标题 | 如 `Push 'main' to 'origin'`，标明本機分支與目標遠端 |
| **Branch**（必填） | 選擇要推送的本機分支 |
| **Remote**（必填） | 選擇目標遠端（如 `origin`） |
| **Push to**（必填） | 推送到遠端的哪条分支（如 `origin/main`）；右側 **+** 可新建遠端分支 |
| **Push all tags to 'origin'** | 一並推送所有本機標籤 |
| **Push all branches to 'origin'** | 推送所有本機分支 |
| **Force Push** | 强制推送（`--force`，請謹慎使用） |
| **Push** | 執行推送 |
| **Hide** | 關閉對話框 |

#### 多倉庫分頁

- 頂部標籤同時開啟多個倉庫（如 `enjoy-git`、`electron` 等），一鍵切換
- 每个標籤獨立保留分支、暫存與檢視狀態

#### 系統快捷入口

| 入口 | 說明 |
|------|------|
| **在終端機開啟** | 在系統終端機中開啟目前倉庫目錄 |
| **在Finder顯示** / **檔案總管** | 在系統檔案管理器中定位倉庫根目錄 |

#### 左侧工作空间

| 入口 | 說明 |
|------|------|
| **本機變更** | 顯示未提交變更數量，進入暫存與提交流程 |
| **提交歷史** | 檢視提交圖、列表與單次提交詳情 |
| **標籤列表** | 瀏覽與管理 Git 標籤 |

側欄还提供**本機分支**、**遠端**、**標籤**、**貯藏**樹形列表，並支援關鍵字篩選。

---

### 二、工作區與暫存区

![暫存区與差異预览](docs/images/staged-files-with-diff.png)

#### 檔案列表

- **已暫存 / 未暫存** 分区展示，帶數量角標
- **狀態圖示**：綠色「+」新增；黃色圓點已修改
- **變更統計**：顯示變更檔案數及总行數 `+新增 -刪除`（如 `5 changed files +387 -8`）
- **關鍵字篩選**：頂部搜尋框按檔案名快速篩選

#### 列表 / 檔案樹檢視

變更檔案支援两种展示方式，透過篩選栏右側圖示一鍵切換（**本機變更**、**提交歷史**中的變更列表均可用）：

| 檢視 | 說明 |
|------|------|
| **列表檢視** | 扁平列出所有變更檔案，適合檔案较少、快速定位 |
| **檔案樹檢視** | 按目錄层级摺疊展示，適合大型變更、按模組瀏覽 |

![變更檔案 - 列表檢視](docs/images/changed-files-list-view.png)

![變更檔案 - 檔案樹檢視](docs/images/changed-files-tree-view.png)

- 檔案夹可展開 / 收起，子路徑下的變更高亮顯示
- 與 **Changes（差異檔案）** / **File Tree（檔案樹）** 分頁配合：前者看本次變更列表，後者在提交歷史中可檢視該提交時刻的完整倉庫目錄快照

#### 批次操作

| 區域 | 按鈕 | 說明 |
|------|------|------|
| 已暫存 | 取消暫存所有 / 取消所選暫存 | 移回未暫存区 |
| 未暫存 | 暫存所有 / 暫存所選 | 加入暫存区 |

#### 未暫存檔案右鍵選單

![未暫存檔案右鍵選單](docs/images/unstaged-file-context-menu.png)

| 選單項 | 說明 |
|--------|------|
| 捨棄變更 | 恢復為 HEAD 版本 |
| 暫存 | 將目前檔案加入暫存區 |
| 歷史記錄 | 開啟單檔案提交歷史 |
| 按行審閱 | `git blame` 行級溯源 |
| 在 Finder 中顯示 | `Cmd+Shift+F`（macOS；Windows / Linux 為對應系統檔案管理器） |
| 開啟 | 使用預設外部程式開啟檔案 |
| 開啟方式 | 子選單：選擇 [外部開啟程式](#外部開啟程式) 中設定的編輯器 |
| 貯藏 | 貯藏目前檔案（可區分已暫存 / 未暫存） |
| 複製路徑 | 複製檔案絕對路徑 |
| 複製相對路徑 | 複製相對於儲存庫根目錄的路徑 |

---

### 三、差異對比（Diff）

- **統一檢視 / 雙欄檢視** 可切換，支援**忽略空格**
- **語法高亮**：Vue、JavaScript、TypeScript、Markdown、Python 等
- **變更高亮**：綠色 `+` 新增，红色 `-` 刪除
- **圖片 diff** 预览；**虛擬列表** 大檔案也流暢
- 可在 diff 中**直接編輯**工作區檔案

#### 雙欄對比

![雙欄差異對比](docs/images/diff-side-by-side.png)

![雙欄差異與构造选项](docs/images/diff-side-by-side-options.png)

#### 上下文摺疊

![向上展開](docs/images/diff-expand-up.png)

![向下展開](docs/images/diff-expand-down.png)

| 操作 | 說明 |
|------|------|
| 向上展開 | 向目前變更塊上方展開更多上下文行 |
| 向下展開 | 向目前變更塊下方展開更多上下文行 |

#### 行級暫存（Hunk 操作）

在 diff 中選取程式碼行（高亮顯示）後右鍵，可進行行級暫存、取消暫存或捨棄等操作：

![行級暫存](docs/images/diff-line-staging-hunk.png)

| 選單項 | 說明 |
|--------|------|
| 複製 | 複製選中內容 |
| 將選中行加入暫存區 | 僅暫存選中行（部分提交） |
| 捨棄選中行 | 放棄選中行修改 |
| 展開整個檔案 | 顯示完整檔案 diff |

已暫存檔案中選中行時，選單會顯示「將選中行移出暫存區」。

---

### 四、提交

主介面底部提交区：

| 功能 | 說明 |
|------|------|
| 提交說明 | 單行摘要 + 可選詳細描述 |
| AI 產生說明 | 根據暫存變更自動產生 commit message（需先在 [AI 提交訊息](#ai-提交訊息) 中設定模型） |
| 修改最後一次提交（Amend） | 將本次變更合併进上一次提交 |
| 跳過提交鉤子 | 等效 `git commit --no-verify` |
| 提交並推送 | 提交後自動推送到遠端 |
| 提交按鈕 | 顯示檔案數與目標分支，如「提交 6 个檔案到 'dev'」 |

存在未解決衝突時，按鈕會提示「請先解決衝突」。

---

### 五、提交歷史

![提交歷史總覽](docs/images/commit-history-overview.png)

- **提交圖（Graph）**：彩色線條與節點展示分支、合併關係
- **提交列表**：說明、作者頭像、短 SHA、相對時间
- **搜尋篩選**：按提交說明關鍵字搜尋（回车觸發）
- **分支篩選**：限定檢視特定分支歷史

#### 提交右鍵選單

![提交右鍵選單](docs/images/commit-context-menu.png)

| 操作 | 說明 |
|------|------|
| 檢出提交 | 切換到該提交（分離 HEAD） |
| 還原提交（Revert） | 產生反向提交 |
| 撤銷提交（Undo） | 撤銷最近一次提交並保留變更 |
| 從提交建立分支 / 標籤 | 開啟建立分支或打標籤對話框 |
| 揀選提交（Cherry-pick） | 開啟對話框，選擇目標分支後應用變更 |
| 編輯提交說明 | 修改 commit message |
| 刪除提交 | 從歷史中移除 |
| 複製 SHA / 複製提交說明 | 快捷複製 |

#### 多選批次操作

![多選提交操作](docs/images/commit-multi-select.png)

選中多個提交後可：**Cherry-pick**、**Squash 壓縮**、**刪除**、複製 SHA 與說明；右側匯總顯示變更檔案與 diff。

#### 揀選提交（Cherry-pick）

在提交歷史中單選或多選提交後，透過右鍵 **Cherry-pick Commit** 或批次選單 **Cherry-pick N Commits** 開啟揀選對話框，選擇要將變更應用到的**目標分支**。

![揀選提交對話框](docs/images/cherry-pick-dialog.png)

| 元素 | 說明 |
|------|------|
| 标题 | 顯示待揀選的提交數量，如 `Cherry-pick 4 Commits` |
| 提示 | 若本機分支與遠端分支同名，不允許揀選到該分支；此類遠端分支預設隱藏 |
| 關鍵字篩選 | 在分支列表中快速搜尋目標分支 |
| 分支列表 | 展示本機與遠端分支，含相對時间；目前分支帶勾選標記 |
| 確認按鈕 | 文案隨所選分支變化，如 `Cherry-pick 4 commits to 'origin/1-4-x'` |

確認後，所選提交的變更將依序應用到目標分支；若產生衝突，將進入 [衝突解決](#十二衝突解決) 流程。

#### 提交詳情與檔案瀏覽

![提交詳情](docs/images/commit-detail-view.png)

右側面板展示完整說明、作者、電郵、時间、SHA、父提交及 PR 連結等。

| 分頁 | 說明 |
|--------|------|
| **Changes（差異檔案）** | 該次提交的變更檔案；支援 [列表 / 檔案樹](#列表--檔案樹檢視) 两种布局，顯示 `+行數 -行數`，點擊檢視 diff |
| **File Tree（檔案樹）** | 該提交時刻的**完整**倉庫目錄快照（唯讀瀏覽） |

![提交檔案樹](docs/images/commit-file-tree.png)

#### 歷史檔案右鍵選單

![歷史檔案右鍵選單](docs/images/history-file-context-menu.png)

| 選單项 | 說明 |
|--------|------|
| 在Finder顯示 | 定位檔案 |
| 開啟 · 最新版本 / 目前选定版本 | 對比不同版本 |
| 透過外部程式開啟 | 子選單選擇應用 |
| 檢視檔案歷史 / 按行審閱 | 歷史與 blame |
| 將檔案重設到提交時狀態 / 提交前狀態 | 還原檔案 |
| 在檔案樹中顯示 | 跳轉到檔案樹並高亮 |
| 複製路徑 / 複製相對路徑 | 快捷複製 |

---

### 六、分支管理

![分支右鍵選單](docs/images/branch-context-menu-en.png)

| 操作 | 說明 |
|------|------|
| 檢出 | 切換到該分支 |
| 推送到遠端倉庫 | 開啟 [推送對話框](#推送對話框) |
| 合併到另一個分支 | Merge |
| 將另一個分支變基到目前分支 | Rebase |
| 新建分支 | 開啟 [建立分支](#新建分支對話框) 對話框 |
| 追蹤遠端分支 | 建立 upstream 追蹤 |
| 重新命名 / 刪除 | 分支生命週期管理 |
| 複製分支名 / 複製遠端分支名 | 快捷複製 |

支援從 **HEAD / 標籤 / 提交 / 遠端分支** 作為起點新建分支（工具栏 **新建分支**、側欄按鈕或右鍵 **Create Branch** 均可開啟對話框）。

#### 新建分支對話框

![建立分支對話框](docs/images/create-branch-dialog.png)

| 元素 | 說明 |
|------|------|
| **Name**（必填） | 輸入新分支名稱 |
| **New branch based on** | 顯示建立起點類型與說明，如 `Branch (main) docs: update Notification...`，即基於某分支、提交或標籤 |
| **Checkout after create** | 勾選後建立完成自動檢出到新分支 |
| **Create Branch** | 確認建立 |
| **Hide** | 關閉對話框 |

建立起點取決於觸發位置：在側欄某分支上右鍵則基於該分支；在提交歷史上右鍵 **Create Branch from Commit** 則基於該提交。

---

### 七、遠端倉庫管理

![遠端右鍵選單](docs/images/remote-context-menu-en.png)

在遠端名（如 `origin`）上右鍵：

| 操作 | 說明 |
|------|------|
| 取得 origin | 僅從該遠端 Fetch |
| 編輯 origin | 修改名稱或 URL（HTTP / SSH） |
| 取消關聯 / 移除 | 刪除遠端設定 |
| 檢出所有分支 | 為遠端全部分支建立本機追蹤分支 |
| 複製名稱 / 複製遠端 URL | 快捷複製 |

支援**多個遠端**的增刪改查。側欄 **Remotes** 區域可新增新遠端，開啟 [新增遠端對話框](#新增遠端對話框)。

#### 新增遠端對話框

![新增遠端對話框](docs/images/add-remote-dialog.png)

| 元素 | 說明 |
|------|------|
| **Name**（必填） | 遠端名稱，如 `origin`、`upstream` |
| **URL**（必填） | 遠端倉庫位址，支援 HTTPS / SSH |
| **Add remote** | 新增遠端並儲存設定 |
| **Hide** | 關閉對話框 |

新增成功後，可在側欄展開該遠端，執行 Fetch、檢出分支或 [推送](#推送對話框) 等操作。

#### 遠端分支

![遠端分支右鍵選單](docs/images/remote-branch-context-menu.png)

| 操作 | 說明 |
|------|------|
| 檢出 | 檢出遠端追蹤分支 |
| 新建分支 | 基於遠端分支建立本機分支 |
| 刪除 | 刪除遠端分支 |
| 複製名稱 | 複製分支名 |

---

### 八、標籤管理

![標籤右鍵選單](docs/images/tag-context-menu.png)

| 操作 | 說明 |
|------|------|
| 檢出標籤 | 切換到標籤對應提交 |
| 刪除標籤 | 移除本機或遠端標籤 |
| 複製標籤名 / 複製標籤 SHA | 快捷複製 |
| 檢視標籤詳情 | 檢視關聯提交與說明 |

側欄 **標籤列表** 支援搜尋與篩選；可從提交歷史右鍵**從提交建立標籤**。

---

### 九、貯藏（Stash）管理

![貯藏右鍵選單](docs/images/stash-context-menu.png)

| 操作 | 說明 |
|------|------|
| 應用貯藏 | 應用變更，保留貯藏記錄 |
| 應用並刪除貯藏 | 等同 `git stash pop` |
| 刪除貯藏 | 捨棄該条貯藏 |
| 複製貯藏名稱 | 快捷複製 |

支援**重新命名**貯藏以便識別。

#### 貯藏對話框

工具栏 **Stash** 或相關選單可貯藏變更；檔案右鍵 **將選中檔案加入貯藏** 可只貯藏部分檔案。貯藏時完整保留暫存区與工作區的區分狀態。

##### 貯藏全部檔案

![貯藏全部檔案](docs/images/stash-all-dialog.png)

| 元素 | 說明 |
|------|------|
| 标题 | `Stash All Files` |
| 說明輸入 | 可選貯藏說明（`Please input stash message (Option)`） |
| **Stash All Files** | 將目前所有未提交變更一並貯藏 |
| **Hide** | 關閉對話框 |

##### 貯藏部分檔案

![貯藏部分檔案](docs/images/stash-files-dialog.png)

| 元素 | 說明 |
|------|------|
| 标题 | 顯示待貯藏檔案數，如 `Stash 1 files` |
| 說明輸入 | 可選貯藏說明 |
| **Select All (N/M)** | 全選 / 取消全選；`N` 為已选數，`M` 為可選檔案总數 |
| 檔案列表 | 勾選要貯藏的檔案（含已暫存與未暫存） |
| **Stash N files** | 僅貯藏勾選的檔案 |
| **Hide** | 關閉對話框 |

從檔案右鍵進入時，預設勾選目前選中檔案；也可在列表中增刪其他檔案。

---

### 十、複製與倉庫接入

![複製倉庫](docs/images/clone-repository.png)

| 欄位 | 說明 |
|------|------|
| 倉庫 URL（必填） | HTTPS / SSH |
| 本機目錄（必填） | 複製目標父目錄 |
| 目標檔案夹 | 預設可從 URL 推導 |
| 倉庫別名 | 僅用於應用程式內顯示 |
| 遞迴複製子模組 | 一並複製 Submodule |

- **新增本機倉庫**：開啟本機已有 Git 專案
- **Git**：Windows / macOS 使用應用**內建 Git**（dugite-native）；Linux 使用系統已安裝的 Git
- 複製失敗時提供權限與網絡相關的詳細錯誤提示

---

### 十一、按行審閱（Blame）與檔案歷史

![按行審閱](docs/images/blame-view.png)

**按行審閱（Blame）** 獨立視窗：

- 左侧：影響該檔案的所有提交列表，支援關鍵字篩選
- 中间：每行顯示最後修改者與日期
- 右側：帶語法高亮的檔案內容
- 頂部分支選擇器可切換分支

**檔案歷史記錄**：從檔案右鍵進入，檢視單檔案完整提交鏈及每次 diff。

---

### 十二、衝突解決

**合併、變基、拉取、貯藏應用、揀選**等任意產生衝突的操作，均提供同一套視覺化解決能力，無需區分場景。

![衝突解決介面](docs/images/rebase-conflict-resolution.png)

| 能力 | 說明 |
|------|------|
| 衝突檔案標示 | 側欄與檔案列表以警告圖示標出待解決檔案 |
| 分塊解決 | 編輯器內高亮衝突块，支援**接受目前 / 接受傳入 / 接受雙方** |
| 批次接受 | 一鍵 **Accept all current / Accept all incoming** |
| 衝突導覽 | 顯示 `1/N conflicts`，支援 Jump 跳轉到下一處 |
| 流程控制 | 進行中的操作（如變基）可**跳過目前步驟**或**中止**整個流程 |
| 提交区聯動 | 未解決完衝突時，提交按鈕提示「請先解決衝突」 |

![並排衝突對比](docs/images/conflict-side-by-side.png)

- 左右並排對比「目前版本」與「傳入版本」
- 類 VS Code 的衝突標記與行內操作按鈕

---

### 十三、其他能力

| 類别 | 能力 |
|------|------|
| Cherry-pick | 單个或批次揀選提交 |
| Squash | 多選提交壓縮為一個 |
| 重設 | 軟重設、硬重設、撤銷提交 |
| 性能 | 提交列表、diff、檔案樹採用虛擬列表，適合大型倉庫 |
| 內建 Git | Windows / macOS 基於 dugite-native 內建，開箱即用；Linux 依賴系統環境中的 Git |

---

## 截圖索引

所有介面截圖存放在 [`docs/images/`](docs/images/) 目錄：

| 檔案名 | 說明 |
|--------|------|
| `main-interface-dark.png` | 主介面（深色） |
| `main-interface-light.png` | 主介面（淺色） |
| `staged-files-with-diff.png` | 暫存区與 diff |
| `changed-files-list-view.png` | 變更檔案列表檢視 |
| `changed-files-tree-view.png` | 變更檔案樹檢視 |
| `unstaged-file-context-menu.png` | 未暫存檔案右鍵 |
| `diff-side-by-side.png` | 雙欄 diff |
| `diff-side-by-side-options.png` | 雙欄 diff（完整） |
| `diff-expand-up.png` | 向上展開上下文 |
| `diff-expand-down.png` | 向下展開上下文 |
| `diff-line-staging-hunk.png` | 行級暫存（選中行右鍵選單） |
| `commit-history-overview.png` | 提交歷史總覽 |
| `commit-context-menu.png` | 提交右鍵選單 |
| `commit-multi-select.png` | 多選提交操作 |
| `cherry-pick-dialog.png` | 揀選提交對話框 |
| `commit-detail-view.png` | 提交詳情 |
| `commit-file-tree.png` | 提交檔案樹 |
| `history-file-context-menu.png` | 歷史檔案右鍵選單 |
| `blame-view.png` | 按行審閱 |
| `branch-context-menu-en.png` | 分支右鍵選單 |
| `create-branch-dialog.png` | 建立分支對話框 |
| `push-dialog.png` | 推送對話框 |
| `remote-context-menu-en.png` | 遠端右鍵選單 |
| `add-remote-dialog.png` | 新增遠端對話框 |
| `remote-branch-context-menu.png` | 遠端分支選單 |
| `tag-context-menu.png` | 標籤選單 |
| `stash-context-menu.png` | 貯藏選單 |
| `stash-all-dialog.png` | 貯藏全部檔案 |
| `stash-files-dialog.png` | 貯藏部分檔案 |
| `clone-repository.png` | 複製倉庫 |
| `rebase-conflict-resolution.png` | 衝突解決介面 |
| `conflict-side-by-side.png` | 並排衝突對比 |
| `menu-app.png` | 應用程式選單 |
| `menu-file.png` | 檔案選單 |
| `menu-view.png` | 檢視選單（含主題切換） |
| `menu-repository.png` | 倉庫選單 |
| `menu-language.png` | 語言選單 |
| `menu-help.png` | 說明選單 |
| `settings-external-programs.png` | 外部開啟程式 |
| `settings-ssh-keys.png` | SSH 金鑰管理 |
| `settings-ai-commit.png` | AI 提交設定 |
| `settings-add-ai-model.png` | 新增 AI 模型 |

更多官方介面見 [官網](https://enjoygit.com)。

---

## 常見問題

關於 Enjoy Git 的一些常見疑問解答。

### Enjoy Git 與其他 Git 客戶端相比有什麼優勢？

Enjoy Git 專注於提供更直觀的用戶介面與更全面的功能支援，特別在**衝突解決**、**部分提交**和**檔案歷史追蹤**方面有獨特優勢。將複雜的 Git 指令封裝成簡單的視覺化操作，同時保留了進階功能的可存取性，讓無論是新手還是資深開發者都能高效使用。

### Enjoy Git 是否監察您的資料？

Enjoy Git **不會監察**您的倉庫內容。您在 Enjoy Git 上管理的所有專案歸您所有，Git 操作、憑證與日誌主要儲存在您的電腦上，不會上傳用於讀取您的提交或倉庫檔案。關於每日活躍裝置等基礎使用統計，請參閱[私隱政策](https://enjoygit.com/privacyPolicy.html)。

### 如何取得說明或報告問題？

- 提交 [GitHub Issue](https://github.com/huangcs427/enjoy-git-release/issues)
- 電郵聯絡：[huangcs427@163.com](mailto:huangcs427@163.com)

---

## 下載與安裝

- 前往 [GitHub Release](https://github.com/huangcs427/enjoy-git-release/releases) 下載對應平台與架構的安裝包

按安裝精靈完成安裝即可。

---

## 使用說明

- 遇到問題？提交 [GitHub Issue](https://github.com/huangcs427/enjoy-git-release/issues)

---

## dugite-native 调用源程式碼

```ts
/**
 * 本軟件內建的Git使用了dugite-native
 * 專案位址：https://github.com/desktop/dugite-native
 * 本檔案包含了取得git路徑和環境变量的函數，以及匯出git指令函數的程式碼。
 */
import { spawn } from 'child_process';
import * as fs from 'fs-extra';
import * as path from 'path';

// 取得windows的git实例子目錄，根據架構回傳不同的目錄
const getWin32GitSubfolder = (arch?: string): string => {
  const archRes = arch || process.arch
  if (archRes === 'x64') {
    return 'mingw64'
  } else if (archRes === 'arm64') {
    return 'clangarm64'
  } else {
    return 'mingw32'
  }
}

// 取得git路徑和環境变量
interface TObjectValue {
  [key: string]: any
}
const getGitPathAndGitEnv = (envTemp?: TObjectValue) => {
  let env = { ...process.env, ...(envTemp || {}) }
  // 此處假設gitFolder為目前檔案夹下的git檔案夹
  const gitFolder = path.join(__dirname, 'git')
  let gitPath = ''
  // Windows 下，git路徑為gitFolder\cmd\git.exe
  if (process.platform === 'win32') {
    const win32GitSubfolder = getWin32GitSubfolder()
    gitPath = path.join(gitFolder, 'cmd', 'git.exe')
    env.GIT_EXEC_PATH = path.join(gitFolder, win32GitSubfolder, 'libexec', 'git-core')
    env.PATH = `${gitFolder}\\${win32GitSubfolder}\\bin;${gitFolder}\\usr\\bin;${env.PATH ?? ''}`
  } else {
    // 其他平台下，git路徑為gitFolder\bin\git
    gitPath = path.join(gitFolder, 'bin', 'git')
    env.GIT_CONFIG_SYSTEM = path.join(gitFolder, 'etc', 'gitconfig')
    env.GIT_EXEC_PATH = path.join(gitFolder, 'libexec', 'git-core')
    env.GIT_TEMPLATE_DIR = path.join(gitFolder, 'share', 'git-core', 'templates')
  }
  // 如果git路徑不存在，使用系統git
  if (!fs.existsSync(gitPath)) {
    env = { ...envTemp }
    gitPath = 'git'
  }
  return { env, gitPath }
}

// 匯出git指令函數
export const git = (args: string[], options: TObjectValue) => {
  if (!options) options = {}
  const { gitPath, env } = getGitPathAndGitEnv(options.env)
  options.env = env
  return spawn(gitPath, args, options)
}
```

---

## 意見與建议

歡迎透過以下方式提出寶貴意見：

- 提交 [GitHub Issue](https://github.com/huangcs427/enjoy-git-release/issues)
- 電郵聯絡：huangcs427@163.com
- [私隱政策](https://enjoygit.com/privacyPolicy.html)
