# DescribeDisks {#doc_api_1032129 .reference}

查询您已经创建的磁盘。

## 接口说明 {#description .section}

-   请求参数RegionId、ZoneId、DiskIds和InstanceId等都是过滤器的概念，参数间是逻辑与（AND）关系。
-   请求参数DiskIds是一个JSON格式的数组（Array），如果参数为空，则过滤器不起作用，但是DiskIds如果是一个空数组，则视为该过滤器有效，且返回空。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Ecs&api=DescribeDisks)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-hangzhou|磁盘所属于的地域ID。您可以调用[DescribeRegions](~~25609~~)查看最新的阿里云地域列表。

 |
|Action|String|否|DescribeDisks|系统规定参数。取值：DescribeDisks

 |
|AdditionalAttributes.N|RepeatList|否|null|其他属性值。

 **说明：** 该参数即将被弃用，为提高兼容性，请尽量使用其他参数。

 |
|AutoSnapshotPolicyId|String|否|auto\_20140724\_2|根据自动快照策略 ID 查询磁盘。

 |
|Category|String|否|all|磁盘种类。取值范围：

 -   all：所有磁盘
-   cloud：普通云盘
-   cloud\_efficiency：高效云盘
-   cloud\_ssd：SSD盘
-   local\_ssd\_pro：I/O密集型本地盘
-   local\_hdd\_pro：吞吐密集型本地盘
-   ephemeral：本地磁盘
-   ephemeral\_ssd：本地SSD盘
-   cloud\_essd：ESSD云盘。目前ESSD云盘正在火热公测中，仅部分地域下的可用区可以选购。更多详情，请参阅 [ESSD云盘FAQ](~~64950~~)。

 默认值：all

 |
|DeleteAutoSnapshot|Boolean|否|false|删除磁盘时，是否同时删除自动快照。取值范围：

 -   true：同时删除自动快照
-   false：保留自动快照

 默认值：false

 |
|DeleteWithInstance|Boolean|否|false|磁盘是否随实例释放。取值范围：

 -   true：实例释放时，这块磁盘随实例一起释放
-   false：实例释放时，这块磁盘保留不释放

 默认值：false

 |
|DiskChargeType|String|否|PostPai|磁盘的计费方式。取值范围：

 -   PrePaid：包年包月
-   PostPaid：按量付费

 |
|DiskIds|String|否|\["d-xxxxxxxxx", "d-yyyyyyyyy", … "d-zzzzzzzzz"\]|磁盘ID。一个带有格式的JSON数组，最多100个ID，用半角逗号（,）隔开。

 |
|DiskName|String|否|JoshuaFinance|磁盘名称。

 |
|DiskType|String|否|all|要查询的磁盘类型。取值范围：

 -   all：同时查询系统盘与数据盘
-   system：只查询系统盘
-   data：只查询数据盘

 默认值：all

 |
|DryRun|Boolean|否|false|是否只预检此次请求。

 -   true：发送检查请求，不会查询资源状况。检查项包括AccessKey是否有效、RAM用户的授权情况和是否填写了必需参数。如果检查不通过，则返回对应错误。如果检查通过，会返回错误码`DryRunOperation`。
-   false：发送正常请求，通过检查后返回2XX HTTP状态码并直接查询资源状况。

 默认值：false

 |
|EnableAutoSnapshot|Boolean|否|false|磁盘是否执行自动快照策略（前提是用户整体的自动快照策略已经开启）。取值范围：

 -   true：表示这块磁盘执行自动快照策略
-   false：表示这块磁盘不执行自动快照策略

 默认值：false

 |
|EnableAutomatedSnapshotPolicy|Boolean|否|false|磁盘设置了自动快照策略。

 **说明：** 该参数即将被弃用，为提高兼容性，请尽量使用其他参数。

 |
|EnableShared|Boolean|否|false|磁盘是否是共享块存储。

 |
|Encrypted|Boolean|否|false|是否过滤加密磁盘。取值范围：

 -   true：只筛选出加密磁盘
-   false：不做加密属性的筛选

 默认值：false

 |
|Filter.1.Key|String|否|CreationStartTime|查询资源时的筛选键。取值必须为 CreationStartTime。

 **说明：** 该参数即将被弃用，为提高兼容性，请尽量使用其他参数。

 |
|Filter.1.Value|String|否|2017-12-05T22:40:00Z|查询资源时的筛选值。取值必须为资源创建的开始时间点（CreationStartTime）。

 **说明：** 该参数即将被弃用，为提高兼容性，请尽量使用其他参数。

 |
|Filter.2.Key|String|否|CreationEndTime|查询资源时的筛选键。取值必须为 CreationEndTime。

 **说明：** 该参数即将被弃用，为提高兼容性，请尽量使用其他参数。

 |
|Filter.2.Value|String|否|2017-12-06T22:40:00Z|查询资源时的筛选值。取值必须为资源创建的结束时间点（CreationEndTime）。

 **说明：** 该参数即将被弃用，为提高兼容性，请尽量使用其他参数。

 |
|InstanceId|String|否|i-instance1|实例ID。

 |
|KMSKeyId|String|否|0e478b7a-4262-4802-b8cb-00d3fb40826X|磁盘使用的KMS密钥ID。

 |
|LockReason|String|否|recycling|磁盘被锁定的原因。取值范围：

 -   financial：因欠费被锁定
-   security：因安全原因被锁定
-   recycling：抢占式实例的待释放锁定状态
-   dedicatedhostfinancial：因为专有宿主机欠费导致 ECS 实例被锁定

 |
|OwnerAccount|String|否|ECSforCloud@Alibaba.com|RAM 用户的账号登录名称。

 |
|PageNumber|Integer|否|1|磁盘状态列表的页码，起始值：1

 默认值：1

 |
|PageSize|Integer|否|10|分页查询时设置的每页行数，最大值：100

 默认值：10

 |
|Portable|Boolean|否|true|要查询的磁盘是否支持卸载，该属性为不可修改属性。取值范围：

 -   true：可卸载磁盘，可以独立存在且可以自由在可用区内挂载和卸载
-   false：不可卸载磁盘，不可以独立存在且不可以自由在可用区内挂载和卸载

 这个属性为`true`的磁盘才能挂载和卸载，其中：

 -   本地盘
-   本地SSD盘
-   普通云盘、高效云盘、ESSD盘和SSD盘的系统盘
-   包年包月的普通云盘、高效云盘、ESSD盘和SSD盘

 该属性都为`false`。

 |
|ResourceGroupId|String|否|rg-resourcegroupid1|磁盘所在的企业资源组 ID。

 |
|SnapshotId|String|否|s-snaoshotid1|创建磁盘使用的快照。

 |
|Status|String|否|all|磁盘状态，参考文档[普通云盘状态](~~25689~~)。取值范围：

 -   In\_use
-   Available
-   Attaching
-   Detaching
-   Creating
-   ReIniting
-   All

 默认值：All

 |
|Tag.N.Key|String|否|FinanceJoshua|磁盘的标签键。

 |
|Tag.N.Value|String|否|FinanceDept|磁盘的标签值。

 |
|Tag.N.key|String|否|FinanceJoshua|磁盘的标签键。

 **说明：** 该参数即将被弃用，为提高兼容性，请尽量使用 Tag.N.Key。

 |
|Tag.N.value|String|否|FinanceDept|磁盘的标签值。

 **说明：** 该参数即将被弃用，为提高兼容性，请尽量使用 Tag.N.Value。

 |
|ZoneId|String|否|cn-hangzhou-g|可用区ID。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Disks| | |磁盘信息组成的集合

 |
|└AttachedTime|String|2018-01-01T01:04:22Z|卸载时间。按照 ISO8601 标准表示，并需要使用 UTC 时间。格式为：YYYY-MM-DDThh:mmZ只有在Status 为 Available 时才有意义。

 |
|└AutoSnapshotPolicyId|String|s-23f2i9s4t|磁盘采用的自动快照策略 ID。

 |
|└Category|String|cloud\_ssd|磁盘种类。取值范围：

 -   cloud：普通云盘
-   cloud\_efficiency：高效云盘
-   cloud\_ssd：SSD 云盘
-   ephemeral\_ssd：本地 SSD 盘
-   ephemeral: 本地磁盘
-   cloud\_essd：ESSD 云盘。目前 ESSD 云盘正在火热公测中，仅部分地域下的可用区可以选购。更多详情，请参阅 [ESSD 云盘 FAQ](~~64950~~)。

 |
|└CreationTime|String|2018-01-01T01:01:22Z|创建时间。

 |
|└DeleteAutoSnapshot|Boolean|false|是否同时删除自动快照。取值范围：

 -   true：删除磁盘上的快照。
-   false：保留磁盘上的快照。

 通过 [CreateSnapshot](~~25524~~) 或者在控制台创建的快照，不受这个参数的影响，会始终保留。

 |
|└DeleteWithInstance|Boolean|true|是否随实例释放。取值范围：

 -   true：释放实例时，这块磁盘随实例一起释放。
-   false：释放实例时，这块磁盘保留不释放。

 |
|└Description|String|FinanceDept|磁盘描述。

 |
|└DetachedTime|String|2018-01-08T01:01:22Z|卸载时间。只有在Status 为 Available 时才有意义。

 |
|└Device|String|/dev/xvdb|磁盘挂载的实例的设备名，例如 /dev/xvdb。只有在 Status 为 In\_use 时才有值，其他状态为空。

 **说明：** 该参数正在内测调整中，尚未正式上线，暂时不建议使用，请您耐心等待。

 |
|└DiskChargeType|String|PostPaid|磁盘的付费方式。取值范围：

 -   PrePaid：预付费，即包年包月。
-   PostPaid：后付费，即按量付费。

 |
|└DiskId|String|d-23jbf2v5m|磁盘 ID。

 |
|└DiskName|String|FinanceDeptJoshua|磁盘名。

 |
|└EnableAutoSnapshot|Boolean|false|磁盘是否执行自动快照策略。取值范围：

 -   true：这块磁盘执行自动快照策略。
-   false：这块磁盘不执行自动快照策略。

 默认值：false

 |
|└EnableAutomatedSnapshotPolicy|Boolean|false|磁盘是否执行自动快照策略。

 **说明：** 该参数即将被弃用，为提高兼容性，请尽量使用其他参数。

 |
|└Encrypted|Boolean|false|是否为加密磁盘

 |
|└ExpiredTime|String|2018-01-10T01:01:22Z|包年包月磁盘的过期时间。

 |
|└IOPS|Integer|4000|每秒读写（I/O）操作的次数，单位：次/s。

 |
|└IOPSRead|Integer|2000|每秒读操作的次数，单位：次/s。

 |
|└IOPSWrite|Integer|2000|每秒写操作的次数，单位：次/s。

 |
|└ImageId|String|m-bp13aqm171qynt3udgd|创建磁盘的镜像 ID，只有通过镜像创建的磁盘才有值，否则为空。这个值在磁盘的生命周期内始终不变。

 |
|└InstanceId|String|i-instanceid1|磁盘挂载的实例 ID。只有在 Status 为 In\_use 时才有值，其他状态为空。

 |
|└KMSKeyId|String|0e478b7a-4262-4802-b8cb-00d3fb40826X|磁盘使用的KMS密钥ID

 |
|└MountInstanceNum|Integer|1|共享存储挂载的实例数量。

 |
|└MountInstances| | |挂载到实例上的信息集合。

 |
|└AttachedTime|String|2017-12-05T2340:00Z|挂载时间。按照[ISO8601](~~25696~~)标准表示，并需要使用UTC时间，格式为yyyy-MM-ddTHH:mm:ssZ。

 |
|└Device|String|/dev/xvda|磁盘的挂载点。

 **说明：** 该参数正在内测调整中，尚未正式上线，暂时不建议使用，请您耐心等待。

 |
|└InstanceId|String|i-instanceid1|磁盘挂载的实例 ID。

 |
|└OperationLocks| | |磁盘锁定原因类型。

 |
|└LockReason|String|security|磁盘被安全锁定的原因。

 |
|└Portable|Boolean|false|磁盘是否可卸载。取值范围：

 -   true：独立普通云盘，可以独立存在且可以自由在可用区内挂载和卸载。
-   false：非独立普通云盘，不可以独立存在，不可以在可用区内挂载和卸载，生命周期与实例等同。

 Portable 属性为 true 的磁盘才能挂载（[AttachDisk](~~25515~~)）或卸载（[DetachDisk](~~25516~~)）。Portable 属性为 false 的磁盘包括本地磁盘、本地 SSD 盘、普通云盘、SSD 盘的系统盘和包年包月的普通云盘。不支持修改该属性。

 |
|└ProductCode|String|jxsc000204|云市场的商品标识。

 |
|└RegionId|String|cn-hangzhou|磁盘所属的地域 ID。

 |
|└ResourceGroupId|String|rg-resourcegroupid1|磁盘所在的企业资源组 ID。

 |
|└Size|Integer|2000|磁盘大小，单位 GiB。

 |
|└SourceSnapshotId|String|s-snapshotid1|创建磁盘使用的快照，如果创建磁盘时，没有指定快照，则为空。这个值在磁盘的生命周期内始终不变。

 |
|└Status|String|Available|磁盘状态。取值范围：

 -   In\_use
-   Available
-   Attaching
-   Detaching
-   Creating
-   ReIniting

 |
|└Tags| | |磁盘的标签集合。

 |
|└TagKey|String|FinanceJoshua|磁盘的标签键。

 |
|└TagValue|String|FinanceDept|磁盘的标签值。

 |
|└Type|String|data|磁盘类型。取值范围：

 -   system: 系统盘
-   data: 数据盘

 |
|└ZoneId|String|cn-hangzhou-g|磁盘所属的可用区 ID。

 |
|PageNumber|Integer|1|磁盘列表的页码

 |
|PageSize|Integer|10|输入时设置的每页行数

 |
|RequestId|String|473469C7-AA6F-4DC5-B3DB-A3DC0DE3C83E|请求 ID

 |
|TotalCount|Integer|1|磁盘总数

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ecs.aliyuncs.com/?Action=DescribeDisks
&RegionId=cn-hangzhou
&ZoneId=cn-hangzhou-g
&DiskIds=["d-disk1"]
&InstanceId=i-instance1
&DiskType=all
&Category=all
&Status=all
&SnapshotId=s-snaoshotid1
&Portable=true
&DeleteWithInstance=false
&DeleteAutoSnapshot=false
&PageNumber=1
&PageSize=10
&DiskName=JoshuaFinance
&AutoSnapshotPolicyId=auto_20140724_2
&EnableAutoSnapshot=false
&Encrypted=false
&DryRun=false
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDisksResponse>
  <Disks>
    <Disk>
      <DeleteAutoSnapshot>true</DeleteAutoSnapshot>
      <DeleteWithInstance>false</DeleteWithInstance>
      <EnableAutoSnapshot>false</EnableAutoSnapshot>
      <Category>cloud</Category>
      <Description/>
      <DiskName/>
      <Size>5</Size>
      <Type>data</Type>
      <InstanceId/>
      <CreationTime>2014-07-23T02:44:07Z</CreationTime>
      <ImageId/>
      <ZoneId>cn-qingdao-b</ZoneId>
      <AttachedTime>2014-07-23T07:47:35Z</AttachedTime>
      <DetachedTime>2014-07-23T08:28:48Z</DetachedTime>
      <Device/>
      <OperationLocks/>
      <Portable>true</Portable>
      <ProductCode/>
      <RegionId>cn-qingdao</RegionId>
      <DiskId>d-28m5zbua0</DiskId>
      <SourceSnapshotId/>
      <Status>Available</Status>
    </Disk>
    <Disk>
      <DeleteAutoSnapshot>true</DeleteAutoSnapshot>
      <DeleteWithInstance>false</DeleteWithInstance>
      <EnableAutoSnapshot>false</EnableAutoSnapshot>
      <Category>cloud</Category>
      <Description/>
      <DiskName/>
      <Size>5</Size>
      <Type>data</Type>
      <InstanceId/>
      <CreationTime>2014-07-23T02:44:06Z</CreationTime>
      <ImageId/>
      <ZoneId>cn-qingdao-b</ZoneId>
      <AttachedTime/>
      <DetachedTime/>
      <Device/>
      <OperationLocks/>
      <Portable>true</Portable>
      <ProductCode/>
      <RegionId>cn-qingdao</RegionId>
      <DiskId>d-28zfrmo13</DiskId>
      <SourceSnapshotId/>
      <Status>Available</Status>
    </Disk>
  </Disks>
  <PageNumber>1</PageNumber>
  <PageSize>2</PageSize>
  <TotalCount>9</TotalCount>
  <RequestId>ED5CF6DD-71CA-462C-9C94-A61A78A01479</RequestId>
</DescribeDisksResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":9,
	"PageSize":2,
	"RequestId":"ACD9BBB0-A9D1-46D7-9630-B7A69889E110",
	"Disks":{
		"Disk":[
			{
				"ImageId":"",
				"Description":"",
				"Device":"",
				"ProductCode":"",
				"Portable":true,
				"DetachedTime":"2014-07-23T08:28:48Z",
				"Type":"data",
				"InstanceId":"",
				"ZoneId":"cn-qingdao-b",
				"EnableAutoSnapshot":false,
				"DiskName":"",
				"AttachedTime":"2014-07-23T07:47:35Z",
				"SourceSnapshotId":"",
				"CreationTime":"2014-07-23T02:44:07Z",
				"Status":"Available",
				"DeleteAutoSnapshot":true,
				"Category":"cloud",
				"RegionId":"cn-qingdao",
				"DeleteWithInstance":false,
				"OperationLocks":{
					"OperationLock":[]
				},
				"DiskId":"d-28m5zbua0",
				"Size":5
			},
			{
				"ImageId":"",
				"Description":"",
				"Device":"",
				"ProductCode":"",
				"Portable":true,
				"DetachedTime":"",
				"Type":"data",
				"InstanceId":"",
				"ZoneId":"cn-qingdao-b",
				"EnableAutoSnapshot":false,
				"DiskName":"",
				"AttachedTime":"",
				"SourceSnapshotId":"",
				"CreationTime":"2014-07-23T02:44:06Z",
				"Status":"Available",
				"DeleteAutoSnapshot":true,
				"Category":"cloud",
				"RegionId":"cn-qingdao",
				"DeleteWithInstance":false,
				"OperationLocks":{
					"OperationLock":[]
				},
				"DiskId":"d-28zfrmo13",
				"Size":5
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|InvalidDiskIds.Malformed|The amount of specified disk Ids exceeds the limit.|指定的磁盘ID格式不正确。|
|404|InvalidDiskChargeType.NotFound|The DiskChargeType does not exist in our records|指定的磁盘类型不存在。|
|400|InvalidTag.Mismatch|The specified Tag.n.Key and Tag.n.Value are not match.|指定的 Tag.n.Key 和 Tag.n.Value 不匹配。|
|400|InvalidRegion.NotFound|The specified parameter RegionId is not valid.|RegionId参数不合法|
|400|InvalidZoneId.NotFound|The zoneId provided does not exist in our records.|提供的 ZoneId 不存在。|
|400|InvalidParamter|Some parameters are invalid in this request.|请求中包含非法参数。|
|400|InvalidSnapshot.NotFound|The specified parameter SnapshotId is not valid.|指定的 SnapshotId 不合法。|
|404|InvalidDiskIds.ValueNotSupported|The specified parameter "DiskIds" is not supported.|指定的磁盘ID无效。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Ecs)

