class: center, middle, inverse
## Windowsコンテナのしくみ

---
### whoami

.left-small[
    ![image](https://pbs.twimg.com/profile_images/994762110792953856/EheEvqBY_400x400.jpg)
]

.right-large[
.tmp[
- Kyohei Mizumoto(@kyohmizu)
]

.tmp[
- C# Software Engineer
]

.tmp[
- Interests
  - Cloud Native
  - Docker
  - Kubernetes
  - Golang
  - Azure
]
]

---
### はじめに

.zoom2[
- Windowsコンテナについて、調べた内容を共有します

.tmp[
- 基本的にMSドキュメントを参考  
  .zoom2[<u><https://docs.microsoft.com/en-us/virtualization/windowscontainers/></u>]
]

- 間違っている点があればご指摘ください
]

---
### 今日話すこと

.zoom2[
- Windowsコンテナ概要

- コンテナ本体のしくみ

- ネットワークのしくみ
]

---
class: header-margin
### Windows on Kubernetes

.half-3[
<center><img src="https://docs.microsoft.com/en-us/virtualization/windowscontainers/container-networking/media/windowsnetworkstack-simple.png" width=92%></center>
]

.zoom0-r[
<u>https://docs.microsoft.com/en-us/virtualization/windowscontainers/container-networking/architecture</u>
]

---
class: header-margin
### Windows on Kubernetes

.half-3[
<center><img src="https://docs.microsoft.com/en-us/virtualization/windowscontainers/container-networking/media/hns-management-stack.png" width=70%></center>
]

.zoom0-r[
<u>https://docs.microsoft.com/en-us/virtualization/windowscontainers/container-networking/architecture</u>
]

---

.half-4[
<center><img src="https://docs.microsoft.com/en-us/virtualization/windowscontainers/deploy-containers/media/docker-on-linux.png" width=89%></center>
]

.zoom0-r[
<u>https://docs.microsoft.com/en-us/virtualization/windowscontainers/deploy-containers/containerd</u>
]

---

.half-4[
<center><img src="https://docs.microsoft.com/en-us/virtualization/windowscontainers/deploy-containers/media/hcs.png" width=87%></center>
]

.zoom0-r[
<u>https://docs.microsoft.com/en-us/virtualization/windowscontainers/deploy-containers/containerd</u>
]

---
### 参考

.zoom1[
.zoom01[
Intro to Windows support in Kubernetes  
<u><https://kubernetes.io/docs/setup/production-environment/windows/intro-windows-in-kubernetes/></u>

Kubernetes on Windows  
<u><https://docs.microsoft.com/en-us/virtualization/windowscontainers/kubernetes/getting-started-kubernetes-windows></u>

Windows container networking  
<u><https://docs.microsoft.com/en-us/virtualization/windowscontainers/container-networking/architecture></u>

KubernetesとFlannelでWindows上にPod間VXLAN Overlayネットワークを構成  
<u><https://www.slideshare.net/anikundesu/kubernetesflannelwindowspodvxlan-overlay-152588125></u>

Kubernetes Networking: Behind the scenes  
<u><https://itnext.io/kubernetes-networking-behind-the-scenes-39a1ab1792bb></u>
]
]

---
class: center, middle, blue
## Thank you!
