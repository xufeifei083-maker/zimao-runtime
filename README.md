# 紫猫固定 Runtime

本仓库用于公开发布紫猫固定版本的 ComfyUI、Python、PyTorch、CUDA Runtime 和 FFmpeg 运行环境清单。

当前已完成本地构建与安装验收、等待上传公开 Release：

```text
win-nvidia-h3-2026.08.2
```

`.2` 从官方上游全新构建，不复制任何第三方整合包文件。旧 `.1` 已撤回，原因见 [`WITHDRAWN.md`](releases/win-nvidia-h3-2026.08.1/WITHDRAWN.md)。

`.2` 的签名元数据和验收记录见 [`releases/win-nvidia-h3-2026.08.2`](releases/win-nvidia-h3-2026.08.2)。在两个分卷上传并完成公开 URL 回归前，不应配置为软件下载源。

## 发布门槛

- 每个源码和二进制依赖都记录官方来源、固定版本或 commit 和 SHA256；
- 禁止旧整合包品牌、推广链接、自定义页面、启动脚本和本机路径进入产物；
- 保留 ComfyUI 和第三方节点要求的 LICENSE/NOTICE；
- 完成签名、分卷校验、全新目录安装和工作流启动测试后才创建公开 Release；
- 模型不进入 Runtime，由软件从 Hugging Face 固定 commit 下载。

Runtime 清单必须符合 [`runtime-manifest.schema.json`](runtime-manifest.schema.json)，发布步骤见 [`RELEASE-CHECKLIST.md`](RELEASE-CHECKLIST.md)，当前构建来源见 [`runtime-profile.json`](runtime-profile.json)。Ed25519 公钥见 [`public-key.txt`](public-key.txt)，私钥不得提交。
