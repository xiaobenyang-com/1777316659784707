# 临时笔记存储服务 

一个为AI代理提供跨对话临时信息存储与检索的轻量级服务，支持复杂任务分步处理。
A lightweight service that provides cross conversation temporary information storage and retrieval for AI agents, supporting step-by-step processing of complex tasks.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| clear_note | Clears the current note, making it empty. |
| write_note | Replaces the current note with a new string. |
| read_note | Returns the current content of the note. |
| append_note | Appends new text to the current note, starting with a new line. Optionally includes a separator line. |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659784707](https://mcp.xiaobenyang.com/inspector/1777316659784707)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659784707](https://mcp.xiaobenyang.com/inspector/1777316659784707)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "临时笔记存储服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659784707/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "临时笔记存储服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659784707/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "临时笔记存储服务": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659784707",
          },
          "transport": "stdio"
        }
      }
}

```
