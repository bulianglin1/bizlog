1. 视频合并功能依赖于 ffmpeg, 因此镜像必须包含 ffmpeg 工具
```dockerfile
RUN apt-get update && \
    apt-get install -y ffmpeg && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
```
命令解释:
1. apt-get update：更新包管理器的缓存，确保可以从最新的软件源中安装软件包。
2. apt-get install -y ffmpeg：安装 ffmpeg 软件包，并通过 -y 参数自动确认安装过程。
3. apt-get clean：清理 APT 缓存，移除安装过程中下载的包文件，减少 Docker 镜像的体积。
4. rm -rf /var/lib/apt/lists/*：删除 APT 的包列表缓存，进一步减小镜像体积。
