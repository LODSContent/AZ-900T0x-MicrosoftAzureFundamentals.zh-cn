---
wts:
  title: 21 - 计算复合 SLA（5 分钟）
  module: 'Module 06: Describe Azure cost management and service level agreements'
---
# <a name="21---calculate-composite-slas-5-min"></a>21 - 计算复合 SLA（5 分钟）

在本演练中，我们将确定 Azure 服务的可用性 SLA，然后计算基于应用程序复合 SLA 的预期可用性。

Our example application consists of these Azure services. We will not go in to deep architectural configuration and considerations, the intention here is to give an high level example.

+ 应用服务：托管应用程序。
+ Azure AD B2C：对用户登录进行身份验证和管理配置文件。
+ **应用程序网关**：管理应用程序访问和缩放。 
+ **Azure SQL 数据库**：存储应用程序数据。 

# <a name="task-1-determine-the-sla-uptime-percentage-values-for-our-application"></a>任务 1：确定应用程序的 SLA 正常运行时间百分比值

1. 在浏览器中，转到 [Azure 服务的 SLA 摘要](https://azure.microsoft.com/en-us/support/legal/sla/summary/)页面。

2. Locate the <bpt id="p1">**</bpt>App Service<ept id="p1">**</ept> SLA uptime value, <bpt id="p2">**</bpt>99.95%<ept id="p2">**</ept>. Click <bpt id="p1">**</bpt>View full details<ept id="p1">**</ept>, and then expand <bpt id="p2">**</bpt>SLA details<ept id="p2">**</ept>. Notice the <bpt id="p1">**</bpt>Monthly uptime percentages<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Service Credits<ept id="p2">**</ept>.

3. 返回 SLA 网页，找到“Azure Active Directory B2C”服务并确定 SLA 运行时间值“99.9％”。 

4. 找到“应用程序网关”SLA 运行时间值 99.95％。 

5. The Azure SQL database uses Premium tiers but is not configured for Zone Redundant Deployments. Locate the <bpt id="p1">**</bpt>Azure SQL Database<ept id="p1">**</ept> SLA uptime value, <bpt id="p2">**</bpt>99.99%<ept id="p2">**</ept>. 

    <bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: There are different uptime values for different configurations and deployments of Azure SQL Database. It is important you are clear on your required uptime values, when planning and costing your deployment and configuration. Small changes in uptime can have impact on service costs as well as potentially increase complexity in configuration. Some other services that may be of interest on the Azure SLA summary web page would include <bpt id="p1">**</bpt>Virtual Machines<ept id="p1">**</ept>, <bpt id="p2">**</bpt>Storage Accounts<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Cosmos DB<ept id="p3">**</ept>.

# <a name="task-2-calculate-the-application-composite-sla-percentage-uptime"></a>任务 2：计算应用程序复合 SLA 百分比运行时间

1. 我们的示例应用程序由这些 Azure 服务组成。

    应用服务 % 运行时间 X Azure AD B2C % 运行时间 X Azure 应用程序网关 % 运行时间 X Azure SQL 数据库 % 运行时间  =  总 % 运行时间    

    换成百分比值如下：

    99.95% X 99.9% X 99.95% X 99.99%  =  99.79%    

    这是使用当前服务和体系结构的应用程序的基于 SLA 的预期可用性。

我们不会深入探讨体系结构配置和注意事项，这里的目的是提供一个高级示例。
