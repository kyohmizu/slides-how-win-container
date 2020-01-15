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
### 今日話すこと

.zoom2[
.tmp[
- Windowsコンテナの主要インターフェイスについて
  - HCS
  - HNS
]
.tmp[
- 実行したコンテナを各種ツールで確認してみる
]
]

---
class: header-margin
### より詳しく知りたい方は…

<center><img src="qiita.png" width=100%></center>

---
### Windowsコンテナの特徴

.zoom1[
.tmp[
- 2つの分離モード
  - プロセス分離、Hyper-V分離
  - `--isolation` オプションで指定
]

.tmp[
- 4つのベースイメージ  
  .zoom1[<u><https://docs.microsoft.com/en-us/virtualization/windowscontainers/manage-containers/container-base-images></u>]
]

.tmp[
- コンテナはホストOSのバージョンに依存
  - プロセス分離の場合、同一バージョンのイメージのみ実行可能
]

.tmp[
- ドキュメントがない、足りない
  - プロプラつらい
]
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
### インターフェイス

.zoom1[
.tmp[
- HCS (Host Compute Service)
  - コンテナ管理のための低レベル機能をAPIとして提供
  - cgroups、namespace 等の役割
  - 実体は `vmcompute.dll`
  - Docker ではGo Wrapperの `hcsshim` を使用
]

.tmp[
- HNS (Host Networking Service)
  - 仮想スイッチやエンドポイント、ポリシーの作成等を行う
  - 5つのネットワークドライバをサポート  
    (nat, overlay, transparent, l2bridge, l2tunnel)
  - `hcsshim` に含まれる
  - 今は HCN (Host Compute Networking) と呼ばれる？
]
]

---
### コンテナランタイム

.zoom1[
<u><https://github.com/microsoft/hcsshim/tree/master/cmd/runhcs></u>

- runhsc
  - OCI準拠のコンテナランタイム
  - `runc` をforkしたもの
  - Windowsコンテナのプロセス分離とHyper-V分離、LCOWに対応
  - containerd (on Windows) + runhcs の構成

```cmd
runhcs run [ -b bundle ] <container-id>
```

- Docker では `hcsshim` で直接HCS、HNSを呼び出している
]

---
class: header-margin
### Linuxコンテナとの比較

.half-3[
<center><img src="diff.png" width=74%></center>
]

.zoom0-r[
<u>https://www.slideshare.net/Docker/windows-container-security</u>
]

---
### 実行環境

---
class: header-margin
### コンテナネットワーク

.half-3[
<center><img src="https://docs.microsoft.com/en-us/virtualization/windowscontainers/container-networking/media/windowsnetworkstack-simple.png" width=92%></center>
]

.zoom0-r[
<u>https://docs.microsoft.com/en-us/virtualization/windowscontainers/container-networking/architecture</u>
]

---
### 参考

.zoom1[
.zoom01[
Docker Desktop の復習と、Windows Container に入門: Windows Server Container 理論編  
<u><https://qiita.com/kikuchi_kentaro/items/2fb0171e18821d402761></u>

Introducing the Host Compute Service (HCS)  
<u><https://techcommunity.microsoft.com/t5/containers/introducing-the-host-compute-service-hcs/ba-p/382332></u>

Containers on Windows Documentation  
<u><https://docs.microsoft.com/en-us/virtualization/windowscontainers/></u>

Windows container security  
<u><https://www.slideshare.net/Docker/windows-container-security></u>

Deep dive into Windows Server Containers and Docker – Part 2  
<u><https://xebia.com/blog/deep-dive-into-windows-server-containers-and-docker-part-2-underlying-implementation-of-windows-server-containers/></u>
]
]

---
class: center, middle, blue
## Thank you!
