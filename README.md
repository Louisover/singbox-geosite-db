# 简介

更好用的可自定义 geosite，适用于 singbox

## 自定义 geosite

放在 geosite-custom 目录下

## 自定义规则文件

### custom-direct.txt

- 想要加入的直连列表
- 格式和 geosite 相同

### custom-direct-remove.txt

- 想删除的直连列表
- 支持类型
  - `all`
  - `clear` 
  - `domain` 
  - `full` 
  - `regexp` 
  - `keyword`
- `all` 和 `clear` 会以关键词匹配删除，区别在于 `all` 会匹配所有规则，`clear` 仅匹配域名
  - `all:google.com` 会删除 `xxx.google.com` `full:xxx.google.com`
  - `clear:.google.com` 会删除 `a.google.com` `a.b.google.com`
  - `clear:google.com` 会删除 `google.com` `agoogle.com` `xxx.google.com`
- `domain` 会删除对应的域名
  - `domain:google.com` 仅会删除 `google.com`
- `full` `regexp` `keyword` 会删除对应的 `geosite` 规则
  - `full:nmsl.google.com` 会删除 `full:nmsl.google.com`
- 被删除的域名在 geosite-custom/switch-direct 找到
