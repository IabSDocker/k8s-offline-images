# 🐳 Kubernetes Images Exporter

> 只是为了在离线部署时不用在`漫天遍野`找镜像 😭
本仓库使用 GitHub Actions 自动拉取并发布指定版本 Kubernetes 所需的容器镜像（ARM64 AMD64架构），支持通过 GitHub Release 下载离线镜像包。

## 🚀 功能简介

当你推送一个带有 `v*` 前缀的 Git 标签（如 `v1.23.17`、`v1.28.2`）时，该工作流程将自动：

1. 安装对应版本的 `kubeadm`
2. 拉取该版本 Kubernetes 所需的镜像
3. 将镜像保存为 tar 包
4. 上传压缩包至当前 tag 对应的 GitHub Release

镜像以 `k8s-<版本号>-arm64.tar.gz` 命名。

---

## 📦 支持内容

- 自动检测 tag 并提取版本（如：`v1.23.17`）
- 安装并使用 Aliyun 源快速安装 `kubeadm`
- 使用 `containerd` 拉取镜像并打包
- 支持 ARM64 AMD64平台

---