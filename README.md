# TreeLayout

[中文文档](README-ch.md)

TreeLayout 树形布局，提供多种自定义属性方便定制出各种各样的树形结构，当然实现时间轴更是不在话下。

# 目前完成的功能

1. 左侧为树形，右侧可以添加任意子控件，用法类似LinearLayout
2. 提供各类自定义属性，方便自定义主干、横枝、枝节点以及叶子
3. 可以灵活配置横枝指向目标条目的位置
4. 相对其他的树形结构实现方案高效，没有过多的嵌套层次，直接在ViewGroup中实现

# 待完善的功能
1. 点击折叠子项
2. 动画展开/折叠
3. 状态保存
4. 为子控件提供 layout_gravity 属性
5. 树形结构位置可配置（目前只能在左侧）

# 设计思路
TreeLayout 继承自 ViewGroup，可以直接在下面写控件，也可以通过 addView() 方法动态添加控件。这样可简化 TreeLayout 的使用，也使得子控件更为灵活，当然也减轻了相当多的绘制工作。
那么 TreeLayout 有两个职责：
1. 将所有添加进来的子控件垂直排布在树形结构的右侧
2. 在左侧根据子控件的位置及属性/特点绘制树形结构

为什么不直接继承 LinearLayout？
直接继承 LinearLayout 无疑要更简单一点，但是为了更灵活，以及后面更多功能的添加，直接继承自 ViewGroup，这样的可操作性更强。 

# LICENSE
TreeLayout is available under the MIT license.