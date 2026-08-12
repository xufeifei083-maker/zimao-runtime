# Runtime 发布检查表

- [ ] 固定 Python 3.12 补丁版本
- [ ] 固定 ComfyUI 完整 commit
- [ ] 固定 PyTorch、CUDA Runtime 与 FFmpeg 版本
- [ ] 锁定所有 Python wheel 和基础节点版本
- [ ] 在全新 Windows 环境完成安装测试
- [ ] 使用 NVIDIA 8 GB 显存、16 GB 内存机器完成最低配置测试
- [ ] 验证 ComfyUI 可以启动并加载内置 H3 工作流
- [ ] 生成分卷并记录每个文件大小和 SHA256
- [ ] 使用生产 Ed25519 私钥签名原始 manifest 字节
- [ ] 复核私钥和测试输入未进入 Release
- [ ] 创建不可变版本号的公开 GitHub Release
- [ ] 从 Release 下载并完成一次端到端回归
