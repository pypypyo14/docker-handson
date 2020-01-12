# docker-handson!
https://tatsunoko.connpass.com/event/159292/
2020/01/31

---
## はじめまして

加藤 早織(@pypypyo14)です。  
1月からAWS関連の技術支援する会社にいます。  
前職でDockerとAWS Fargateを使ったシステムの構築などを少しやってました。  
  
たくさんの女性エンジニアに会えて嬉しいです。  
今日はよろしくお願いします！

---

## 得られること

- Dockerの概要理解
- Docker基本操作コマンドの理解

---

### 内容について

公式DocのGet Startedをかいつまんで説明する内容になっています
https://docs.docker.com/


---

## 目次

📖: 座学  💻:手を動かす

- 📖 Docker概要
- 💻 Hello World
- 💻 Docker ContainerとDocker Image
- 💻 Dockerfile
- 📖 まとめ
- 💻 いろいろなDockerfile

---

## Docker概要

---

## What is Docker?

- 「コンテナ」と呼ばれる仮想環境上のアプリケーションを
  「<font color ="red">開発</font>」「<font color ="red">共有</font>」「<font color ="red">実行</font>」するためのプラットフォーム
  - アプリケーションだけでなく、インフラも含めたコード化(Dockerfile)|
  - 環境(Docker Image)をまるっと、かんたんに配布|
    - 複数の開発者が同一設定のインフラ環境で開発 |
    - 環境間で意図しない環境差分を作らない |
  - 軽量で素早い実行 |

---

## コンテナ型仮想環境?

コンピュータリソースを  
すばやく、効率的に活用するための仕組み

---

## コンテナ型仮想環境?
- (物理、ハイパーバイザとの違いを図示）
- HWもOSも含まないため以下のメリットがある
   - 起動/スケールが早い |
   - 同じハードでもアプリに割けるリソースが多い |

---

## Docker概要まとめ

- コンテナ環境上のアプリケーションを
  「<font color ="red">開発</font>」「<font color ="red">共有</font>」「<font color ="red">実行</font>」するためのプラットフォーム
  - コンテナとは、コンピュータリソースをすばやく効率的に活用する仕組み

---

## Hello World

---

## Hello World

HelloWorld用のコンテナを  
インターネットで「<font color ="red">共有</font>」&  「<font color ="red">実行</font>」しましょう！

---

## Hello World

```
$ docker run hello-world
```
---

## Hello World

```
$  docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
1b930d010525: Pull complete 
Digest: sha256:d1668a9a1f5b42ed3f46b70b9cb7c88fd8bdc8a2d73509bb0041cf436018fbf5
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```
@[2-6](コンテナイメージをダウンロード)
@[7-27](アプリケーションの実行(標準出力))

---

## 参考リンク
-  Docker Docs
  - https://docs.docker.com/