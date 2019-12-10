# 访问OBS<a name="zh-cn_topic_0138837834"></a>

## 操作场景<a name="section208321434111114"></a>

VPN、云专线线下节点通过终端节点高速访问OBS。

## 操作前提<a name="section4151131713"></a>

-   VPN连接的本端子网需包含OBS的网段100.125.0.0/16
-   专线虚拟网关的VPC网段需包含OBS的网段100.125.0.0/16

## 操作步骤<a name="section14475182616113"></a>

1.  在管理控制台左上角单击![](figures/d00356817-云计算开发部-公有云_IaaS-image-f1cac6ef-c4f7-462b-a7f1-85e988937e64-6.png)图标，选择区域和项目。
2.  创建VPN网关、VPN连接连通线下节点和VPC。
3.  单击“服务列表”中的“网络 \> VPC终端节点”，进入终端节点页面。
4.  在左侧导航栏选择“VPC 终端节点 \> 终端节点”。
5.  <a name="li145571928161519"></a>在终端节点界面单击“购买终端节点”，创建连接DNS服务的终端节点。
6.  选择“云服务 \> dns.myhuaweicloud.com”。
7.  选择“创建内网域名”。虚拟私有云和子网选择VPN或专线接入的云内VPC ，配置参数如[购买终端节点](#fig13281195818209)所示。

    **图 1**  购买终端节点2<a name="fig13281195818209"></a>  
    ![](figures/购买终端节点2.png "购买终端节点2")

8.  选择“立即购买 \> 提交”，完成创建。
9.  <a name="li688862223218"></a>查看连接DNS服务的终端节点创建完成后返回的节点IP。
10. 在用户线下的DNS服务器配置相应的DNS转发规则，将解析OBS域名的请求转发到DNS终端节点。

    以常见的DNS软件Bind为例：

    方式1：在/etc/named.conf内，增加DNS转发器的配置，forwarders为DNS终端节点IP地址。

    ```
    options {
            forward only；
            forwarders{ xx.xx.xx.xx;};
    };
    ```

    方式2：在/etc/named.rfc1912.zones文件，增加如下内容，forwarders为DNS终端节点IP地址。

    以华南OBS Endpoint为例：

    ```
    zone "obs.cn-south-1.myhuaweicloud.com" {
            type forward;
            forward only;
            forwarders{ xx.xx.xx.xx;};
    };
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   线下若无DNS服务器，需要通过增加DNS终端节点IP地址到线下节点的/etc/resolv.conf文件中。  
    >-   xx.xx.xx.xx为步骤[9](#li688862223218)中的节点IP。  

11. 配置线下节点到专线网关或VPN网关的DNS路由。

    DNS终端节点IP的IP地址为xx.xx.xx.xx，所以需要将节点访问DNS的流量指向线下专线网关或VPN网关，然后走专线或VPN访问OBS。在线下节点配置永久路由，指定访问OBS的流量下一跳为线下专线网关或VPN网关的IP地址。

    route -p add xx.xx.xx.xx mask 255.255.255.255 xxx.xxx.xxx.xxx

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   xx.xx.xx.xx为步骤[9](#li688862223218)中的节点IP。  
    >-   xxx.xxx.xxx.xxx为线下专线网关或VPN网关的IP地址。  

12. 参考步骤[5](#li145571928161519)到[9](#li688862223218)，创建连接OBS服务的终端节点。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >线下节点只能访问终端节点所在区域对应的OBS域名地址。  

13. 配置线下节点到专线网关或VPN网关的OBS路由。

    线上OBS的IP地址网段为100.125.0.0/16，所以需要将节点访问OBS的流量指向线下专线网关或VPN网关，然后走专线或VPN访问OBS。

    在线下节点配置永久路由，指定访问OBS的流量下一跳为线下专线网关或VPN网关的IP地址。

    ```
    route -p add 100.125.0.0 mask 255.255.0.0 xxx.xxx.xxx.xxx
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果线下节点和线下专线网关或VPN网关网络不通，需要预先打通之间的网络。  


