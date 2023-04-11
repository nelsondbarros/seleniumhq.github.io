---
title: "安装浏览器驱动"
linkTitle: "安装驱动"
weight: 4
description: >
  设置您的浏览器用于自动化.
aliases: [
"/documentation/zh-cn/selenium_installation/installing_webdriver_binaries/",
"/documentation/zh-cn/webdriver/driver_requirements/",
"/zh-cn/documentation/getting_started/installing_browser_drivers/"
]
---

通过WebDriver, 
Selenium支持市场上所有主要浏览器, 
如Chrome、Firefox、Internet Explorer、Edge和Safari. 
WebDriver尽量使用浏览器内置的自动化支持
来驱动浏览器.

由于除Internet Explorer之外的所有驱动程序实现
都是由浏览器供应商自己提供的, 
因此标准Selenium发行版中不包括这些驱动程序. 
本节介绍了使用不同浏览器的基本要求.

在我们的[驱动程序配置]({{< ref "/documentation/webdriver/drivers/" >}}) 文档中
阅读有关启动驱动程序的更多高级选项.

{{% pageinfo color="warning" %}}
<p class="lead">
   <i class="fas fa-language display-4"></i> 
   Page being translated from English to Chinese. 
   Do you speak Chinese? Help us to translate
   it by sending us pull requests!
</p>
{{% /pageinfo %}}

## 四种使用驱动的方法

### 1. Selenium Manager <small>(Beta)</small>

{{< badge-version version="4.6" >}}

Selenium Manager可以帮助你获得一个运行Selenium的开箱即用的环境。
如果在`PATH`中没有找到Chrome、Firefox和Edge的驱动，Selenium Manager的Beta 1版将为它们配置。
不需要额外的配置。如果有必要，Selenium Manager的未来版本也会在必要时一同下载浏览器。

在这篇[公告](/blog/2022/introducing-selenium-manager/)中了解更多有关 Selenium Manager 的信息。

### 2. 驱动管理软件

大多数机器会自动更新浏览器, 
但不会自动更新驱动程序. 
为了确保为浏览器提供正确的驱动程序, 
这里有许多第三方库可为您提供帮助.

{{< tabpane text=true langEqualsHeader=true >}}
{{% tab header="Java" %}}
**注意：** 这个软件包目前不能用于IEDriverServer v4以上的版本。

1. 导入 [WebDriverManager](https://github.com/bonigarcia/webdrivermanager)
```java
import io.github.bonigarcia.wdm.WebDriverManager;
```
2. 调用 `setup()`:

{{< gh-codeblock path="examples/java/src/test/java/dev/selenium/getting_started/InstallDriversTest.java#L17-L19" >}}

{{% /tab %}}
{{% tab header="Python" %}}

1. 导入 [WebDriver Manager for Python](https://github.com/SergeyPirogov/webdriver_manager)

```py
from webdriver_manager.chrome import ChromeDriverManager
```

2. 使用 `install()` 获取管理器使用的位置, 并将其传递到服务类中

{{< gh-codeblock path="examples/python/tests/getting_started/test_install_drivers.py#L15-L17" >}}

{{% /tab %}}
{{% tab header="CSharp" %}}
1. 导入 [WebDriver Manager Package](https://github.com/rosolko/WebDriverManager.Net)

```csharp
using WebDriverManager;
using WebDriverManager.DriverConfigs.Impl;
```

2. 使用 `SetUpDriver()` 时需要一个配置类:

{{< gh-codeblock path="examples/dotnet/SeleniumDocs/GettingStarted/InstallDriversTest.cs#L19-L21" >}}

{{% /tab %}}
{{% tab header="Ruby" %}}
1. 增加 [webdrivers gem](https://github.com/titusfortner/webdrivers) 到 Gemfile:

```rb
gem 'webdrivers', '~> 5.0'
```

2. 在程序中Require webdrivers:
```rb
require 'webdrivers'
```

3. 像往常一样初始化驱动程序:
```rb
driver = Selenium::WebDriver.for :chrome
```

<div class="github">
    <a href ="https://github.com/SeleniumHQ/seleniumhq.github.io/blob/dev/examples/ruby/spec/getting_started/install_drivers_spec.rb">
查看GitHub上的完整示例.</a>
</div>

{{% /tab %}}
{{% tab header="JavaScript" %}}
 *暂时还没有推荐的JavaScript驱动管理器*
{{% /tab %}}
{{% tab header="Kotlin" %}}

1. 导入 [WebDriver Manager](https://github.com/bonigarcia/webdrivermanager)
```java
import io.github.bonigarcia.wdm.WebDriverManager;
```
2. 在初始化驱动程序之前调用setup方法:

{{< gh-codeblock path="examples/kotlin/src/test/kotlin/dev/selenium/getting_started/InstallDriversTest.kt#L17-L18" >}}

{{% /tab %}}
{{< /tabpane >}}

### 3. `PATH` 环境变量
此选项首先需要手动下载驱动程序
(有关链接, 请参阅[快速参考](#快速参考) 部分).

这是一个灵活的选项, 
可以在不更新代码的情况下更改驱动程序的位置, 
并且可以在多台机器上工作, 
而不需要每台机器将驱动程序放在同一位置. 

您可以将驱动程序放置在路径中已列出的目录中, 
也可以将其放置在目录中并将其添加到`PATH`.

* 要查看`PATH`上已有哪些目录, 
请打开命令提示符/终端并键入:  

{{< tabpane text=true persistLang=false >}}
{{% tab header="Bash" %}}

要查看`PATH`上已经有哪些目录, 请打开Terminal并执行
```shell
echo $PATH
```
如果驱动程序的位置不在列出的目录中, 
可以将新目录添加到PATH:
```shell
echo 'export PATH=$PATH:/path/to/driver' >> ~/.bash_profile
source ~/.bash_profile
```
您可以通过启动驱动程序来测试其是否被正确添加:
```shell
chromedriver
```
{{% /tab %}}
{{% tab header="Zsh" %}}
要查看`PATH`上已经有哪些目录, 请打开Terminal并执行:
```shell
echo $PATH
```
如果驱动程序的位置不在列出的目录中, 
可以将新目录添加到PATH:
```shell
echo 'export PATH=$PATH:/path/to/driver' >> ~/.zshenv
source ~/.zshenv
```
您可以通过启动驱动程序来测试其是否被正确添加:
```shell
chromedriver
```
{{% /tab %}}
{{% tab header="Windows" %}}

要查看`PATH`上已经有哪些目录, 请打开命令提示符并执行:
```shell
echo %PATH%
```
如果驱动程序的位置不在列出的目录中, 
可以将新目录添加到PATH:
```shell
setx PATH "%PATH%;C:\WebDriver\bin"
```
您可以通过启动驱动程序来测试其是否被正确添加:
```shell
chromedriver.exe
```
{{% /tab %}}
{{< /tabpane >}}

如果`PATH`配置正确, 
  您将看到一些与驱动程序启动相关的输出: 

```
Starting ChromeDriver 95.0.4638.54 (d31a821ec901f68d0d34ccdbaea45b4c86ce543e-refs/branch-heads/4638@{#871}) on port 9515
Only local connections are allowed.
Please see https://chromedriver.chromium.org/security-considerations for suggestions on keeping ChromeDriver safe.
ChromeDriver was started successfully.
```

想要重新控制命令提示符可以按下 <kbd>Ctrl+C</kbd>

### 4. 硬编码位置

与上面的选项3类似, 
您需要手动下载驱动程序(有关链接, 请参阅[快速参考](#快速参考) 部分). 
在代码中指定位置本身的优点是
不需要指出系统上的环境变量, 
但缺点是使代码的灵活性大大降低. 

{{< tabpane langEqualsHeader=true >}}

{{< tab header="Java" >}}

System.setProperty("webdriver.chrome.driver","/path/to/chromedriver");
ChromeDriver driver = new ChromeDriver();

{{< /tab >}}

{{< tab header="Python" >}}

from selenium import webdriver
from selenium.webdriver.chrome.service import Service

service = Service(executable_path="/path/to/chromedriver")
driver = webdriver.Chrome(service=service)

{{< /tab >}}

{{< tab header="CSharp" >}}

var driver = new ChromeDriver(@"C:\WebDriver\bin");

{{< /tab >}}

{{< tab header="Ruby" >}}

service = Selenium::WebDriver::Service.chrome(path: '/path/to/chromedriver')
driver = Selenium::WebDriver.for :chrome, service: service

{{< /tab >}}

{{< tab header="JavaScript" >}}
const {Builder} = require('selenium-webdriver');
const chrome = require('selenium-webdriver/chrome');

const service = new chrome.ServiceBuilder('/path/to/chromedriver');
const driver = new Builder().forBrowser('chrome').setChromeService(service).build();
{{< /tab >}}

{{< tab header="Kotlin" >}}

import org.openqa.selenium.chrome.ChromeDriver

fun main(args: Array<String>) {
    System.setProperty("webdriver.chrome.driver", "/path/to/chromedriver")
    val driver = ChromeDriver()
}

{{< /tab >}}

{{< /tabpane >}}

## 快速参考

| 浏览器               | 支持的操作系统                     | 维护者              | 下载                                                                    | 问题追溯                                                             |
|-------------------|-----------------------------|------------------|-----------------------------------------------------------------------|------------------------------------------------------------------|
| Chromium/Chrome   | Windows/macOS/Linux         | Google           | [下载](//chromedriver.chromium.org/downloads)                | [Issues](//bugs.chromium.org/p/chromedriver/issues/list)         |
| Firefox           | Windows/macOS/Linux         | Mozilla          | [下载](//github.com/mozilla/geckodriver/releases)                       | [Issues](//github.com/mozilla/geckodriver/issues)                |
| Edge              | Windows/macOS/Linux         | Microsoft        | [下载](//developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/) | [Issues](https://github.com/MicrosoftDocs/edge-developer/issues) |
| Internet Explorer | Windows                     | Selenium Project | [下载](/downloads)                                                      | [Issues](//github.com/SeleniumHQ/selenium/labels/D-IE)           |
| Safari            | macOS High Sierra and newer | Apple            | 内置                                                                    | [Issues](//bugreport.apple.com/logon)                            |

备注：Opera驱动不再适用于Selenium的最新功能，目前官方不支持。


## 下一步
[创建你的第一个Selenium脚本]({{< ref "first_script.md" >}})
