#css命名思考
## 命名的思考
>名字本质符号，是用来区分。简单常见的名字可用来复用。独特的名字比较少被复用
>使用BEM的诀窍是，你要知道什么时候哪些东西是应该写成BEM格式的。因为某些东西确实是位于一个块的内部，但这并不意味它就是BEM中所说的元素。这个例子中，网站logo完全是恰巧在.header的内部，它也有可能在侧边栏或是页脚里面。一个元素的范围可能开始于任何上下文，因此你要确定只在你需要用到BEM的地方你才使用它。
为什么css命名这么难？  
其他语言为什么不需要那么纠结。类名全局，无命名空间，无关键字
设计师的灵感及突发奇想
但却灵活 像xml
###我的命名尝试
-包含父类
-缩进式
-互为上下文式
##命名类型
-展示性命名 eg : btn-primary
-内容性命名 eg : intro-text
-功能性命名 eg : green-btn
##BEM命名法则
>.block .block_element .block--modifier
-.block 代表最高级别的抽象或组件
-.block_element 代表 .block的后代，用于形成一个完整的.block的整体
-.block--modifier 代表.block的不同状态或者版本
防止脱节，形成上下文

>Block  !误区:这个block并非inline-block里的block,而是将所有东西都划分为一个**独立的模块**,一个header是block,header里嵌套的搜索框是block,甚至一个icon一个logo也是blockblock可以相互嵌套
>Element !误区:如果一个Element-son是另一个Element-father的子元素, 那么写法是 Block__Element-father__Element-son_Modifer,嵌套多了会很长么? 不是的!!! 一个Block下的所有Element无论相互层级如何,都要摊开扁平的属于Block所以 BEM 最多只有 B+E+M 三级,不可能出现 B+E+E+..+E+M 超长class名,也要求E不能同名
>Modifier 之前我们经常写的 .current .active 等表达状态
##规定一些关键字
main bd hd nav header footer cont sidebar main_cont wrapper login reg
btn- ico- pic- bg- link-
btn_info btn_ico
page-head page-content page-foot ?
##缩进增加上下文的联系
.page {}
    .page__content {}
    .page__sub-content {}
    .page__footer {}
        .page__copyright {}
##案例分析
###豆瓣网 张克军
豆瓣主页 类似BEM的命名方法  
anony-   匿名   annoymous_home.css
##我的结论
-结构可用BEM
-可重用的部分，如组件不使用
-页面css适当分离，主页面样式如果与子页面不共用
-BEM实际是规定了类似命名空间，css无命名空间的概念，所有的变量都是全局的
-结构下为组件式的命名
-前缀能起到命名空间的作用 b- (block)   c-(control)  g-(globalj)
##相关文章
csswizardry MindBEMding – getting your head ’round BEM syntax [BEM][1] 译文
cssguidelin [cssGuide][2]

[1]:http://www.w3cplus.com/css/mindbemding-getting-your-head-round-bem-syntax.html
[2]:http://cssguidelin.es/