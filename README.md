# d3入门

[常用数据可视化工具简介](#常用数据可视化工具)

[D3简介](#d3简介)

[常用API](#d3api)

- [API总览](#d3api)
- [元素操选择](#元素操选择)
- [元素编辑](#元素编辑)
- [数据绑定](#数据绑定)
- [比例尺](#比例尺)

[SVG基础](#svg基础)

[举个栗子🌰](#举个例子)

[如何完成一个用户轨迹图绘制](#如何完成一个用户轨迹图绘制)


## 常用数据可视化工具

| 工具库|兼容性 |是否免费/开源| 优点 | 缺点 |
| --- | --- | --- | --- | --- |
| [D3](https://github.com/d3/d3/wiki/Gallery) |IE9|完全免费，代码开源 |能够通过扩展实现任何可以想到的数据可视化效果，调试容易、扩展效果较多、调用方式类JQuery| 学习曲线太过严苛、好效果需要深入理解JavaScript |
| [Echarts](http://echarts.baidu.com/) |IE6|完全免费，代码开源|中文文档和支持、使用方便，底层依赖轻量级的 Canvas 类库 ZRender|基础图形都有，地图也有(扩展不多)。提供很多参数接口，但是不能自己定义新的图形样式|
| [Highcharts](http://www.highcharts.com/demo)|IE6 |非商业免费，商业需授权，代码开源|超轻量级，并且性能非常好，浏览器兼容性好|图表类型有限|
|[Chart.js](http://www.chartjs.org/samples/latest/)|支持所有现代浏览器|开源|响应式|图表类型有限|

[FusionCharts](https://www.fusioncharts.com/)、 [JavaScript InfoVis Toolkit](http://philogb.github.io/jit/)、[zingchart](https://www.zingchart.com/)

Highcharts currently supports line, spline, area, areaspline, column, bar, pie, scatter, angular gauges, arearange, areasplinerange, columnrange, bubble, box plot, error bars, funnel, waterfall and polar chart types.

## d3简介

 D3.js is a JavaScript library for manipulating documents based on data. D3 helps you bring data to life using HTML, SVG, and CSS. D3’s emphasis on web standards gives you the full capabilities of modern browsers without tying yourself to a proprietary framework, combining powerful visualization components and a data-driven approach to DOM manipulation.
D3 (Data-Driven Documents or D3.js) 是一个Web标准的书籍可视化工具库。 D3帮助我们通过使用SVG、Canvas、HTML让数据变得生动，D3将可视化、交互技术与数据驱动的DOM操作完美结合。让我们可以充分发挥现代浏览器的功能，自由地设计合理的数据可视化界面。
https://d3js.org/#transformation
[d3github](https://github.com/d3)
[d3画廊](https://github.com/d3/d3/wiki/Gallery)

功能模块

![d3功能模块](http://upload-images.jianshu.io/upload_images/280923-4dfaf35d0eb1d04f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### 安装

NPM: `npm install d3`或script标签引用
```javascript
<script src="https://d3js.org/d3.v4.min.js"></script>
```
d3是由各个模块协同工作的，而不是一个单独的库（v4版本开始）。你可以按需加载独立的模块，默认的大库包含了大概30个子库。
如:
```javascript
<script src="https://d3js.org/d3-selection.v1.js"></script>
```
```javascript
import {scaleLinear} from "d3-scale";
```
### 支持环境
D3支持“现代”浏览器，也就是除IE8及以下的浏览器。

## d3API

[API](https://github.com/d3/d3/blob/master/API.md)

* [Arrays](https://github.com/xswei/d3js_doc/tree/master/API/d3-array-master)  (Statistics, Search, Transformations, Histograms)(**数组、
静态方法、查找类方法、变换类方法、直方图**)

* [Axes](https://github.com/xswei/d3js_doc/tree/master/API/d3-axis-master)(**坐标轴**)

* [Brushes](https://github.com/xswei/d3js_doc/tree/master/API/d3-brush-master)(刷子)

* [Chords](https://github.com/xswei/d3js_doc/tree/master/API/d3-chord-master)(弦图)

* [Collections](https://github.com/xswei/d3js_doc/tree/master/API/d3-collection-master)(Object,Maps,Sets,Nests)(集合、对象、map、嵌套)

* [Colors](https://github.com/xswei/d3js_doc/tree/master/API/d3-color-master)(颜色)

* [Delimiter-Separated Values(d3-dsv)](https://github.com/xswei/d3js_doc/tree/master/API/d3-dsv-master)(dsv模块)

* [Dispatches](https://github.com/xswei/d3js_doc/tree/master/API/d3-dispatch-master)(事件调度)

* [Dragging](https://github.com/xswei/d3js_doc/tree/master/API/d3-drag-master)(**拖拽**)

* [Easings](https://github.com/xswei/d3js_doc/tree/master/API/d3-ease-master)(**过渡类型**)

* [Forces](https://github.com/xswei/d3js_doc/tree/master/API/d3-force-master)(**力学仿真模拟**)

* [Number Formats](https://github.com/xswei/d3js_doc/tree/master/API/d3-format-master)(数值格式化)

* [Geographies](https://github.com/xswei/d3js_doc/tree/master/API/d3-geo-master)(地理)

* [Hierarchies](https://github.com/xswei/d3js_doc/tree/master/API/d3-hierarchy-master)(层次结构布局)

* [Interpolators](https://github.com/xswei/d3js_doc/tree/master/API/d3-interpolate-master)(插值器)

* [Paths](https://github.com/xswei/d3js_doc/tree/master/API/d3-path-master)(Canvas和SVG之间互转)

* [Polygons](https://github.com/xswei/d3js_doc/tree/master/API/d3-polygon-master)(二维多边形)

* [Quadtrees](https://github.com/xswei/d3js_doc/tree/master/API/d3-quadtree-master)(四叉树)

* [Queues](https://github.com/xswei/d3js_doc/tree/master/API/d3-queue-master)(队列)

* [Random Numbers](https://github.com/xswei/d3js_doc/tree/master/API/d3-random-master)(随机数)

* [Requests](https://github.com/xswei/d3js_doc/tree/master/API/d3-request-master)(数据请求)

* [Scales](https://github.com/xswei/d3js_doc/tree/master/API/d3-scale-master)  (Continuous, Sequential, Quantize, Ordinal)(比例尺)

* [Selections](https://github.com/xswei/d3js_doc/tree/master/API/d3-selection-master)  (Selecting, Modifying, Data, Events, Control, Local Variables, Namespaces)(选择集)

* [Shapes](https://github.com/xswei/d3js_doc/tree/master/API/d3-shape-master)  (Arcs, Pies, Lines, Areas, Curves, Symbols, Stacks)(形状)

* [Time Formats](https://github.com/xswei/d3js_doc/tree/master/API/d3-time-format-master)(日期时间)

* [Time Intervals](https://github.com/xswei/d3js_doc/tree/master/API/d3-time-master)(时间间隔)

* [Timers](https://github.com/xswei/d3js_doc/tree/master/API/d3-timer-master)(定时器)

* [Transitions](https://github.com/xswei/d3js_doc/tree/master/API/d3-transition-master)(过渡)

* [Voronoi Diagrams](https://github.com/xswei/d3js_doc/tree/master/API/d3-voronoi-master)(Voronoi图)

* [Zooming](https://github.com/xswei/d3js_doc/tree/master/API/d3-zoom-master)(缩放)

### 常用方法举例

[d3-selection](https://github.com/d3/d3-selection) 

#### 元素操选择

***d3.select(selector)*** 选择第一个匹配selector字符串的元素:
```javascript
var anchor = d3.select("a");
```
***d3.selectAll(selector)*** 选中所有与selector匹配的元素:
```javascript
var paragraph = d3.selectAll("p");
```
#### 元素编辑

***selection.attr(name[, value])*** 设置或获取元素的name属性；
***selection.style(name[, value[, priority]])*** 设置style样式，如果指定了value，则设置对应的样式为value。value可以为变量，也可以为一个函数。
```javascript
d3.select("a")
    .attr("name", "fred")
    .style("color", "red");
```
***selection.classed(names[, value])*** 设置或获取指定的类名状态，如果指定了value则根据value值启用或关闭类：
```javascript
selection.classed("foo bar", true);//添加类
selection.classed("foo bar", false);//移除类
selection.classed("foo bar");//获取类名状态
```
***selection.text([value])*** 设置或获取text content内容。可以使用这个方法清空元素内容。
***selection.html([value])*** 设置或获取inner HTML内容
***selection.append(type)*** 如果*type*是一个字符串，则在选择集中的每个元素的子元素末尾追加一个元素。如果selection是一个enter selection，则将元素追加到元素末尾，作为选择集中元素的下一个兄弟节点。
***selection.remove()*** 移除元素

#### 数据绑定

***selection.data([data[, key]])***
```javascript
    d3.selectAll('p').data( [1, 2, 3, 4, 5, 6]).text(function (d) {
        return d
    })//选择文档中所有的p元素与数组[1,2,3,4,5,6]绑定，并将p元素的文本设置为数组对应值
```
##### Update、Enter、Exit 

数据绑定是当数组的长度与元素数量不一致（数组长度 > 元素数量 or 数组长度 < 元素数量），这时候就需要理解 Update、Enter、Exit 的概念。
如果数组为 [3, 6, 9, 12, 15]，将此数组绑定到三个 p 元素的选择集上。可以想象，会有两个数据没有元素与之对应，这时候 D3 会建立两个空的元素与数据对应，这一部分就称为 Enter。而有元素与数据对应的部分称为 Update。如果数组为 [3]，则会有两个元素没有数据绑定，那么没有数据绑定的部分被称为 Exit。[参考](http://wiki.jikexueyuan.com/project/d3wiki/enterexit.html)

![enter exit图解](http://upload-images.jianshu.io/upload_images/280923-7b4b685d4dc4d182.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 比例尺

d3中的比例尺描述的是一种映射关系；
比例尺，很像数学中的函数。例如，对于一个一元二次函数，有 x 和 y 两个未知数，当 x 的值确定时，y 的值也就确定了。
在数学中，x 的范围被称为**定义域**，y 的范围被称为**值域**。
D3 中的比例尺，也有定义域和值域，分别被称为 domain 和 range。开发者需要指定 domain 和 range 的范围，如此即可得到一个计算关系。

##### 常用比例尺

***连续型比例尺Continuous Scales***
连续型比例尺可以将连续的，可量化的输入 domain 映射到另一个一个连续区间 range.如果 range 也是数值类型，则映射可以 inverted(逆计算). 连续比例使用 linear, power, log, identity, time 或 sequential color 来创建.
```javascript
var x = d3.scaleLinear()
    .domain([0, 10])
    .range([0, 100]);

x(1); // 10
x(5); // 50
x.invert(80);//8 逆运算
```
***Quantize Scales量化比例尺***
量化比例尺根据输出范围将输入分割成不同的片段，每个片段内的值都会对应同一个range值。
```javascript
var color = d3.scaleQuantize()
    .domain([0, 1])
    .range(["brown", "steelblue"]);

color(0.49); // "brown"
color(0.51); // "steelblue"
```
***Ordinal Scales序数比例尺***
有时候，定义域和值域不一定是连续的。例如，有两个数组：
```javascript
var index = [0, 1, 2, 3, 4];
var color = ["red", "blue", "green", "yellow", "black"];
```
我们希望 0 对应颜色 red，1 对应 blue，依次类推。
但是，这些值都是离散的，线性比例尺不适合，需要用到序数比例尺。
```javascript
var ordinal = d3.scaleOrdinal()
        .domain(index)
        .range(color);

ordinal(0); //返回 red
ordinal(2); //返回 green
ordinal(4); //返回 black
```
## SVG基础
SVG 意为可缩放矢量图形（Scalable Vector Graphics）。
SVG 使用 XML 格式定义图像。
圆、箭头、路径、线条
[W3School](http://www.w3school.com.cn/svg/index.asp)

## 举个例子

![image.png](http://upload-images.jianshu.io/upload_images/280923-236df1231bc24294.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/400)

[地址](http://localhost:63342/demo/d3-histogram.html?_ijt=bam8m7m8l6sfhndrlrggs47vfi)

## 如何完成一个用户轨迹图绘制

### 需求：

展示蜗牛客户端用户浏览路径，使用不同颜色、粗细的线条叠加展示所有用户的浏览轨迹
[交互稿](http://10.240.100.17:8080/yunyuedu/蜗牛/交互/客户端/轨迹图/#g=1&p=轨迹图说明)
[线上地址](http://manhua.pris.netease.com/heatmapUserTrail.do?type=1&platform=0)

### 需求实现步骤，对应知识点

[d3-selection](https://github.com/d3/d3-selection)
[d3-force](https://github.com/d3/d3-force)
d3中的[d3-force](https://github.com/d3/d3-force)力导向模块，是绘图的一种算法。实现了物理粒子之间的作用力仿真，在二维或三维空间里配置节点，节点之间用线连接，称为连线。节点和连线都被施加了力的作用，力是根据节点和连线的相对位置计算的。根据力的作用，来计算节点和连线的运动轨迹，并不断降低它们的能量，最终达到一种能量很低的安定状态。
***力导向图能表示节点之间的多对多的关系***

##### step1定义点、线数据

```javascript
var graph = {
        links: [{
            source: 1,
            target: 3,
            value: 139920
        }, {
            source: 11,
            target: 16,
            value: 139920
        }],
        nodes: [{
            x: 172,
            y: 543.5,
            meta: {
                eId: "c1-39",
                height: 33,
                id: 10403,
                name: "领读-感兴趣的人加关注",
                pageName: "c1-领读"
            }
        }, {
            x: 172,
            y: 543.5,
            meta: {
                eId: "a1-13",
                height: 33,
                id: 10403,
                name: "书桌-向左滑动",
                pageName: "a1-书桌"
            }
        }]
    }
```
首先为指定的一组节点创建一个仿真[simulation](https://github.com/xswei/d3js_doc/tree/master/API/d3-force-master#simulation)并且指定[力学模型类型]
(https://github.com/xswei/d3js_doc/tree/master/API/d3-force-master#simulation_force)    
```javascript
  var simulation = d3.forceSimulation(this.graph.nodes)//仿真指定数组
          .force("link", d3.forceLink(linkDataArray)//为指定的link数组创建一个link作用力
         .id(function (d) {
            return d.index
          }))//设置link中节点的查找方式
          .force("charge", d3.forceManyBody())//使用默认的设置构建一个多体作用力
          .force("center", d3.forceCenter(this.bgStyle.width / 2, this.bgStyle.height / 2))//重力，布局有一个参考位置，不会跑偏
          .stop()//停止仿真
          .on("tick", ticked);//监听仿真事件
 
```
点线关联后数据变化:
![link-after.jpg](http://upload-images.jianshu.io/upload_images/280923-d9dbaa9a711300ef.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
仿真模拟器新建之后，连线的两个节点序号，分别变成了对应的节点对象。
![node-after.jpeg](http://upload-images.jianshu.io/upload_images/280923-504b7c2dad34049e.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
以下几个属性是通过仿真模拟器添加的
index - 节点的索引
x - 节点当前的 x-位置
y - 节点当前的 y-位置
vx - 节点当前的 x-速度 
vy - 节点当前的 y-速度
下一个位置 ⟨x + vx,y + vy⟩
如果要为某个节点设置默认的位置，则需要为该节点设置如下两个属性:
fx - x-位置
fy - y-位置
这里由于需求原因节点x，y坐标已经固定，所以x,y、fx,fy已经预先设定。
在每次[tick](https://github.com/xswei/d3js_doc/tree/master/API/d3-force-master#simulation_tick)完成后，定义了*node*.fx的节点的*node*.x将被重置为*node*.fx，*node*.vx被设置为0. 同理*node*.y将被重置为*node*.fy，*node*.vy被设置为0

##### step2绑定点、线数据绘图、事件处理

```javascript
     linkSelect = linkSelect.data(linkDataArray, function (d) {
          return "link_" + d.source.name + "_" + d.target.name + "_" + d.index;
        }).enter()
          .append("svg:path")
          .attr("id", function (d) {
            return "link_" + d.source.name + "_" + d.target.name + "_" + d.index
          })
          .attr("class", "link")
          .attr("marker-end", function (d) {
            return "url(#markerLevel" + (d.level) + ")";
          })
          .style("stroke", function (d) {
            return hueLink(d.level);
          })
          .style("stroke-width", function (d) {
            return widthLink(d.level) * scale / 10.0;
          }).attr("d", function (d) {
            if (d.linkD) return d.linkD;

            d.linkD = getLinkD(d);
            return d.linkD;
          })
          .on("click", this.$switchToEditMode.bind(this))
          .on("mouseover", this.linkMouseOver.bind(this))
          .on("mouseout", this.linkMouseOut.bind(this));
```

##### step3增加拖动、仿真

调用 call( force.drag ) 后节点可被拖动。force.drag() 是一个函数，将其作为 call() 的参数，相当于将当前选择的元素传到 force.drag() 函数中。
开始拖动点时开始触发仿真事件，由于力导向图是不断运动的，每一时刻都在发生更新，因此，必须不断更新节点和连线的位置。
```javascript
 function ticked() {
          nodeSelect.attr("transform", function (d) {
            d.nodeTransform = "translate(" + d.fx + "," + d.fy + ")";
            return d.nodeTransform
          })
          linkSelect.attr("d", function (d) {
            d.linkD = getLinkD(d);
            return d.linkD;
          })
        }

        function dragsubject() {
          return simulation.find(d3.event.x, d3.event.y);
        }

        function dragstarted(d) {
          if (!d3.event.active) simulation.alphaDecay(0.5).alphaTarget(0.3).restart();
        }

        function dragged(d) {
          let x = d3.event.x > 0 ? d3.event.x : 0;
          let y = d3.event.y > 0 ? d3.event.y : 0;
          if (x > bgStyle.width) {
            x = bgStyle.width
          }
          if (y > bgStyle.height) {
            y = bgStyle.height
          }
          d.fx = x
          d.fy = y
        }

        function dragended(d) {
          if (!d3.event.active) simulation.alphaTarget(0);
          let x = d3.event.x > 0 ? d3.event.x : 0;
          let y = d3.event.y > 0 ? d3.event.y : 0;
          if (x > bgStyle.width) {
            x = bgStyle.width
          }
          if (y > bgStyle.height) {
            y = bgStyle.height
          }
          d.fx = x
          d.fy = y
        }

        nodeSelect = nodeSelect.data(this.graph.nodesNoFake, function (d) {
          return "node_" + d.name;
        });
        nodeSelect.exit().remove();
        nodeSelect = nodeSelect.enter().append("svg:g")
          .attr("id", function (d) {
            return "node_" + d.name;
          })
          .attr("class", "node")
          .style("display", function (d) {
            if (d.siblings && d.siblings.some(function (item, index, array) {
                return item && item.link.visible
              })) {
              return '';
            }
            return 'none';
          })
          .attr("transform", function (d) {
            if (d.nodeTransform) return d.nodeTransform;
            d.nodeTransform = "translate(" + d.fx + "," + d.fy + ")";
            return d.nodeTransform
          })
          .call(drag)
          .on('click', this.displayClickData.bind(this));

        nodeSelect.append("svg:circle")
          .attr("r", function (d) {
            return d.r;
          })
          .style("fill", function (d) {
            return hueNode(d.out + d.in);
          });
```
