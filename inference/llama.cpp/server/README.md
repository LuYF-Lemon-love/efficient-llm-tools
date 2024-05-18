# LLaMA.cpp HTTP Server

基于 [httplib](https://github.com/yhirose/cpp-httplib)、[nlohmann::json](https://github.com/nlohmann/json) 和 llama.cpp 的快速、轻量级、纯 C/C++HTTP 服务器。

一组 LLM REST API 和一个与 llama.cpp 交互的简单 Web 前端。

## 特点

- GPU 和 CPU 上 F16 和量化模型的 LLM 推理。
- OpenAI API 兼容的聊天完成和嵌入路由。
- 支持多用户的并行解码。
- 连续 batching。
- 多模态。
- 监控端点。
- 模式约束的 JSON 响应格式。

## 命令行选项

- `-v`，`--verose`：启用详细的服务器输出。使用 `/completion` 端点时，这包括标记化提示词、完整请求和完整响应。
- `-t N`，`--threads N`：设置 CPU 层在生成过程中使用的线程数。卸载到 GPU 的模型层不使用。使用最大 GPU 层数时，此选项无效。默认值：`std::thread::hardware_concurrency()`（CPU 内核数）。
- `-tb N`，`--threads-batch N`：设置 CPU 层在批处理和提示词处理期间使用的线程数（>=32 tokens）。如果 GPU 可用，此选项无效。默认值：`--threads`。
- `--threads-http N`：http服务器池中处理请求的线程数。默认值：`max(std::thread::hardware_concurrency() - 1, --parallel N + 2)`。