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

## 今日やること

- Dockerの概要理解
- Docker基本操作コマンドの理解
- Dockerfile基本文法

---

## 目次

📖: 座学  💻:手を動かす

- 📖 Docker概要
- 💻 Hello World
- 💻 Docker ContainerとDocker Image
- 💻 Dockerfile
- 📖 まとめ
- 💻 ハンズオン!

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
  - コンテナとは、コンピュータリソースをすばやく効率的に活用する仕組み|

---

## 💻Hello World💻

---

## Hello World

HelloWorldのコンテナを  
インターネットで「<font color ="red">共有</font>」&  「<font color ="red">実行</font>」してみましょう！

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

(略)
```
@[2-6](コンテナイメージをダウンロード)
@[7-11](アプリケーションの実行(標準出力))

---

## 何が起こった?
- (図解)

---

## Docker image と Docker container

- コンテナは都度作成され、アプリケーションを動かし、停止する。
- imageはコンテナの元となるもの。

```
$ docker container ls -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                      PORTS               NAMES
dba1b03834f1        hello-world         "/hello"            9 seconds ago       Exited (0) 7 seconds ago                        festive_black
```

@[3](実行後、コンテナは停止している(Exited(0)))

---
## Docker image と Docker container

```
$ docker container ls -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                      PORTS               NAMES
dba1b03834f1        hello-world         "/hello"            9 seconds ago       Exited (0) 7 seconds ago                        festive_black
2a0530875f56        hello-world         "/hello"            12 seconds ago      Exited (0) 10 seconds ago                       festive_satoshi
```
@[4](もう一度 docker run すると、新しいコンテナが作成される)

---

Dockerイメージを確認するコマンドを叩いてみると  
hello-worldというIMAGEがある

```
$ docker image ls
REPOSITORY                            TAG                 IMAGE ID            CREATED             SIZE
hello-world                           latest              fce289e99eb9        12 months ago       1.84kB
```

DL、あるいはビルドしたイメージは  
`$ docker image ls`コマンドで確認可能！

---
## Docker imageをビルドする

以降Dockerfileの説明。まだできておらず…
メモ https://gist.github.com/pypypyo14/7c53334b73d5ca36382cc5a34f5679d5


---
## 参考リンク
-  Docker Docs
  - https://docs.docker.com/