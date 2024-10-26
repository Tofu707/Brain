# 准备
读完了菜鸟教程和 w3school 的 PHP 基础手册。
因为写过一些简单的爬虫，所以没去看 python 了。
# 过程
## Wp
```php
<?php   highlight_file(__FILE__);   if(isset($_GET['syc'])&&isset($_POST['lover'])){    $syc=$_GET['syc'];    $lover=$_POST['lover'];       if($syc=="lover"&&$lover=="syc"){           echo "congratulate!!!you have finished the first level"."<br>";           if(isset($_COOKIE['GiveMe'])&&isset($_REQUEST['flag'])){            $cookie=$_COOKIE['GiveMe'];            $flag=$_REQUEST['flag'];               if($cookie=="GiveMe"&&$flag==$cookie){                   echo file_get_contents('/flag');               }           }       }   }
```
给了这个 php。
其实就是要求构造 url 后面传参 syc=lover，post 传参 lover=syc，Cookie 设置一个 GiveMe=GiveMe，在 url（get）或者 post 里面传参 flag=GiveMe。用 hackbar 很方便解决。
SYC{Y0u_Ar3_the_P0st_And_G3t_Master}
# 其他
Php 的漏洞了解的不是很多，毕竟刚刚才读完的几个教程。
就教程里面的描述，在配置不安全的情况下肯定是可以通过构建 payload 欺骗服务器进行一些不应该的操作，例如在 url 后面传参，使得 php 相关参数后面接上不用户输入的 JS（XSS 攻击），或者差不多的原理应该也可以进行远程代码执行、sql 注入什么的。新手管理员应该会很容易犯类似的配置错误。
