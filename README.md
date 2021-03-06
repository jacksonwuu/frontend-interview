# 前端面试题汇总

汇总一些前端常见的面试题，大多数没有标准答案， 不同的人可能有不同深度的回答。

同时，这些问题也可以用来检验自己的前端技术水平。（很多问题还是挺考验水平的。）

建议不要背答案，而是尽可能地理解背后的原理，这样才能游刃有余。

## HTML

-   DOCTYPE 是什么？

    -   [Document type declaration | Wikipedia](https://en.wikipedia.org/wiki/Document_type_declaration)
    -   [文档类型声明 | MDN](https://developer.mozilla.org/zh-CN/docs/Glossary/Doctype)

-   meta 标签有哪些用处？

-   哪些标签是块级标签/行内标签？

-   有哪些语义化标签？

    -   [HTML Semantic Elements | w3schools](https://www.w3schools.com/html/html5_semantic_elements.asp)

-   什么是 data 属性？

## JS

-   基本数据类型有哪些？

    -   在 JavaScript 中，共有 7 种基本类型：string，number，bigint，boolean，null，undefined，symbol (ECMAScript 2016 新增)。

-   Symbol 是什么？有什么用？有什么特点？

    -   [Symbol | MDN](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Symbol)
    -   [Symbol 类型 |《现代 JavaScript 教程》](https://zh.javascript.info/symbol)

-   箭头函数有什么特点？

    -   [箭头函数，基础知识 |《现代 JavaScript 教程》](https://zh.javascript.info/arrow-functions-basics)

-   Map 和 Object 有什么区别？

-   详细描述一下原型链（是什么？有什么用？有哪些特点？）

-   防抖和节流，以及它们的应用场景？

    -   举个例子：在搜索框里输入时，防抖就是输完过一会儿出现补全提示，节流就是输入的时候隔一段时间出现一次补全提示，两者都是靠定时器来实现的。

-   详细说说 var、let、const 的区别？

    -   var 是全局作用域，let 和 const 是块级作用域，const 不可以被再次赋值。
    -   三者都会进行变量提升，但是 let 和 const 不会在变量提升时进行初始化。

-   this 到底指向谁？请分情况说明。

-   什么是闭包？以及它的使用场景？

    -   [闭包 | MDN](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Closures)
    -   [变量作用域，闭包 | 《现代 JavaScript 教程》](https://zh.javascript.info/closure)
    -   [学习 Javascript 闭包 | 阮一峰](https://www.ruanyifeng.com/blog/2009/08/learning_javascript_closures.html)

-   如何初始化一个元素全是 0 的二维数组？

    -   错误的解法：

        ```js
        let arr = new Array(3).fill(new Array(5).fill(0));
        ```

    -   正确的解法：

        ```js
        let arr;
        for (let i = 0; i < 3; i++) {
            arr[i] = new Array();
            for (let j = 0; j < 5; j++) {
                arr[i][j] = 0;
            }
        }

        or;

        let arr = new Array(3).fill(0).map((item) => new Array(5).fill(0));
        ```

-   如何判断一个 Object 对象是否为空？

    -   解法一：

        ```js
        if (JSON.stringify(obj) === JSON.stringify({})) {
            //obj为空对象
        }
        ```

    -   解法二：

        ```js
        if (
            obj &&
            Object.keys(obj).length === 0 &&
            obj.constructor === Object
        ) {
            //obj为空对象
        }
        ```

-   async 和 await 是什么？

    -   简单来说，它们是基基于 promises 的语法糖，使异步代码更易于编写和阅读。通过使用它们，异步代码看起来更像是老式同步代码。
    -   [async 和 await:让异步编程更简单 | MDN](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Asynchronous/Async_await)

-   如何进行断点调试？

    -   [在 Chrome 中调试](https://zh.javascript.info/debugging-chrome)

-   说说 for...in 和 for..of 的用法

## CSS

-   div 如何垂直水平居中？

    -   绝对定位
    -   flex

-   CSS 选择器的优先级

    -   !important > 内联 > ID 选择器 > 类选择器 > 标签选择器

-   常见布局的实现方式

-   什么是 BFC？

-   如何用 css 实现动画？

    -   两个属性：transition 和 animation

-   如何用 css 画出等腰三角形？

-   什么是回流和重绘？如何触发它们？

-   移动端适配是怎么做的？

    -   viewport 适配
    -   媒体查询 + 弹性布局
    -   rem 适配

-   em、rem 怎么使用？

    -   em 是相对于父元素的字体大小，例如，父元素的字体大小 16px，10em 将等同于 160px。
    -   rem 是相对于根元素字体大小，例如，根元素的字体大小 16px，10rem 将等同于 160px。
    -   [何时使用 Em 与 Rem](https://webdesign.tutsplus.com/zh-hans/tutorials/comprehensive-guide-when-to-use-em-vs-rem--cms-23984)
    -   [CSS 的值与单位 | MDN](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Values_and_units)

-   如何实现亮/暗模式的切换？如何根据设备的模式自动切换亮/暗模式？

    -   利用 CSS 变量和媒体查询 prefers-color-scheme（只有高版本浏览器才支持）

-   getComputedStyle()了解吗？

    -   简单来说就是获取已经应用到元素上的样式清单

## 浏览器

-   说一下浏览器的缓存策略？

-   浏览器有哪些全局变量？

-   详细描述一下事件循环？

-   简述页面的解析和渲染过程？

-   如何在浏览器上开启 UDP 连接？

-   懒加载和预加载分别是什么？如何实现？

-   前端如何实现文件上传功能？

-   浏览器运行环境下的前端如何做优化？

-   从输入网址到看到页面，这之间发生了什么事情？

-   如何处理 CPU 消耗型任务的同时保证页面流畅？

-   Cookie、localStorage、sessionStorage 有什么区别？

-   详细说一下 Cookie？

## React

-   简述 React 的原理？

-   React diff 是怎么样的呢？

-   React 有哪些生命周期函数？

-   React 类组件和函数组件有什么区别？

-   函数组件的生命周期呢？

-   说说 React-Router 的原理？

-   说说 Redux 的原理？

## Vue

-   MVVM 是什么？

## Angular

待补充

## Webpack

-   Webpack 有什么用？

-   说说 Webpack 的原理？

-   Webpack 有哪些配置选项？

-   什么是 loader？有什么用？

-   还接触过哪些打包库？

## Babel

-   Babel 有什么用？

-   说说 Babel 的原理？

-   Babel 有哪些配置选项？

## NodeJS

-   NodeJS 有哪些特点？

-   NodeJS 有什么用？

-   NodeJS 的事件循环是怎么样的？

-   单线程有什么好处？

-   yarn 相比于 npm 有什么改进？

## 微信小程序

-   微信小程序和普通的网页应用有什么不同？

## Typescript

-   用 Typescript 有什么好处？

## 安全

-   跨站和跨域有什么区别？

-   CSRF 是什么，如何防范？

    -   CSRF：跨站请求伪造攻击
    -   CSRF Token 验证
    -   Cookie 的 SameSite 属性
    -   ……

-   XSS 是什么，如何防范？

    -   XSS：跨站脚本攻击
    -   关键在于对输入和输出进行有效的过滤，前后端都要做防范。
    -   Cookie 设置为 HttpOnly
    -   ……

-   SQL 注入是什么，如何防范？

-   什么是 DoS，什么是 DDoS，如何防范？

-   什么是浏览器的同源策略，有什么作用？

-   实现跨域请求的几种方式，优缺点？

-   为什么 HTTPS 是安全的？为什么需要 CA 证书？

-   什么是对称加密，什么是非对称加密？

## 测试

-   前端项目如何编写测试？

## 操作系统

-   线程和进程的区别？

-   什么是死锁？形成条件？如何预防？如何检测？如何恢复？

-   进程间如何通信？

    -   管道, 系统 IPC(消息队列,信号量,共享存储), SOCKET

-   什么是进程同步？如何实现？

-   什么是进程互斥？如何实现？

-   线程同步如何实现？

-   描述一下进程的虚拟地址空间？

-   进程中哪些资源被其线程所共享？

-   操作系统是如何切换进程的？

-   操作系统是如何调度进程的？有哪些调度算法？

-   用户线程和内核线程有什么区别？

-   描述一下虚拟存储的原理？

-   分页和分段有什么区别？

-   中断的处理过程？

-   有哪些页面置换算法？

-   什么是文件系统？有哪些常见的文件系统类型？

## 计算机网络

-   简述 OSI 七层（或 TCP/IP 五层模型）中的每一层以及各自的作用？

    -   七层模型从下往上：物理层、数据链路层、网络层、传输层、会话层、表示层、应用层
    -   五层模型从下往上：物理层、数据链路层、网络层、传输层、应用层

-   GET 和 POST 的区别？

-   为什么说 POST 比 GET 安全？

    -   其实都不安全，只不过 POST 把请求参数隐藏到请求之中了，而 GET 是直接把请求参数放到 URL 里了。真正的安全还得靠 HTTPS 的非对称加密传输。

-   PUT 和 POST 的区别？

    -   技术上来说两者是一样的，只不过 HTTP 协议对两者做了语义上的区分，反映了请求 URL 的 含义的不同。PUT 是幂等操作，POST 不是幂等操作；PUT 指定具体操作对象，POST 可以不具体指定操作对象。
    -   [What's the difference between a POST and a PUT HTTP REQUEST? | Stack Overflow](https://stackoverflow.com/questions/107390/whats-the-difference-between-a-post-and-a-put-http-request)

-   HTTP 常见的认证方式？

-   OAuth 是什么，描述一下 OAuth 认证流程？

-   RESTFUL API 是什么？

-   GraphQL 是什么？优缺点是什么？

-   有哪些应用层协议？有哪些传输层协议？

-   分别说一下 HTTP、UDP、TCP 的报文结构？

-   TCP 建立连接和释放连接的过程？

-   说一下 TCP 的拥塞控制机制？

-   TCP 协议如何保证传输的可靠性?

-   什么是单工、半双工、全双工？

-   断点续传功能的原理？

-   TCP 有什么问题和改进空间？

-   如何提高 UDP 的传输质量？

-   如何建立 TCP/UDP 连接？对 Socket 编程了解吗？

-   Websocket 是什么？

-   如何在浏览器上建立即时通讯服务？

    -   通过使用浏览器的提供的 WebRTC API ，来建立点对点的网络连接，实现视频流和音频流或者其他任意数据的传输。
    -   [WebRTC API | MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/WebRTC_API)
    -   [WebRTC | High Performance Browser Networking](https://hpbn.co/webrtc/)

-   CDN 是什么？你对它有多了解？

-   了解 IPv4 协议吗？IPv6 呢？

## 编译原理

-   简述编译器的工作流程？

-   什么是 AST?

-   简述 Babel 的工作原理？

## 算法

不管前端还是后端，只要你是一个有技术追求的程序员，算法一定是要不断精进的。

算法部分强烈建议去 leetcode 上刷一遍《剑指 Offer》，把每一道题涉及的数据结构和算法思想都吃透。

-   什么是复杂度，什么是大 O 表示法？

-   冒泡排序、快速排序、归并排序

-   如何先序、中序、后序、层序遍历一棵树？

-   递归遍历和非递归遍历一棵树？

-   栈和队列的区别，以及它们在 JS 中的实现？

-   如何用 JS 实现并查集？

-   如何用 JS 实现二叉树？

-   如何用动态规划解决爬楼梯问题？

-   如何实现深度遍历和广度遍历？

-   什么是堆，什么是堆排序？

-   二分查找法的复杂度？

## 手写代码

-   实现 Promise、Promise.all、Promise.race

-   实现一个 EventEmitter

-   实现一个 Singleton

-   实现 Array 的自带函数（map、reduce、some、any、every……）

-   实现 call、apply、bind

-   实现 new

-   实现 instanceof

-   实现 JSON.stringify 和 JSON.parse

-   实现深拷贝

-   实现一个柯里化函数

-   实现一个数组扁平化函数

## Git

-   常用的 git 命令

-   什么是 fast-forward？

-   什么是裸库，什么是非裸库？

-   如何管理一个 Git 仓库？

## 待分类

-   怎么追踪用户页面情况？

-   创建一个前端项目的步骤？

-   什么是 Web 安全色？

-   为什么要使用 Sass 或 Less？

-   使用过 ESLint 吗？

-   使用过 Prettier 吗？

-   使用过 Electron 吗？

-   使用过 Express、EggJS 和 Sails 和吗？

-   package-lock 文件是干嘛用的？

-   平时如何学习编程知识的？

-   有文字总结的习惯吗？

-   前端的前沿了解多少？

-   了解 WebAssembly 吗?

## 资源推荐

-   [MDN](https://developer.mozilla.org/zh-CN/)

-   [《现代 JavaScript 教程》](https://zh.javascript.info/)
