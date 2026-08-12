# win-nvidia-h3-2026.08.1 验收记录

验收日期：2026-08-12

## 固定版本

- Python：3.12.12
- ComfyUI：`14b05228cef127ce529bc0c08660770d4af3e9a8`
- PyTorch：2.12.1+cu130
- CUDA Runtime：13.0
- FFmpeg：2025-06-26-git-09cd38e9d5

## 构建验证

- Runtime 文件：84,700 个
- 未压缩大小：7,287,000,293 字节
- 分卷总大小：3,849,560,045 字节
- 整体 SHA256：`c1f3bc4d0a72c46341db6c50cbc01f47771940fdeea7fa6b8c0071b54e9e75e3`
- 分卷 SHA256 与 `checksums.sha256` 一致
- Ed25519 manifest 签名验证通过
- Zip 完整性测试通过（84,700 个文件）

## 本地端到端安装验证

使用临时空数据目录和本地 HTTP 下载源运行正式安装器，实际完成：

1. 下载两个分卷至 100%；
2. 逐分卷 SHA256 校验；
3. 合并并校验完整压缩包 SHA256；
4. 安全解压和必需文件检查；
5. 原子切换当前 Runtime；
6. 从安装目录启动 `walkingwithai/python.exe --version`。

结果：`FULL_RUNTIME_INSTALL_OK`，内置 Python 输出 `Python 3.12.12`。

## 尚未完成

- 上传 GitHub Release 公开资产；
- 从公开 Release URL 重新执行端到端安装；
- 在最低配置（NVIDIA 8 GB 显存、16 GB 内存）的全新 Windows 环境启动 ComfyUI 并运行 H3 工作流。
