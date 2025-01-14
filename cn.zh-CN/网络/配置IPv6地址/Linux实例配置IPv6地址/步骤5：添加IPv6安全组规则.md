# 步骤5：添加IPv6安全组规则 {#concept_hmt_rbx_wgb .concept}

IPv4 和 IPv6 通信彼此独立，如果当前的安全组规则不能满足业务需求，您需要为 ECS 实例单独配置 IPv6 安全组规则。

## 操作配置 {#section_fvv_z2g_xgb .section}

1.  登录[ECS管理控制台](https://ecs.console.aliyun.com)。
2.  在左侧导航栏，选择**网络与安全** \> **安全组**。
3.  在顶部状态栏处，选择地域。
4.  找到目标安全组，然后单击**配置规则**。
5.  单击**添加安全组规则**。
6.  配置安全组规则。

    其中，授权类型选择**IPv6地址段访问**，然后输入授权的 IPv6 地址段。输入**::/0**则代表授权所有 IPv6 地址。

    安全组规则的配置步骤和常见案例，请参见[添加安全组规则](../cn.zh-CN/安全/安全组/添加安全组规则.md#)和[安全组应用案例](../cn.zh-CN/安全/安全组/安全组应用案例.md#)。


