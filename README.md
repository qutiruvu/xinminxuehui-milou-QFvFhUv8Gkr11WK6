> [【从UnityURP开始探索游戏渲染】](https://github.com)**专栏-直达**

# **图形学光照模型发展史：技术演进与里程碑**

## section 基础奠基期(1960s-1970s)

* 1967 ： Lambert模型(漫反射) - Bui Tuong Phong提出
* 1971 ： Gouraud着色 - Henri Gouraud发明顶点插值着色
* 1973 ： Warnock算法 - 首次实现隐藏面消除
* 1975 ： Phong模型 - Bui Tuong Phong提出完整反射模型

## section 物理模型探索期(1980s)

* 1980 ： Whitted光线追踪 - Turner Whitted实现全局光照
* 1981 ： Cook-Torrance模型 - 首个微表面BRDF
* 1982 ： Blinn-Phong改进 - Jim Blinn优化Phong模型
* 1984 ： Radiosity方法 - Cornell大学提出热辐射算法
* 1986 ： Kajiya渲染方程 - 奠定现代渲染数学基础

## section 实时渲染突破期(1990s)

* 1991 ： Ward各向异性模型 - 解决拉丝金属效果
* 1993 ： Schlick近似 - 高效菲涅尔计算
* 1996 ： Oren-Nayar模型 - 粗糙表面漫反射
* 1997 ： HDR渲染 - Debevec首次实现高动态范围

## section 现代PBR时期(2000s-)

* 2003 ： Ashikhmin-Shirley模型 - 各向异性BRDF
* 2007 ： GGX分布 - Bruce Walter引入长尾高光
* 2010 ： Disney BRDF - Brent Burley统一艺术工作流
* 2014 ： UE4 PBR - Tim Sweeney推动游戏业标准化
* 2016 ： 路径追踪实时光追 - NVIDIA Turing架构

# **一、基础奠基期（1967-1979）**

## **1967：‌Lambert漫反射模型‌**

* ‌**提出者**‌：法国计算机科学家Bui Tuong Phong
* ‌**核心贡献**‌：$L = k\_d \* I \* max(0, N·L)$
* ‌**背景**‌：犹他大学早期CG研究，受限于SDS 9300主机（32KB内存）
* ‌**意义**‌：首个可计算的漫反射模型

## **1971：‌Gouraud着色‌**

* ‌**提出者**‌：法国科学家Henri Gouraud（犹他大学博士）
* ‌**原理**‌：顶点光照插值
* ‌**硬件支持**‌：GE CT扫描仪专用图形系统
* ‌**突破**‌：实现光滑表面效果，计算量降低95%

## **1975：‌Phong反射模型‌**

* ‌**提出者**‌：Bui Tuong Phong（完成博士论文后不久去世）
* ‌**核心公式**‌：$L = ambient + diffuse + k\_s \* (R·V)^n$
* ‌**实验环境**‌：在DEC PDP-10主机上实现，单帧渲染耗时数小时
* ‌**历史意义**‌：奠定现代光照模型三大组件基础

# **二、物理模型探索期（1980-1989）**

## **1980：‌Whitted光线追踪‌**

* ‌**提出者**‌：Turner Whitted（贝尔实验室）
* ‌**突破**‌：首次实现反射、折射全局效果
* ‌**硬件背景**‌：VAX-11/780主机，512x512图像需74分钟

## **1981：‌Cook-Torrance微表面模型‌**

* ‌**提出者**‌：Robert Cook（Lucasfilm）和Kenneth Torrance（康奈尔大学）
* ‌**核心突破**‌：分解BRDF为D/F/G三项
* ‌**应用**‌：电影《星际迷航2》特效制作

## **1984：‌Radiosity方法‌**

* ‌**研发机构**‌：康奈尔大学（Donald Greenberg团队）
* ‌**原理**‌：热辐射能量传递在CG的应用
* ‌**代表成果**‌：康奈尔盒子（至今仍是标准测试场景）

## **1986：‌Kajiya渲染方程‌**

* ‌**提出者**‌：Jim Kajiya（Caltech）
* ‌**数学表达**‌：$L\_o = L\_e + ∫f\_r L\_i cosθ dω$
* ‌**意义**‌：统一光照计算理论框架

# **三、实时渲染突破期（1990-1999）**

## **1991：‌Ward各向异性模型‌**

* ‌**提出者**‌：Greg Ward（LBNL）
* ‌**解决痛点**‌：金属拉丝、CD光盘等方向性反射

## **1993：‌Schlick菲涅尔近似‌**

* ‌**提出者**‌：Christophe Schlick（法国蒙彼利埃大学）
* ‌**公式**‌：$F = F\_0 + (1-F\_0)(1-cosθ)^5$
* ‌**价值**‌：计算效率提升20倍，沿用至今

## **1996：‌Oren-Nayar粗糙漫反射‌**

* ‌**提出者**‌：Michael Oren和Shree Nayar（哥伦比亚大学）
* ‌**背景**‌：NASA火星探测计划表面材质研究
* ‌**突破**‌：修正Lambert对粗糙表面的失真

# **四、现代PBR时期（2000至今）**

## **2007：‌GGX法线分布‌**

* ‌**提出者**‌：Bruce Walter（康奈尔大学）
* ‌**特性**‌：长尾高光分布，符合真实材质
* ‌**工业应用**‌：迪士尼动画《长发公主》(2010)

## **2010：‌Disney BRDF‌**

* ‌**领导者**‌：Brent Burley（迪士尼动画工作室）
* ‌**核心思想**‌："艺术家友好"的参数化
* ‌**参数体系**‌：Metallic/Roughness工作流成为行业标准

## **2014：‌游戏PBR革命‌**

* ‌**里程碑产品**‌：
  + Unreal Engine 4（Tim Sweeney）
  + Unity 5（Unity Technologies）
  + Frostbite引擎（EA DICE）
* ‌**硬件支撑**‌：PlayStation 4/Xbox One统一PBR管线

## **2018：‌实时光线追踪‌**

* ‌**硬件突破**‌：NVIDIA Turing架构（RT Core）
* ‌**标志产品**‌：
  + NVIDIA OptiX 5.0
  + Microsoft DXR API
  + UE4 Ray Tracing
* ‌**性能数据**‌：1080p路径追踪达60fps（对比1980年74分钟/帧）

---

# **技术演进关键转折点**

## **理论到应用的跨越（1980s）**

电影特效需求

工业光魔成立1975

Cook-Torrance模型

学术研究

康奈尔程序化渲染

Pixar RenderMan1988

## **实时渲染民主化（2000s）**

| 年份 | 硬件性能 | 代表游戏 | 光照技术 |
| --- | --- | --- | --- |
| 2001 | 10M tris/sec | 最终幻想X | 预烘焙光照 |
| 2007 | 500M tris/sec | 孤岛危机 | 动态光影 |
| 2013 | 2G tris/sec | 战地4 | 屏幕空间反射 |
| 2020 | 15G tris/sec | 赛博朋克2077 | 混合光追 |

## **学术-工业协同创新**

* ‌**SIGGRAPH纽带**‌：自1974年创办，成为技术转化桥梁
* ‌**关键人物迁移**‌：
  + Jim Blinn (NASA → Caltech → Microsoft)
  + Pat Hanrahan (皮克斯 → 斯坦福 → Tableau)
  + Eric Veach (谷歌 → 迪士尼 → Waymo)

---

# **未来发展方向**

## ‌神经辐射场（NeRF）

* 2020年伯克利提出，实现照片级新视角合成

## ‌**材质感知光传输**‌

* MIT 2023年实现亚表面散射实时模拟（Joule: 0.3ms/frame）

## ‌**量子光照计算**‌

* 谷歌Quantum AI实验室光量子处理器（2025目标）

光照模型发展史是计算机图形学从经验公式到物理真理的演进历程，每一步突破都凝聚着学术智慧与工业实践的碰撞，持续推动着虚拟世界与现实边界的融合。

---

> [【从UnityURP开始探索游戏渲染】](https://github.com):[蓝猫加速器](https://lanmaovqn.com)**专栏-直达**

（欢迎*点赞留言*探讨，更多人加入进来能更加完善这个探索的过程，🙏）
