# [LitCTF 2023]Follow me and hack me

## 题目来源

[[LitCTF 2023]Follow me and hack me](https://www.nssctf.cn/problem/3864)

## 思路

让初学者知道get和post两者传参的区别    
但是get好像也能传一些body,忘记什么时候看到的  
用hackbar先get到`url/?CTF=Lit2023`  
然后是post传一个`Challenge=i'm_c0m1ng`  
这道题倒是有个彩蛋  

(弱智dirsearch)  
参照官方wp,解出来flag之后会提示备份文件里有好东西  
考点在于网站备份文件泄露,这题比较简单就直接在www.zip下可以找到  
正常是使用dirsearch等网站后台扫描工具去看看有什么可以直接拿到的  
然后陷入了长达半天的dirsearch安装之路

首先py310不知道会报一些奇奇怪怪的错误,按照官网的git clone也是一样的奇怪问题  
总之会报错`no pq wrapper available.`根据提示去下载对应的也是一样的问题  
最后用conda切到3.9的环境直接`pip install dirsearch`就成功了,但是还出现了个typing_extension的错误,把这个包卸了就没事了  
然后在Ubuntu里直接apt-get install也可以  
总之很迷   

用了之后大概就可以扫到一个flag.php和www.zip,访问就可以下载备份文件,打开后可以找到彩蛋的位置  
就是nss上交不了彩蛋,权当知识提升吧  

## 总结

ctf需要的环境好多啊  
Ubuntu下下不了john,windows下一大堆软件用不了(点名dbg),还有各种python和其他软件的环境配置问题  