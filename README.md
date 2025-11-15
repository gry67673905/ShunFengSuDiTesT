
# 2025 全国大学生软件测试大赛 Web 应用测试省赛（顺丰场景）示例仓库

本仓库包含 3 类提交内容中的 **测试脚本代码** 与 **GitHub Actions 自动化运行配置**，方便在 GitHub 上一键运行 Selenium + Pytest，用于生成题目要求的测试截图压缩包。

> **注意：**
> - 题目平台最终评测时，仍需保证 `test_SF.py` 中 WebDriver 的本地路径为题目要求的  
>   `C:\Users\86153\AppData\Local\Google\Chrome\Application\chromedriver.exe`。
> - 本示例在检测到环境变量 `GITHUB_ACTIONS=true` 时，会自动改用 `webdriver-manager` 下载驱动并以无头模式运行，用于 GitHub Actions 环境。

## 目录结构

- `test_SF.py`：Selenium + Pytest 自动化脚本（10 个测试用例，对应 R001~R010）。
- `requirements.txt`：Python 依赖。
- `.github/workflows/run-sf-tests.yml`：GitHub Actions 工作流，负责安装 Chrome、依赖并执行测试。
- `SF_测试用例.xlsx`：根据需求文档设计的功能测试用例（文件一示例）。

## 在 GitHub 上运行测试的步骤

1. 在 GitHub 新建一个空仓库。
2. 将本压缩包解压后全部文件上传到仓库根目录（注意 `.github/workflows` 目录不要丢）。
3. 在仓库页面选择 **Actions → Run workflow** 触发 `Run SF Selenium Tests`。
4. 运行结束后，在 **Actions → 该次运行详情 → Artifacts** 中下载 `sf-screenshots` 压缩包，
   即为题目要求的 **测试截图压缩包**（文件三的基础素材）。

