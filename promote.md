---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: ./douglas-bagg-SHE_ZiroE0g-unsplash.jpg
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# use UnoCSS
css: unocss
---

# 基于WSL快速搭建轻量linux开发环境

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    按空格到下一页 <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---

# Why WSL?

我的三段工作经历

<div class="grid grid-cols-3 gap-2">
  <div>
    <h3>Tencent</h3>
    <p>
      2个月
      <span class="bg-green-500 rounded-md text-sm w-10 inline-block text-center">高效</span>
    </p>
    <ul class="text-base">
      <li>windows + <span class="text-green-500">linux云主机</span>(16G内存, X BG 云主机服务)</li>
      <li>windows只负责完成开发工作, 使用云主机可实现<span class="text-green-500">独立</span>调试/联调</li>
      <li>vscode remote ssh, 直接在linux开发</li>
      <li>命令行工具根据环境名快速补全查找, 跳转机器</li>
      <ul class="pl-14 text-sm">
        <li><span class="text-green-500">No</span> xx环境信息.xlsx</li>
        <li><span class="text-green-500">No</span> 146.12.3.1</li>
        <li><span class="text-green-500">No</span> Password</li>
        <li><span class="text-green-500">No</span> VPN Client</li>
      </ul>
    </ul>
  </div>
  <div>
    <h3>Huawei/ICT/NCE</h3>
    <p>
      1.4年
      <span class="bg-red-500 rounded-md text-sm w-10 inline-block text-center">低效</span>
      <span class="bg-red-500 rounded-md text-sm w-16 inline-block text-center ml-1">加班主因</span>
    </p>
    <ul>
      <li>开发无单独环境</li>
      <li>断点互相冲突, <span class="text-red-500">单线程联调</span></li>
      <li>环境经常因测试占用/底座升级无法使用, 环境迁移成本高</li>
      <li>前端对接的环境<span class="text-red-500">不稳定</span></li>
    </ul>
  </div>
  <div>
    <h3>Huawei/ICT/K8S</h3>
    <p>
      1周
    </p>
    <ul>
      <li>k8s主仓未考虑windows开发者, vendor均为<span class="text-red-500">linux软链</span></li>
      <li>cfe-apiserver部分用例写死临时目录路径, 仅<span class="text-red-500">linux/git-bash能跑</span></li>
      <li>开发无个人集群用于验证, 复杂场景难以协调环境</li>
    </ul>
  </div>
</div>

---

# WSL + K8S = minikube

```bash
minikube dashboard
```

<Xterm></Xterm>
