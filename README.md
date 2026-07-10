# GitCG - GitHub Contribution Wall

自动刷 GitHub 贡献墙的脚本，每天随机提交 3-7 次，让贡献图保持绿色。

## 快速开始

```bash
# 一键配置
bash setup.sh

# 手动运行一次
bash contribute.sh
```

## 工作原理

- systemd timer 每天 08:00-22:00 间随机触发
- 脚本每次运行随机产生 3-7 次提交
- 每次提交间隔 1-10 分钟随机延迟
- 提交内容为随机哈希值，确保分布自然

## 常用命令

```bash
# 查看定时器状态
systemctl --user status github-contribute.timer

# 查看日志
cat .contribute.log

# 停用
systemctl --user disable --now github-contribute.timer
```

## 依赖

- [GitHub CLI (gh)](https://cli.github.com/) 已登录
- systemd (Linux)
