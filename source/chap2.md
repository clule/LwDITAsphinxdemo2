# Why Use LwDITA

## 适用场景

LwDITA是一种基于标准的替代品，它适用于：

**1. 使用DITA 1.3过于复杂的情况：**

DITA 1.3 拥有成熟的结构和多样化的功能，但这种成熟的结构也可能让那些希望采用DITA进行写作的技术人员望而却步。LwDITA在提供精简后DITA解决方案的同时，依旧支持与DITA 1.3 的完全兼容。

**2. 不使用XML作为创作基础的技术协作人员:**

有些技术写作人员依赖除XML以外的特定格式进行写作（例如Markdown或HTML）。尽管这些格式与XML的表现稍有区别，也可以融入到DITA生态系统当中。为了方便他们的使用，LwDITA是第一个跨格式的DITA版本，支持HTML5和Markdown编辑。

——————————————————————

但LwDITA不是DITA 1.3 的替代品。一直使用DITA进行创作的技术人员可以尝试使用LwDITA，但他们并不是LwDITA的主要受众。LwDITA真正关注的，是那些之前并没有使用DITA，或者不熟悉使用XML进行创作的团队。LwDITA会作为这些用户创作和复用内容的入门工具。

LwDITA本意是作为DITA 1.3 版本的一个子集。

---

## 核心

- 提供精简的DITA使用体验
- 提供XML，HTML5，Markdown之间的映射。由此，用户可以：
  - 使用熟悉的格式进行内容创作
  - 多种标记语言格式内容的轻松发布
- ？？支持LwDITA的新型、低成本应用的出现
这三个方面会在接下来文章中进行详细介绍。

### 精简的结构

简化DITA到最小程度是设计LwDITA的主要目的之一。
LwDITA支持DITA标准核心功能，例如：语法标记（semantic tagging）、话题指向（topic orientation）、内容复用（content reuse）等等。但为了在更多行业领域内适用，采用了较DITA 1.3相比更通用的结构，但由此也限制了本身的元素种类、属性、功能，同时降低了适用难度。
上到会议展示，下到使用者的博客，有时会形容DITA的元素类型多的吓人：DITA 1.3拥有189种元素类型；而相比之下LwDITA48种，其中39种从DITA 1.3中沿袭而来，另外增加了9种多媒体元素种类。

### 多种标记语言的支持

开发LwDITA的另一个目的是希望讲DITA从XML语法中解放出来。许多刚毕业的软件开发人员对XML构造几乎没有直接的经验，而对Markdown和HTML等其他格式则更加熟悉。如今，技术写作人员采用HTML5进行网络结构化文档创建已经非常普遍；Markdown语言也被许多行业和学术界所接受。LwDITA针对这种情况，增加了对两种标记语言的支持，根据语言的不同，LwDITA分为以下三种:

- **XDITA：** 基于XML的LwDITA
- **HDITA：** 基于HTML-5的LwDITA
- **MDITA：** 基于Markdown的DITA

这些创作格式可以增强跨部门之间的合作，例如工程师可以适用Markdown编写，网站营销人员可以使用HTML5编写，技术写作人员和其他熟悉DITA的人可以用XML编写。不同语言编写的问价可以轻松集合成单个文档集合发布，并集成在DITA 1.3当中。

**未来发展趋势：** 可能会逐步增加DITA与JSON、AsciiDoc、MS Word之间的映射。

### 低成本LwDITA工具的出现

DITA技术委员会希望通过简化DITA，降低企业开发平价DITA工具的成本。

DITA 1.3版本的情况是：过多的元素和功能限制了企业开发基于DITA的写作、发布的新平台系统。结构精简的LwDITA避免了这一情况，为未来可能出现的商业、开源应用做好铺垫。

---

## LwDITA与标准DITA的区别

以下列举了一些LwDITA与标准DITA之间的显著区别，但再LwDITA规范确定之后可能会有所更改：

- 不允许混合内容。所有文本内容必须存在于‹p›元素中。比如：++‹li›这是一个列表项‹/li›++ 这一句存在语法错误。要想改正需要增加‹p›标签，例如：++‹li› ‹p›这是一个列表项‹/p› ‹/li›++ 此是为了确保跨内容的统一，和结构的可预测性，使开发样式表和工具来处理内容变得更加容易
- 没有CALS表元素（‹table›，‹row›，‹entry›等）。举个例子，这意味着用户无法创建具有合并单元格，标题或特定列宽的复杂表格。
- 没有prolog元信息（所有内容都在‹data›标签中）
- 没有相关链接
- 只有突出显示highlight的域中的子集：‹b›，‹i›，‹u›，‹sup›，‹sub›标签可用
- 只有‹topicmeta›、‹topicref›可用，没有‹topichead›和‹topicgroup›
- 没有‹topicmeta›和‹topicref›可用，没有‹topichead›和‹topicgroup›标签
- 地图没有‹title›元素。标题（如需要添加）可以放在‹topicmeta›中的‹navtitle›中
- 仅‹topicmeta›和‹topicref›可用；没有‹topichead›或‹topicgroup›
- 属性可以随时启用和关闭。其中，默认只有@props可用，其他属性可以进行自定义添加

### LwDITA和标准DITA的兼容性

像前文说的那样，LwDITA可以说算是标准DITA的一个子集，因此，大多数LwDITA内容都与标准DITA环境兼容。

此外，在标准地图（map）中允许LwDITA主题和标准DITA主题同时出现。但在LwDITA环境中并不能使用DITA标准版本的地图和属性。
