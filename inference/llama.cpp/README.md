# llama.cpp

原始项目地址：https://github.com/ggerganov/llama.cpp

>llama.cpp 的主要目标是在各种硬件（本地和云中）上以最少的设置和最先进的性能启用 LLM 推理。
>
>- 没有任何依赖关系的普通 C/C++ 实现。
>- Apple 芯片也被支持-通过ARM NEON、Accelerate和Metal框架进行优化。
>- AVX、AVX2 和 AVX512 支持 x86 架构。
>- 1.5 位、2 位、3 位、4 位、5 位、6 位和 8 位整数量化，用于更快的推理和减少内存使用。
>- 用于在 NVIDIA GPU 上运行 LLM 的自定义 CUDA 内核（通过 HIP 支持 AMD GPU ）。
>- Vulkan、SYCL 和（部分）OpenCL 后端支持。
>- CPU+GPU 混合推理，可部分加速大于总 VRAM 容量的模型。
>
>支持的平台：
>
>- [X] Mac OS
>- [X] Linux
>- [X] Windows (via CMake)
>- [X] Docker
>- [X] FreeBSD

## [HTTP server](./server/)

[llama.cpp web server](https://github.com/ggerganov/llama.cpp/blob/master/examples/server) 是一个轻量级的 [OpenAI API](https://github.com/openai/openai-openapi) 兼容 HTTP 服务器，可用于服务本地模型并轻松将它们连接到现有客户端。