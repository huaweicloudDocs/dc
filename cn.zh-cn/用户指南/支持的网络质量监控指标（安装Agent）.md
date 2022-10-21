# 支持的网络质量监控指标（安装Agent）<a name="dc_04_0805"></a>

云专线插件是用于检测云专线端到端的网络质量的插件，主要包含网络时延和丢包率两个指标。

云专线插件分为两种：

-   dc-nqa-collector：用于监控自动化专线，探测远端子网的时延和丢包率。
-   history-dc-nqa-collector：用于监控手工专线，探测远端子网的时延和丢包率。

详细请参考[安装云专线指标采集插件](https://support.huaweicloud.com/usermanual-ces/ces_01_0102.html)。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   自动化专线，云专线资源包括物理连接、虚拟网关和虚拟接口，路由配置自动下发。目前大多数Region的云专线都属于自动化专线。
>-   手工专线，云专线资源只有物理连接，没有虚拟网关和虚拟接口，需手工配置路由等信息。目前有部分Region的存量资源属于手工专线。

## 监控指标<a name="section1132516534316"></a>

**表 1**  网络质量监控指标

<a name="table114711628164913"></a>
<table><thead align="left"><tr id="row64721428144917"><th class="cellrowborder" valign="top" width="16.666666666666664%" id="mcps1.2.7.1.1"><p id="zh-cn_topic_0024607920_p61417783193247"><a name="zh-cn_topic_0024607920_p61417783193247"></a><a name="zh-cn_topic_0024607920_p61417783193247"></a>指标ID</p>
</th>
<th class="cellrowborder" valign="top" width="16.666666666666664%" id="mcps1.2.7.1.2"><p id="zh-cn_topic_0024607920_p8784488193247"><a name="zh-cn_topic_0024607920_p8784488193247"></a><a name="zh-cn_topic_0024607920_p8784488193247"></a>指标名称</p>
</th>
<th class="cellrowborder" valign="top" width="16.666666666666664%" id="mcps1.2.7.1.3"><p id="zh-cn_topic_0024607920_p40454922193247"><a name="zh-cn_topic_0024607920_p40454922193247"></a><a name="zh-cn_topic_0024607920_p40454922193247"></a>指标含义</p>
</th>
<th class="cellrowborder" valign="top" width="16.666666666666664%" id="mcps1.2.7.1.4"><p id="zh-cn_topic_0024607920_p55623236193247"><a name="zh-cn_topic_0024607920_p55623236193247"></a><a name="zh-cn_topic_0024607920_p55623236193247"></a>取值范围</p>
</th>
<th class="cellrowborder" valign="top" width="16.666666666666664%" id="mcps1.2.7.1.5"><p id="zh-cn_topic_0024607920_p9188287193247"><a name="zh-cn_topic_0024607920_p9188287193247"></a><a name="zh-cn_topic_0024607920_p9188287193247"></a>测量对象</p>
</th>
<th class="cellrowborder" valign="top" width="16.666666666666664%" id="mcps1.2.7.1.6"><p id="p181159917508"><a name="p181159917508"></a><a name="p181159917508"></a>监控周期</p>
</th>
</tr>
</thead>
<tbody><tr id="row144721028134914"><td class="cellrowborder" valign="top" width="16.666666666666664%" headers="mcps1.2.7.1.1 "><p id="p74721028194912"><a name="p74721028194912"></a><a name="p74721028194912"></a>latency</p>
</td>
<td class="cellrowborder" valign="top" width="16.666666666666664%" headers="mcps1.2.7.1.2 "><p id="p94724284493"><a name="p94724284493"></a><a name="p94724284493"></a>时延</p>
</td>
<td class="cellrowborder" valign="top" width="16.666666666666664%" headers="mcps1.2.7.1.3 "><p id="p1747232834912"><a name="p1747232834912"></a><a name="p1747232834912"></a>云专线的网络时延</p>
<p id="p083113712439"><a name="p083113712439"></a><a name="p083113712439"></a>单位：ms</p>
</td>
<td class="cellrowborder" valign="top" width="16.666666666666664%" headers="mcps1.2.7.1.4 "><p id="p4472162814493"><a name="p4472162814493"></a><a name="p4472162814493"></a>≥ 0 ms</p>
<p id="p136857168430"><a name="p136857168430"></a><a name="p136857168430"></a></p>
</td>
<td class="cellrowborder" valign="top" width="16.666666666666664%" headers="mcps1.2.7.1.5 "><p id="p14472628194911"><a name="p14472628194911"></a><a name="p14472628194911"></a>物理连接和历史物理连接</p>
</td>
<td class="cellrowborder" valign="top" width="16.666666666666664%" headers="mcps1.2.7.1.6 "><p id="p947216280493"><a name="p947216280493"></a><a name="p947216280493"></a>1分钟</p>
</td>
</tr>
<tr id="row14722028174919"><td class="cellrowborder" valign="top" width="16.666666666666664%" headers="mcps1.2.7.1.1 "><p id="p947212286495"><a name="p947212286495"></a><a name="p947212286495"></a>packet_loss_rate</p>
</td>
<td class="cellrowborder" valign="top" width="16.666666666666664%" headers="mcps1.2.7.1.2 "><p id="p6472228124915"><a name="p6472228124915"></a><a name="p6472228124915"></a>丢包率</p>
</td>
<td class="cellrowborder" valign="top" width="16.666666666666664%" headers="mcps1.2.7.1.3 "><p id="p1161217415449"><a name="p1161217415449"></a><a name="p1161217415449"></a>云专线的丢包率</p>
<p id="p1761218416447"><a name="p1761218416447"></a><a name="p1761218416447"></a>单位：%</p>
</td>
<td class="cellrowborder" valign="top" width="16.666666666666664%" headers="mcps1.2.7.1.4 "><p id="p1961212404419"><a name="p1961212404419"></a><a name="p1961212404419"></a>0~100%</p>
<p id="p15612114204417"><a name="p15612114204417"></a><a name="p15612114204417"></a></p>
</td>
<td class="cellrowborder" valign="top" width="16.666666666666664%" headers="mcps1.2.7.1.5 "><p id="p176122049445"><a name="p176122049445"></a><a name="p176122049445"></a>物理连接和历史物理连接</p>
</td>
<td class="cellrowborder" valign="top" width="16.666666666666664%" headers="mcps1.2.7.1.6 "><p id="p961211411444"><a name="p961211411444"></a><a name="p961211411444"></a>1分钟</p>
</td>
</tr>
</tbody>
</table>

## 维度<a name="section17245133619325"></a>

<a name="zh-cn_topic_0024607920_table30802540193247"></a>
<table><thead align="left"><tr id="zh-cn_topic_0024607920_row7692483193247"><th class="cellrowborder" valign="top" width="28.000000000000004%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0024607920_p19111369193247"><a name="zh-cn_topic_0024607920_p19111369193247"></a><a name="zh-cn_topic_0024607920_p19111369193247"></a>Key</p>
</th>
<th class="cellrowborder" valign="top" width="72%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0024607920_p4517093193247"><a name="zh-cn_topic_0024607920_p4517093193247"></a><a name="zh-cn_topic_0024607920_p4517093193247"></a>Value</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0024607920_row30340220193247"><td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.1.3.1.1 "><p id="p529414117341"><a name="p529414117341"></a><a name="p529414117341"></a>virtual_interface_id</p>
</td>
<td class="cellrowborder" valign="top" width="72%" headers="mcps1.1.3.1.2 "><p id="p102924111349"><a name="p102924111349"></a><a name="p102924111349"></a>虚拟接口，自动化专线的监控维度。</p>
</td>
</tr>
<tr id="row1092317557465"><td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.1.3.1.1 "><p id="p0923115514617"><a name="p0923115514617"></a><a name="p0923115514617"></a>history_direct_connect_id</p>
</td>
<td class="cellrowborder" valign="top" width="72%" headers="mcps1.1.3.1.2 "><p id="p17923205512466"><a name="p17923205512466"></a><a name="p17923205512466"></a>历史物理连接，手工专线的监控维度。</p>
</td>
</tr>
</tbody>
</table>

