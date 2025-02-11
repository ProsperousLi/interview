- DOCKER 是什么？

  - 答： dokcker 在linux的操作系统/虚拟机上，使用namespace、cgroup、chroot等技术形成一个个集装箱式的容器，使程序在一个个容器中进行隔离性的运行，互不干扰。

- 如何使用DOCKER 技术创建与环境无关的容器系统？
  
  - 答： docker pull centos:latest; 比如我现在是ubutun系统，使用buildx 可以创建不同的系统架构、不同操作系统的镜像。 
  
- DOCKERFILE 配置文件中的COPY 和ADD 指令有什么不同

  - 答：COPY和ADD都可以将宿主机文件拷贝到镜像里面，COPY支持多阶段构建，即可以将上一阶段的文件或者运行的结果copy到当前阶段。
  - ADD 不支持多阶段构建，但支持curl和直接解压包到镜像
  - 使用实践：使用COPY，解压可以在dockerfile之前的shell脚本做，curl可以在build或者run的时候做。
  
- DOCKER 映像（IMAGE）是什么
  - 镜像由多个文件层组成，是保存某个时间容器的状态，可以被import导出成tar包，可以打tag，上传到私仓或者dockerhub。

- DOCKER 容器（CONTAINER）是什么
  - 容器是镜像通过docker run运行的一个实例，是一个隔离的“操作系统”，可以通过save，load对容器进行容器打tar包和容器解压tar包

- DOCKER 中心（HUB）什么概念
  - 类似github，GitHub是代码的集中中心；HUB是镜像的提交中心。
- 在任意给定时间点指出一个DOCKER 容器可能存在的运行阶段
  - docker 创建 created
  - run
  - 暂停
  - delete
  - stop
- 有什么方法确定一个DOCKER 容器运行状态
  - docker ps -a |grep xxx
- 在DOCKERFILE 配置文件中最常用的指令有哪些
  - FROM、ENV、COPY、COMMAND、RUN、EXPOSE 
- 什么类型的应用（无状态性或有状态性）更适合DOCKER 容器技术
  - 无状态应用更适合，docker启动，删除实例，不影响系统的功能，且可以拓展成多个实例，实现扩容。
- 解释基本DOCKER 应用流程
  - 略 
- DOCKER IMAGE 和DOCKER LAYER (层) 有什么不同
  - image是layer的集合
- 虚拟化技术是什么
  - 在一台物理机上可以运行多个虚拟计算机，资源上限为物理机的上限。
- 什么是孤儿卷及如何删除它
  - 未与任何容器关联的卷。
- docker为什么是轻量级别的
  - 因为docker是在操作系统，通过linux计算隔离的资源，没有虚拟机一样厚重再套os，占用资源和体积都会比较小。且
  - 可以在虚拟机上运行docker。
- docker run -v
  - 挂载宿主机的卷，共享宿主机的目录。
- docker rm
  - rm 删除容器， rmi删除镜像； rm -f 强制删除容器
- 虚拟机和普通容器的不同点？网络实现都有什么原理？
  - 虚拟机是将虚拟的硬件、内核打包到虚拟环境，可以作为一个虚拟的环境，构建一个完全独立的操作系统
  - 容器是直接运行在操作系统上面的，公共一台物理机的内核、硬件和操作系统。
  - 都是通过物理机的网桥来进行网络通信的。
