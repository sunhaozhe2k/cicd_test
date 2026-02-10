# cicd_test

[![C Build CI](https://github.com/sunhaozhe2k/cicd_test/actions/workflows/c-build.yml/badge.svg)](https://github.com/sunhaozhe2k/cicd_test/actions/workflows/c-build.yml)

这是一个最小化的 GitHub CI/CD 示例仓库，用于编译并运行 `main.c`。

## 项目结构

- `main.c`：示例 C 程序入口。
- `Makefile`：本地与 CI 统一使用的构建脚本。
- `.github/workflows/c-build.yml`：GitHub Actions 工作流，自动构建并运行程序。

## 本地运行

```bash
make
./main
```

## GitHub Actions 行为

在以下事件触发时执行：

- push 到 `main` 或 `master`
- 向 `main` 或 `master` 发起 pull request

CI 会执行：

1. 拉取代码
2. 安装 C 编译工具链（`build-essential`）
3. 执行 `make` 编译 `main.c`
4. 运行编译产物 `./main`
