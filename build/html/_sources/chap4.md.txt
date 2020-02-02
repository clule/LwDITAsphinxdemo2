# LwDITA的种类

## XDITA

XDITA是基于XML的LwDITA，也是DITA标准版本的一个子集，并额外增加了新媒体元素类型。

**面向对象：**
XDITA面向不需要使用DITA标准版全部功能的用户设计。

XDITA的++潜在用户++包括：

- 使用XML编辑器工作，但仅使用少量元素和属性的用户
- 希望减少开发、维护样式表成本的部门
- 希望已有的DITA内容兼容Markdown或者HTML5的内容创作者

    **举例**

XDITA topic（基于DITA标准版元素类型，新增加多媒体元素，如 ++< video >++ 标签）

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE topic PUBLIC "-//OASIS//DTD LIGHTWEIGHT DITA Topic//EN" "lw-topic.dtd">
<topic id="install-and-setup">
<title>Installing and Setting up Remote Lighting</title>
<shortdesc>Installation of your lighting kit includes installing the light bulbs
into light fixtures, preparing the remote control, and programming lighting groups.
</shortdesc>
<prolog>
<data name="author" value="Kevin Lewis"/>
</prolog>
<body>
<section>
<title>Steps</title>
<ul>
<li><p>Install light bulbs.</p></li>
<li><p>Prepare remote control.</p></li>
<li><p>Program lighting groups.</p></li>
</ul>
</section>
<section>
<title>Example</title>
<p>The following video demonstrates a recommended installation:</p>
<video>
<video-poster value="remote-poster.jpg" />
<media-controls />
<media-source value="remote.mp4" />
</video>
</section>
</body>
</topic>
```

## HDITA

HDITA是基于HTML-5的LwDITA，包含定制的属性，其中HTML中一些标签的使用与DITA相互转换。

**面向对象**
熟悉使用HTML进行结构化内容开发的人员。

HDITA的++潜在用户++包括:

- 市场文档写作者，不使用XML编辑器，但能贡献基于DITA的产品信息
- 使用HTML写作工具的软件开发人员
- 想使用移动端设备编辑内容的博主或内容架构师
- 只需编写内容但不想要格式转换过程的文档作者
- 熟悉和偏好HTML5的文档写作者

    **举例**

HDITA topic（使用与HTML5相同的元素类型和属性，提高复用性和与DITA的兼容性）

```html
<!DOCTYPE html>
<html>
<head>
<title>Installing and Setting up Remote Lighting</title>
</head>
<body>
<article id="install-and-setup">
<h1>Installing and Setting up Remote Lighting</h1>
<p>Installation of your lighting kit includes installing the light bulbs into
light fixtures, preparing the remote control, and programming lighting groups.</p>
<h2>Steps</h2>
<ul>
<li>
<p>Install light bulbs.</p>
</li>
<li>
<p>Prepare remote control.</p>
</li>
<li>
<p>Program lighting groups.</p>
</li>
</ul>
<section>
<h2>Example</h2>
<p>The following video demonstrates a recommended installation:</p>
<video src="remote.mp4" controls poster="remote.png"></video>
<p data-conref="bulbs-to-groups.dita#bulbs-to-groups/assign-disclaimer"></p>
</section>
</article>
</body>
</html>
```

## MDITA

MDITA是基于Markdown的LwDITA，包含两种类型：

1. **核心类型（core profile）：**
对应GitHub Flavored Markdown（GFM）
2. **扩展类型（extended profile）：**
针对于一些只在特定Markdown格式才中出现的功能，提供更加友好的DITA体验。

**面向对象：**
由于MDITA分为两种类型，它的++潜在用户++也分为两类：

核心类型MDITA的用户：

- 不想使用XML编辑器，但要为基于DITA的产品文档贡献内容的软件开发人员
- 负责API文档应用的开发或者技术写作者，需要将内容与其他技术文档应用共享
- 想要使用移动端（但不支持XML编辑器）编辑的写作者
- 希望内容后期能快速地转换为结构化的内容
- 希望利用DITA重用和发布机制，但不依赖于XML标签的写作者

扩展类型MDITA的用户：

- 接收文档开发人员Markdown格式文件的内容管理人员
- 想将Markdown文件包含进DITA或者XDITA话题集合中的技术写作人员
- 想要使用移动端（但不支持XML编辑器）编辑的写作者

    **举例**

MDITA *core profile*

MDITA核心类型中包含Markdown格式本身包含的信息架构，允许用户使用熟悉的写作方式编辑，例如：• Title；Paragraph；Section title；Ordered list；Unordered list；Link；Image；Preformatted text；Italics；Bold；Table；Code block

```md
# Installing and Setting up Remote Lighting
Installation of your lighting kit includes installing the light bulbs into light
fixtures, preparing the remote control, and programming lighting groups.
## Suggested Steps
1. Install light bulbs.
2. Prepare remote control.
3. Program lighting groups.
## Example
![Remote installation example](remote.png)
```

**使用LwDITA跨格式创建内容**
LwDITA支持跨格式的内容共享。作者可以同时使用XDITA，HDITA，MDITA，或DITA 1.3标准版进行创作，然后统一集合发布。除MDITA 核心类型外，用户可以在其他所有格式中使用content references和key reference。
跨格式内容共享的能力可以用来：

- 使用XDITA地图链接XDITA，HDITA，MDITA，或DITA 1.3标准版格式的话题
- 使用XDITA话题重用MDITA话题
- 使用HDITA话题重用MDITA话题
- 使用MDITA扩展类型话题重用HDITA话题
