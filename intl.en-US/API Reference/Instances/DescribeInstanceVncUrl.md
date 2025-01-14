# DescribeInstanceVncUrl {#doc_api_1161580 .reference}

You can call this operation to query the Web management terminal URL of an ECS instance.

## Description {#description .section}

When you call this operation, note that:

-   A management terminal URL is only valid for 15 seconds. If a connection is not established within 15 seconds after a successful query, the URL expires and you must query it again.
-   The **KeepAlive** time of a management terminal connection is 60 seconds. If the user does not interact with the management terminal within 60 seconds, the management terminal will be automatically disconnected.
-   When the management terminal is disconnected, you can only reconnect to the management terminal up to 30 times a minute.
-   At the end of [https://g.alicdn.com/aliyun/ecs-console-vnc2/0.0.3/index.html](https://g.alicdn.com/aliyun/ecs-console-vnc2/0.0.3/index.html), add `vncUrl=xxxx`, `instanceId=xxx`, `isWindows=True`, `isWindows=False`, and`password=XXXXXX`. Connect these parameters with `&`. Where:
    -   `vncUrl`: The value of `vncUrl` is returned after a successful query.
    -   `instanceId`: the ID of instance.
    -   `isWindows`: indicates whether the operating system of the instance is Windows. The value of `true` indicates the Windows system. The value of `false` indicates that it is not the Windows system.
    -   `password`: Optional. The password to establish a remote connection from an instance. It must be 6 characters in length and can contain digits and uppercase and lowercase letters. You can use this parameter to eliminate the need to enter your password when the connection is being established.

        Example:

        ``` {#codeblock_xfj_8oh_hzj}
        
                https://g.alicdn.com/aliyun/ecs-console-vnc/0.0.7/index.html?vncUrl=ws%3A%2F%xxx&instanceId=i-wz9hhwq5a6tmxxxxxxx&isWindows=true 
                
        ```

        or

        ``` {#codeblock_p91_0kc_f1b}
        
                https://g.alicdn.com/aliyun/ecs-console-vnc/0.0.7/index.html?vncUrl=ws%3A%2F%xxx&instanceId=i-wz9hhwq5a6tmxxxxxxx&isWindows=true&password=111111 
                
        ```


## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Ecs&api=DescribeInstanceVncUrl) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Name|Type|Required|Example|Description|
|----|----|--------|-------|-----------|
|InstanceId|String|Yes|i-AY121018033933eaxxxxxxx| The ID of the instance.

 |
|RegionId|String|Yes|cn-hangzhou| The region ID of the instance. You can call the [DescribeRegions](~~25609~~) operation to view the latest region list.

 |
|Action|String|No|DescribeInstanceVncUrl| The operation that you want to perform. Set the value to DescribeInstanceVncUrl.

 |
|OwnerAccount|String|No|ECSforCloud@Alibaba.com| The logon name of the RAM user.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example|Description|
|----|----|-------|-----------|
|RequestId|String|473469C7-AA6F-4DC5-B3DB-A3DC0DE3C83E| The request ID. The system returns a unique RequestId for each API request, regardless of whether the API operation is successful.

 |
|VncUrl|String|ws%3A%2F%2Fhz01-vncproxy.aliyun.com%2Fwebsockify%2F%3Fs%3DDvh%252FIA%252BYc73gWO48cBx2gBxUDVzaAnSKr74pq30mzqUYgeUMcB%252FbkNixDxdEA996| The management terminal URL.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

https://ecs.aliyuncs.com/?Action=DescribeInstanceVncUrl
&InstanceId=i-AY121018033933eaxxxxxxx
&RegionId=cn-hangzhou 
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeInstanceVncUrlResponse>
  <RequestId>1450F2D7-5435-4420-BBC9-49C5xxxxxxxx</RequestId>
  <VncUrl>ws%3A%2F%2Fhz01-vncproxy.aliyun.com%2Fwebsockify%2F%3Fs%3DDvh%252FIA%252BYc73gWO48cBx2gBxUDVzaAnSKr74pq30mzqUYgeUMcB%252FbkNixDxdEA996</VncUrl>
</DescribeInstanceVncUrlResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"VncUrl":"ws%3A%2F%2Fhz01-vncproxy.aliyun.com%2Fwebsockify%2F%3Fs%3DDvh%252FIA%252BYc73gWO48cBx2gBxUDVzaAnSKr74pq30mzqUYgeUMcB%252FbkNixDxdEA996",
	"RequestId":"1450F2D7-5435-4420-BBC9-49C514B0157E"
}
```

## Error codes {#section_owt_6xw_a3a .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|IncorrectInstanceStatus|The current status of the resource does not support this operation.|The error message returned when the operation is not supported while the resource is in the current state.|

[View error codes](https://error-center.aliyun.com/status/product/Ecs)

