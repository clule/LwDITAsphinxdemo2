# LwDITA设计

## LwDITA的话题组成

LwDITA通过精筛，保留了以下文档组成部分：

- Body
- Cross reference
- Data
- Description
- Figure
- Footnote
- Image and alternate text
- In-line formatting: Bold, italics, underline, subscript, superscript
- Lists: Definition list, ordered list, unordered list
- Note
- Paragraph
- Phrase
- Prolog
- Preformatted text
- Section
- Short description
- Table
- Title
- Topic

## LwDITA的地图组成

LwDITA通过精筛，保留了以下地图组成元素：

- Data
- In-line formatting: Bold, italics, underline, superscript, subscript
- Key definition
- Link text
- Map
- Navigation title
- Phrase
- Topic metadata
- Topic reference

## 更加严格的模型限制

更加严格的模型减少了写作时进行选择时的思考成本，但依赖于一些硬性规定。例如在XDITA和HDITA中，除了description、short description、和title元素之外，所有的文字必须包含在段落标签中，提高信息复用性。在段落中可以出现Bold、Italics、Phrase、Superscript、Subscrip、Underline几种形式。

DITA 1.3中的标签形式：

```xml
<section>Compatible light bulbs include the following:
<ul>
<li>Compact Fluorescent</li>
<li>Light Emitting Diode</li>
</ul>
</section>
```

对比LwDITA中的有效标签形式：

```xml
<section>
<p>Compatible light bulbs include the following:</p>
<ul>
<li>
<p>Compact Fluorescent</p>
</li>
<li>
<p>Light Emitting Diode</p>
</li>
</ul>
</section>
```

## 多媒体内容

LwDITA为**多媒体内容**添加了新的元素类型。 这些元素类型与
HTML5兼容，接下来也会在DITA 1.3标准版中出现。
DITA 1.3规范中将‹object›元素类型设置为
在主题中包含的多媒体内容，与HTML中的‹object›对应。 LwDITA更新了XML到HTML元素类型的对应关系，将原来存在于DITA 1.3中的‹object›和‹param›标签进行细化，整理为以下几个元素类型：

- Audio
- Autoplay
- Controls
- Loop
- Muted
- Poster
- Source
- Track
- Video

**注：** 多媒体元素不能在MDITA中使用。
