---
layout: wiki
title: JS 之奇淫技巧
description: 聪明的你总是能想出一些非常奇妙的方法
date: 2020-02-19
categories: JavaScript
---

* TOC
{:toc}

## Window 相关

### 重新加载页面

1. 刷新当前页

    ```js
    location.reload(force);                 // 重载当前页面，force 为真强制刷新
    location.replace(location.href);        // 访问当前 URL
    history.go(0);                          // 访问最新历史记录
    location = location;                    // 替换 location 对象为本身
    location.assign(location);              // 替换 location 对象为本身
    location.replace(location);             // 替换 location 对象为本身
    ```

2. 上一页并刷新页面

    ```js
    location.replace(document.referrer);    // 替换为前一个页面
    ```

    注：`history.back();` 后跟刷新页面是无效的

3. 定时刷新页面

    ```html
    <meta http-equiv="refresh" content="20">                        <!-- 定时刷新 -->
    <meta http-equiv="refresh" content="20;url=http://www.xxx.net"> <!-- 定时跳转 -->
    ```

    ```js
    function refreshPage() {
        window.location.reload();
    }
    setTimeout('refreshPage()',1000);
    ```