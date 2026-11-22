# 同步上游代码指南

## 首次设置

添加上游 remote（只需执行一次）：

```bash
git remote add upstream https://github.com/dstrml/wu.git
```

验证 remote 配置：

```bash
git remote -v
```

应该看到：
- `origin` → 你的 fork（`TalentSmallPanda/mu`）
- `upstream` → 原项目（`dstrml/wu`）

---

## 同步上游代码

### 步骤 1：获取上游最新代码

```bash
git fetch upstream
```

### 步骤 2：切换到 main 分支

```bash
git checkout main
```

### 步骤 3：合并上游代码

```bash
git merge upstream/main
```

如果有冲突：
1. 解决冲突文件
2. `git add <冲突文件>`
3. `git merge --continue`

### 步骤 4：推送到你的 fork

```bash
git push origin main
```

---

## 常用命令

### 查看上游和本地的差异

```bash
git diff upstream/main..HEAD
```

### 查看上游的提交历史

```bash
git log upstream/main --oneline -10
```

### 强制同步（丢弃本地改动，慎用！）

```bash
git fetch upstream
git checkout main
git reset --hard upstream/main
git push origin main --force
```

---

## 注意事项

1. **同步前先提交本地改动**，避免丢失
2. **如果有冲突**，优先保留上游的改动，你的本地改动记录在 `.github/release/LOCAL_CHANGES.md`
3. **同步后更新 `LOCAL_CHANGES.md`**，记录你的本地改动和上游版本的对应关系
