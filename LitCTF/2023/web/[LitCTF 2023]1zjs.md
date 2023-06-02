# [LitCTF 2023]1zjs

## 题目来源 

[[LitCTF 2023]1zjs](https://www.nssctf.cn/problem/3871)

## 思路

拧魔方小游戏  
~~赛场上坐牢就直接开始玩~~  
什么都不懂,但题目说是1z的js就打开源代码看看了  
页面使用了`./dist/index.umd.js`这个js文件,转到js里查看  
在一开始的注释里有条特别的提示信息`PERFORMANCE OF THIS SOFTWARE.Your gift just take it : /f@k3f1ag.php`  
访问后页面是一大片的`+(![]`,猜测是jsfuck  
扔到控制台里回车得到flag


## 总结

不造,感谢出题人把hint放在很前面不是对着5w行硬找