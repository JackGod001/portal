---
title: 响应参数
sidebar_label: 响应参数
slug: /docs/tutorials/http/server/response-body
---

## 概述

在 go-zero 中，支持通过 `http.ResponseWriter` 的 `Write` 方法来返回响应参数，同时支持通过 `http.ResponseWriter` 的 `Header` 方法来返回响应头，其默认支持 `application/json` 格式，对于其他响应格式，可参考
<https://github.com/zeromicro/x/blob/main/http/responses.go> , 目前 <a href="https://github.com/zeromicro/x" target="_blank">zeromicro/x</a> 实现了 xml 的扩展。

## 示例

### Json 响应参数

```go
type Response struct {
 Name   string `json:"name"`
 Age    int    `json:"age"`
}

resp := &Response{Name: "jack", Age: 18}
httpx.OkJson(w, resp)
```
