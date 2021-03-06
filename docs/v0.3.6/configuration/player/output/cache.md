---
title: cache
---

cache
===

### 说明
每次完整的媒体资源解编码结束后，生成缓存文件。下一次将直接命中缓存文件进行资源推流。
因为避免了重复的解编码操作，cpu、内存占用将大幅降低。适用于循环推流的场景。

::: warning 注意
1. 在视频文件并未完整播放结束或中途断开造成缓存未完全生成的情况，二次解析缓存将提示无法命中。只需等待完整播放完视频文件之后有效的缓存即会生成

2. 在对视频输出参数存在修改的情况下，缓存将会立即失效重建

3. 在加载对音视频存在更改的插件情况下，需要手动删除缓存文件(同级目录的cache文件夹中)，否则插件无法生效
:::

### 类型
| 数据类型 | 是否必填 | 默认值 | 可选值 |
|---|---|---|---|
| 布尔 | 否 | false | true false |

### 示例
```yaml {4}
version: "1.0"
player:
  output:
    cache: true
```
