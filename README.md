# 紫猫固定 Runtime

本仓库用于公开发布紫猫固定版本的 ComfyUI、Python、PyTorch、CUDA Runtime 和 FFmpeg 运行环境清单。

首个 Runtime ID 预定为：

```text
win-nvidia-h3-2026.08.1
```

当前仓库只建立发布规范，尚未发布 Runtime 二进制。只有完成干净机器安装、8 GB 显存 / 16 GB 内存门槛测试、文件哈希和 Ed25519 签名后，才会创建正式 GitHub Release。

## 发布物

正式 Release 应包含：

- `runtime-manifest.json`
- `runtime-manifest.sig`
- `checksums.sha256`
- `runtime-<version>.partNN` 分卷

Runtime 清单必须符合 [`runtime-manifest.schema.json`](runtime-manifest.schema.json)，发布步骤见 [`RELEASE-CHECKLIST.md`](RELEASE-CHECKLIST.md)。

Runtime 版本盘点见 [`runtime-profile.json`](runtime-profile.json)，Ed25519 公钥见 [`public-key.txt`](public-key.txt)。签名私钥仅保存在发布机器，不得提交。

## 构建

先只读检查纳入范围和预计体积：

```powershell
python tools/build_runtime.py --source <COMFYUI_ROOT> --dry-run
```

正式构建器位于 `zimao-app/tools/build_runtime.py`。它会排除模型、用户输入输出和无关自定义节点，生成 Zip64 压缩包、约 1.9 GB 分卷、SHA256 清单和 Ed25519 签名 manifest。

本仓库不存放模型；工作流模型由软件从 Hugging Face 固定 commit 下载。
