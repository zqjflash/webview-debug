### webview-debug

> 移动端webview页面调试

### 微信开发者工具支持X5内核

> 移动开发者在微信webview上调试页面一直是件非常蛋疼的事情，简直是盲人捉象，业界没有一款能够满足可视化、可编辑、可断点的综合调试能力

### 目前业界常用的一些移动调试方法

* chrome模拟器
* weinre
* fiddler
* safari

### 来看下这几个调试方法的优劣：

<table cellpadding="0" cellspacing="0">
    <thead><tr><td>方法</td><td>优点</td><td>缺点</td></tr></thead>
    <tbody>
      <tr><td>chrome模拟器</td><td>可视化、可编辑、可断点</td><td>非真机，与实际场景误差比较大</td></tr>
      <tr><td>weinre</td><td>跨平台</td><td>无法调试js，且需额外引入调试js</td></tr>
      <tr><td>fiddler</td><td>远程代理到本地调试</td><td>没有断点、可视化</td></tr>
      <tr><td>safari</td><td>调试ios上的app包裹的浏览器</td><td>不支持跨平台</td></tr>
    </tbody>
</table>

__我们的业务开发通常在QB、微信、手Q场景，以上几种调试都难以满足快速迭代调试，排查问题也很费劲__

### 在过去半年里，我们X5内核经过不断的迭代，逐步探索出一套适合我们业务前端开发的一套调试工具（x5 inspect），x5 inspect彻底解决在QB、微信、手Q场景的真机远程调试，做到可视化编辑、可断点、可打log的完整闭环调试

### 这期间经历了三个阶段：

* 第一阶段：命令模式阶段，需要运行脚本，手工安装调试内核；
* 第二阶段：半自动化阶段，按步骤执行操作流程即可安装一套调试工具；
* 第三阶段：内核集成调试工具，开启开关即可使用。

### 接下来重点阐述第三阶段的调试方案

* 下载tbs2.0调试包并解压得到apk（http://res.imtt.qq.com/tbs_inspect/tbs_2.0_inspector_beta.zip），放在手机sdcard/tbs/com.tencent.mm目录下，打开微信访问debugtbs.qq.com，先点击“清除TBS内核”，再点击“安装本地TBS内核”即可；（blink版本全量上线以后此步骤省略）

* 微信访问一个页面，手机USB连接电脑，打开chrome浏览器，输入chrome://inspect即可

* 微信访问页面如下图：

    ![Alt text](https://raw.githubusercontent.com/zqjflash/webview-debug/master/wx-page.png)

* pc chrome浏览器访问chrome://inspect如下图：

    ![Alt text](https://raw.githubusercontent.com/zqjflash/webview-debug/master/chrome-inspect.png)

* 点击inspect按钮访问效果如下图：

    ![Alt text](https://raw.githubusercontent.com/zqjflash/webview-debug/master/developer-tools.png)

