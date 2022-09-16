---
title: Kotlin易忘知识补充
date: 2022-09-16 15:10:02
tags: [Kotlin]
---
<br/>

1. Kotlin泛型类型直接在代码中使用:使用关键字***reified***,且放到**inline**方法当中

    ```
    inline fun <reified T> getType(value: T) {
        println("$value 的类型是 ${T::class.java}")
    }
    ```
<!--more-->

2. 尾递归优化:使用关键字***tailrec***
    ```
    tailrec fun cumsum(n:Int, res:Long = 0) : Long  = 
        if (n == 1) 
              n + res 
          else  
              cumsum(n - 1, n + res)

    ```