# win-nvidia-h3-2026.08.2 验收记录

验收日期：2026-08-13

## 来源

- ComfyUI：官方仓库 commit `14b05228cef127ce529bc0c08660770d4af3e9a8`
- Python：python.org 官方 Windows 嵌入版 3.12.10
- PyTorch：官方 CUDA 13.0 索引，2.12.1+cu130
- KJNodes：官方仓库 commit `6ab7e8130e449ed2c0037589bcf84146ceb7fc9c`
- VideoHelperSuite：官方仓库 commit `4ee72c065db22c9d96c2427954dc69e7b908444b`
- FFmpeg：BtbN Windows LGPL 构建 `n8.1.2-34-g9b6c8969e0-20260812`

没有复制旧第三方整合包中的文件。

## 审计与功能验证

- `pip check`：通过
- 旧作者品牌、推广网址、自定义 Gradio 页面、旧目录名和本机路径审计：通过
- ComfyUI CPU 模式启动：通过
- ComfyUI GPU 模式启动：通过，识别 RTX 3090 / CUDA 13.0 / cuDNN 92000
- 网页标题：`ComfyUI`
- H3 四种模式所需节点：23/23 可用，缺失 0
- KJNodes 和 VideoHelperSuite：加载成功
- 可选 `PatchTritonVAE` 未安装；H3 工作流不依赖该节点

## 构建与安装验证

- 文件数：41,972
- 未压缩：4,568,229,518 字节
- 分卷总大小：2,772,916,220 字节
- 整体 SHA256：`98452e559a1884e0274367304b10894eae6a0d0614a10f6e1fe32709e541ab14`
- 逐分卷 SHA256、ZIP CRC 和 Ed25519 签名：通过
- 真实安装器下载、合并、校验、安全解压和原子切换：通过
- 安装后 Python 3.12.10 与 FFmpeg 8.1 启动：通过

## 公开 Release 回归

- 五个 GitHub Release 资产的服务端大小与 SHA256：通过
- 从公开 Release URL 下载 0–100%：通过
- 从空数据目录安装、校验、解压和原子切换：通过
- 从公开安装目录启动 Python、FFmpeg 和 GPU ComfyUI：通过
- H3 核心节点缺失：0

## 尚未完成

- 在最低配置（NVIDIA 8GB 显存、16GB 内存）的全新 Windows 机器运行完整 H3 推理。
