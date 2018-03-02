# zero2one

>近日整理云盘发现几年下来，也算是做了不少的东西，看着一个个项目，发现爬过不少的坑，大学那会有想法想做个什么东西，找个心仪的图标都可以把自己逼疯。最近刚做完一个项目，发现现在做东西比之前顺手很多，遂趁热打铁，记录下过程。每个人、团队、公司做事情的习惯、流程可能都不一样，本文就以一个Android客户端的开发为例，结合自己的开发感受，只简单介绍想法到实现过程中关键点，罗列下使用的工具、资源。希望可以给追逐路上的你插上翅膀。


## 需求整理
当我们有了某个想法之后，总是第一个时间记在某个地方，比如云笔记、便签等地方，方便补充。但是等我们真正要着手开发一个产品的时候，比如App，不管是自己开发还是给别人查看，这些纯文字性的整理总是不够清晰明了。所以这个时候我们就需要一个工具来帮我们梳理，譬如脑图，这里可以需用XMind等脑图软件，整理完后，大概可能是下面的样子：

![产品结构脑图](http://upload-images.jianshu.io/upload_images/1694733-33c05012c990e4ad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这个时候，我们自己看着是不是也舒服多了？

先打住，这里一定要提下大家常说的MVP！MVP！MVP！

我们想做一个产品时，总是有N多假设，当然假设在自己心里总是美好的，恨不得马上实现上线给大家去用，心情可以理解。但是，如果不是抱着纯粹学习某方面知识的态度（譬如我就是想学学怎么写代码），就要去考虑我们的产品是不是人们需要的，抱着为什么用户要用我的产品的想法出发，用最小的成本去验证我们各种假设。注意，这里的验证不一定是代码实现的东西，更不是开发了一半功能的产品。

好了，就说这么多，有篇关于这方面的文章推荐一个（这难道是《精益创业》的读后感？）。
[A Minimum Viable Product Is Not a Product, It’s a Process.](http://blog.ycombinator.com/minimum-viable-product-process/)


## UI
这里在做出开发需要的设计图前，我们是不是可以先在纸上画出大概的样子？
比如这样：

![UI设计草图](http://image.woshipm.com/wp-files/2017/01/rwJt7onh7CxhFMNilA9n.png)

这个时候我们再去画产品设计图是不是更好一些？
对于移动端产品的设计尤其推荐Sketch。这里就不过多吹捧，用过都说好。这里有本[秘籍]（https://github.com/magicsu/zero2one/tree/master/ui/sketch%20templates）送给你（高质量模板、示例）。

### 配色
不懂配色？没有关系，对于我们来说，尽量避免一个页面内出现多种颜色，我们可以根据自己想做的产品方向选择合适的主题色，再来选一个辅色，配上这个工具，想必也丑不到哪里去。[MaterialPalette](https://www.materialpalette.com/light-blue/blue)

### 图标
我们在做设计图的时候可能会需要很多图标。对于Android应用来说，无论应用采用Material Design与否，官方图标当然都是首选，别说话了，[拿去吧](https://github.com/google/material-design-icons)。

这里，对于android开发者必须要介绍一个AS插件：Material design icon，可在生成各种尺寸png或vector格式的官方MD图标，生成后直接放入对应资源包中。另外，必须要提一点的是，对于当前越来越多的应用放弃拟物化，越来越扁平化，一个应用可能很少会使用拟物图标，这个时候vector图标就非常合适使用，当我们引用最新的com.android.support:appcompat-v7时，我们可以直接在项目中使用vector图标资源。在UI设计、开发中节省很多时间，统一了应用图标风格。另外，vector图标加载占用内存更小、性能更高。

另外，阿里妈妈[Iconfont](http://www.iconfont.cn/)也是很不错的选择。

### 开工
有了这些资源之后，我们是不是就可以开工了？刚开始是下面这样的。

![UI设计草图](https://github.com/magicsu/zero2one/blob/master/images/sketch.png?raw=true)

接下来，有个UI的大致框架后(这个应用采用的是Google的MaterialDesign样式，可以参考文档去设计)，我们就可以对照着产品功能脑图去完成剩余的工作，期间没有灵感的时候可以看下样式[模板](https://github.com/magicsu/zero2one/tree/master/ui/sketch%20templates)、刷[dribbble](https://dribbble.com/)，可能最快的解决办法就是模仿同类设计了（模仿优秀设计是一个好的习惯），最终，我们最终的效果差不多就是下面这种(强烈建议在Sketch中每个模块单独分到一个Page，下图为展示需要）。

![UI设计完成稿](https://github.com/magicsu/zero2one/blob/master/images/sketch_completed.jpg?raw=true)

## 开发测试
如果我们完成了应用的开发，第一时间就是要别人测试一下。因为我们自己测试总是有弊端，比如操作的习惯、使用的设备等等，都会影响测试的结果。当然，测试之前程序添加第三方的bug检测、数据统计都是必要的，方便测试修改。

## 相关资源
恩~这里都是干货。

### 第三方服务
我们在项目开发的各个阶段都有各种各样的需求，当我们无从下手的时候可以来这里看一下。这里从产品开发前期到设计阶段到开发测试都有相应的工具、服务，每个细分项里面的内容很全。

![DevStore](https://github.com/magicsu/zero2one/blob/master/images/dev_store.jpeg?raw=true)

## TODO
* UI
* 开发/测试
* 其他
