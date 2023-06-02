# [LitCTF 2023]Ping

## 题目来源 

[[LitCTF 2023]Ping](https://www.nssctf.cn/problem/3873)

## 参考文章

[[LitCTF2023] web方向全题解wp](https://blog.csdn.net/Leaf_initial/article/details/130671885)  
[官方wp](https://dqgom7v7dl.feishu.cn/docx/VyLmdhKDOou5E8xruA7c8bSInKf)

## 思路

### burpsuite

不会用.jpg  
如果没有burp相关的资源可以去官网下然后按照[这个大佬的仓库](https://github.com/h3110w0r1d-y/BurpLoaderKeygen)进行激活  
也不需要浏览器代理插件了,2020.12后的burp都内置了Chrome浏览器(而且ui变好看了不少)  
之前使用浏览器插件的方法还是可以使用,只需要在setting里设置就好了  
总之在proxy下open browser,然后把环境url载入就好了  
先关闭intercept,等全部加载完毕后在启动  
按照题意输入ip地址,尝试输一些无意义的字段会提示必须要是ip,这里可以打开js查看过滤逻辑,总之先输个127.0.0.1(这时候记得打开intercept拦截)  
然后回burp里就可以看到我们发送的数据包是什么样的,关键在于最后一行的command=122.2.2.2&ping=Ping,可以看出来是个直接执行的代码    
右键send to repeater把数据包扔到重发器里,方便查看返回的数据  
尝试修改command的指令进行,比如command=127.1.1.1;ls&ping=PING这样  
会发现返回了不少的数据,修改为ls /后可以看到很多东西,其中就有flag  
使用cat /flag获取flag即可  


### JS hook

参照官方wp复现的  

