# [LitCTF 2023]导弹迷踪

## 题目来源

[[LitCTF 2023]导弹迷踪](https://www.nssctf.cn/problem/3863)

## 思路

打开环境是个~~操作极其难受的~~火箭小游戏,提示是打到第六关就好了  
真的有人能打过吗  
因为是easy题所以直接在js文件里搜相关代码就好了  
在`src/game.js`下存在通关输出语句 
`text:  function () {if (mLevel === 6) {return 'GOT F|L|A|G {y0u_w1n_th1s_!!!}';} else {return 'CLICK TO CONTINUE';}},`  
提交对应的flag即可  

## 总结

简单题,虽然还蛮好玩的