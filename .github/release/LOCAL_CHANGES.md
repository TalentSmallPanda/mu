# 本地改动记录

本文件记录本项目（`TalentSmallPanda/mu`）相对于上游（`dstrml/wu`）的本地改动。

---

## 1.2.1 - 2026-11-09

### 功能改动

- **LSP 位置选择器支持双击确认**
  - 新增 `double_click_to_confirm` trait 方法
  - `handle_click` 增加 `click_count` 参数
  - 单击选中/预览，双击确认

- **Git diff 视图显示完整文件**
  - 改用 `MultiBuffer::singleton` 模式
  - 展开所有 diff hunks
  - 获得完整导航体验

- **更新应用图标**
  - 替换所有平台的图标文件（PNG/ICO/ICNS）

### 修改的文件

#### 代码文件

- `crates/picker/src/picker.rs`
  - 新增 `double_click_to_confirm()` trait 方法（默认返回 `false`）
  - `handle_click` 增加 `click_count` 参数
  - 支持双击确认逻辑

- `crates/lsp_locations/src/lsp_locations.rs`
  - 实现 `double_click_to_confirm() -> true`
  - LSP 位置选择器启用双击确认

- `crates/git_ui/src/solo_diff_view.rs`
  - 改用 `MultiBuffer::singleton` 模式
  - 调用 `set_all_diff_hunks_expanded` 展开所有 hunks

#### 图标文件

- `crates/wu/resources/app-icon.png`（242KB）
- `crates/wu/resources/app-icon@2x.png`（923KB）
- `crates/wu/resources/app-icon-dev.png`
- `crates/wu/resources/app-icon-dev@2x.png`
- `crates/wu/resources/windows/app-icon.ico`
- `crates/wu/resources/windows/app-icon-dev.ico`
- `crates/wu/resources/Document.icns`

---

## 同步上游后的操作

1. 每次同步上游代码后，检查是否有冲突
2. 如果有图标相关的改动，需要重新应用你的图标
3. 更新本文件，记录新的本地改动

---

## 版本对应关系

| 上游版本 | 本地版本 | 日期 |
|---------|---------|------|
| 1.2.0 | 1.2.1 | 2026-11-09 |
