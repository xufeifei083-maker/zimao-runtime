# Runtime 发布检查表

- [x] 固定 Python 3.12 补丁版本
- [x] 固定 ComfyUI 完整 commit
- [x] 固定 PyTorch、CUDA Runtime 与 FFmpeg 版本
- [x] 锁定 Runtime 文件和工作流所需自定义节点内容哈希
- [ ] 在全新 Windows 环境完成安装测试
- [ ] 使用 NVIDIA 8 GB 显存、16 GB 内存机器完成最低配置测试
- [x] 验证 ComfyUI 可以启动且内置 H3 工作流所需节点全部可用
- [x] 生成分卷并记录每个文件大小和 SHA256
- [x] 使用生产 Ed25519 私钥签名原始 manifest 字节
- [x] 复核私钥和测试输入未进入 Release
- [x] 使用临时空数据目录完成下载、校验、合并、解压和原子切换
- [x] 创建不可变版本号的公开 GitHub Release
- [x] 从 Release 下载并完成一次端到端回归
