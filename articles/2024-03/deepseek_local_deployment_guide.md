# DeepSeek 本地部署教程

本文将介绍如何在本地快速部署 DeepSeek 模型。对于新手用户，我们推荐使用 Ollama 框架进行部署，这是一种轻量级且用户友好的解决方案。

## 一、基于 Ollama 的快速部署（新手推荐）

### 1. 安装 Ollama 框架

#### Windows 安装
- 访问 [Ollama 官网](https://ollama.com) 或国内镜像站（如 2265.com）下载安装包
- 双击 .exe 文件进行安装，默认安装至 C 盘
- 如需更改安装路径，可在命令行执行：
```bash
.\OllamaSetup.exe /DIR="D:\Ollama"
```

#### macOS 安装
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

#### Linux 安装
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

#### 验证安装
打开终端输入：
```bash
ollama list
```
如显示模型列表则表示安装成功。

### 2. 下载 DeepSeek 模型

#### 选择合适的模型版本
- DeepSeek-R1 8B 版本
  - 适合普通用户
  - 需求约 5GB 显存
  - 性能适中
  
- DeepSeek-R1 16B 版本
  - 需要高性能显卡（16GB 以上显存）
  - 性能更优
  - 适合专业用户

#### 下载安装模型
```bash
# 下载 8B 版本
ollama run deepseek-r1:8b

# 下载 16B 版本（如果硬件配置足够）
ollama run deepseek-r1:16b
```

### 3. 配置可视化界面（可选）

#### Open WebUI 方案
1. 安装 Python 3.11
2. 安装 Open WebUI：
```bash
pip install open-webui
```
3. 启动服务：
```bash
open-webui start
```
4. 访问 http://localhost:8080 使用图形界面

#### Chatbox AI 方案
1. 下载安装 [Chatbox](https://chatboxai.app)
2. 设置 API 类型为 Ollama
3. 配置本地连接
4. 开始对话交互

### 4. 浏览器插件集成

#### Page Assist 插件配置
1. 在 Edge/Chrome 应用商店安装 Page Assist 插件
2. 打开插件设置
3. 选择模型类型为 Ollama
4. 配置本地连接参数
5. 即可在浏览器中直接调用 DeepSeek

## 二、使用建议

### 1. 硬件配置建议
- CPU：建议 Intel i5/AMD Ryzen 5 及以上
- 内存：最低 8GB，建议 16GB
- 显卡：
  - 8B 版本：NVIDIA GTX 1660 6GB 及以上
  - 16B 版本：NVIDIA RTX 3080 16GB 及以上

### 2. 性能优化
- 使用 GPU 加速
- 适当调整上下文长度
- 根据实际需求选择模型大小
- 使用量化版本节省资源

### 3. 常见问题

#### 显存不足
- 尝试使用更小的模型版本
- 关闭其他占用显存的程序
- 使用量化版本

#### 模型下载慢
- 使用国内镜像源
- 检查网络连接
- 尝试断点续传

#### 启动失败
- 检查 Ollama 服务状态
- 验证显卡驱动
- 确认系统兼容性

## 总结

通过 Ollama 框架部署 DeepSeek 是一种简单高效的方案，特别适合个人用户和开发者快速开始。选择合适的模型版本，配合可视化界面和浏览器插件，可以轻松搭建本地 AI 助手。建议在部署前检查硬件配置，并根据实际需求选择适合的模型版本。 