# 混合模式

学习目标

1. 什么是混合模式？
2. 什么是基色、混合色、结果色？
3. 混合模式组
4. 混合模式的应用对象
5. 混合模式应用

### 什么是混合模式

对大多数人来说，在使用混合模式的过程就是一个探索的过程。因为应用混合模式所呈现的结果几乎是无法预知的。所以我们大多数时候，总在试试看，然后选择一种混合模式作为你的最终结果。

那么，混合模式究竟是什么？我们先来看几个应用混合模式的例子：

- 如果你有一张色调偏暗的照片，你想让它变亮一些，那么复制一份，然后应用滤色就可以了。
- 如果你有一张色调偏亮的照片，你想让它变暗一些，那么复制一份，然后应用正片叠底就可以了。

混合模式用于控制底层图像中的像素如何受上层图层像素的影响。

### 什么是基色、混合色、结果色？

为了能更加清晰的解释混合模式，我们先来确定几个概念：

- 基色是图像中的原稿颜色。
- 混合色是用于发生混合的颜色（绘画或编辑工具）。
- 结果色是混合后得到的颜色

### 混合模式组

- 【普通模式组】（概述：普通模式组中的模式，必须要降低图层不透明度才能看到效果。）
  - 正常：默认的混合模式。必须通过降低不透明度才可以使其与下面的图层混合。图层的不透明度100%时，完全覆盖下面的图像。
  - 溶解：降低不透明度后，可使图层上的像素离散，产生点状颗粒，使其成为结果色。结果色由基色或混合色的像素随机替换。
- 【加深模式组】(概述：加深模式组中的混合模式可使图像变暗。在混合过程中，图层中的白色将被底层较暗的像素替换。)
  - 变暗：查看每个通道中的颜色信息，并选择基色或混合色中较暗的颜色作为结果色。
  - 正片叠底：查看每个通道中的颜色信息，并将基色与混合色进行正片叠底(将基色与混合色相乘，再除以255)生成结果色。问：结果色比之前暗还是亮？[公式：结果色= (基色*混合色)/255
  - 颜色加深：查看每个通道中的颜色信息，并通过增加二者之间的对比度使基色变暗以反映混合色。[公式：结果色=基色-(基色的反相*混合色的反相)/混合色
  - 线性加深：查看每个通道中的颜色信息，并通过减小亮度使基色变暗以反映混合色。[公式：结果色=(基色+混合色)-255
  - 深色：检查每个通道中的颜色信息，比较混合色和基色的所有通道值的总和并显示值较小的颜色。[公式：结果色=min(基色、混合色)
- 【减淡模式组】(概述：减淡模式组中的混合模式可使图像变亮。在混合过程中，图层中的黑色会被底层较亮的像素替换。)
  - 变亮：查看每个通道中的颜色信息，并选择基色或混合色中较亮的颜色作为结果色。
  - 滤色：查看每个通道的颜色信息，并将混合色的互补色与基色的补色进行正片叠底。 [结果色=255-[(255-基色)*(255-混合色)/255
  - 颜色减淡：查看每个通道中的颜色信息，并通过减小二者之间的对比度使基色变亮以反映出混合色。[结果色=基色+(基色*混合色)/(255-混合色)
  - 线性减淡：查看每个通道中的颜色信息，并通过增加亮度使基色变亮以反映混合色。 [结果色=基色+混合色
  - 浅色：查看每个通道中的颜色信息，比较混合色和基色的所有通道值的综合，并显示值较大的颜色。 [公式：结果色=max(基色、混合色)
- 【对比模式组】（概述：对比模式组中的混合模式可增强图像反差。在混合时，50%的灰会完全消失，任何亮度值高于50%的灰色的图像都可能加亮底层图像；亮度值低于50%灰色的像素则可能使底层图像变暗。）
  - 叠加：对颜色进行正片叠底或过滤，具体取决于基色。图案或颜色在现有像素上叠加，同时保留基色的明暗对比。不替换基色， 但基色与混合色相混以反映原色的亮度或暗度。
  - 柔光
  - 强光
  - 亮光
  - 线性光
  - 点光
  - 实色混合
- 【反相模式组】（概述：如果当前图层包含白色，白色区域会使底层图像反相，而黑色不会对底层图像产生影响。）
  - 差值
  - 排除
  - 减去
  - 划分
- 【颜色模式组】
  - 色相
  - 饱和度
  - 颜色
  - 明度

### 混合模式的应用对象

### 混合模式应用