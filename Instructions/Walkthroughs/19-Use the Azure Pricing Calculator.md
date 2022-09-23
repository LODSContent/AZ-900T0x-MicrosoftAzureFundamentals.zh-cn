---
wts:
  title: 19 - 使用 Azure 定价计算器（10 分钟）
  module: 'Module 06: Describe Azure cost management and service level agreements'
---
# <a name="19---use-the-pricing-calculator-10-min"></a>19 - 使用 Azure 定价计算器（10 分钟）

在本演练中，我们将使用 Azure 定价计算器生成 Azure 虚拟机和相关网络资源的成本估算。

# <a name="task-1-configure-the-pricing-calculator"></a>任务 1：配置定价计算器

在此任务中，我们将使用 Azure 定价计算器来估算示例基础结构的成本。 

<bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: To create an Azure Pricing Calculator estimate, this walkthrough provides example configurations for the VM and related resources. Use this example configurations or provide the Azure Pricing Calculator with details of your <bpt id="p1">*</bpt>actual<ept id="p1">*</ept> resource requirements instead.

1. 在浏览器中，导航至 [Azure 定价计算器](https://azure.microsoft.com/en-us/pricing/calculator/)网页。

2. 要添加 VM 配置的详细信息，请在“产品”选项卡上单击“虚拟机” 。向下滚动以查看虚拟机的详细信息。 

3. Replace <bpt id="p1">**</bpt>Your Estimate<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Virtual Machines<ept id="p2">**</ept> text with more descriptive names for your Azure Pricing Calculator estimate and your VM configuration. This walkthrough example uses <bpt id="p1">**</bpt>My Pricing Calculator Estimate<ept id="p1">**</ept> for the estimate, and <bpt id="p2">**</bpt>Windows VM<ept id="p2">**</ept> for the VM configuration.

   ![Screenshot of the vm configuration area within the Azure pricing calculator estimate webpage. The highlighted estimate name and vm configuration name indicate how to add an estimate name and a vm configuration name to an Azure pricing calculator estimate.](../images/1901.png)

4. 修改默认的 VM 配置。

    | 设置 | 值 |
    | -- | -- |
    | 区域 | **北欧** |
    | 操作系统 | **Windows** |
    | 类型 | （仅限 OS） |
    | 层 | **Standard** |  
    | 实例 | A2：**2 个核心，3.5 GB RAM，135 GB 临时存储** |

   ![Screenshot of the vm configuration area within the Azure pricing calculator estimate webpage. The highlighted examples of user inputted vm configuration property values indicate how to specify a vm configuration within an Azure pricing calculator estimate.](../images/1902.png)

    <bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: The VM instance specifications and pricing may differ from those in this example. Follow this walkthrough by choosing an instance that matches the example as closely as possible. To view details about the different VM product options, choose <bpt id="p1">**</bpt>Product details<ept id="p1">**</ept> from the <bpt id="p2">**</bpt>More info<ept id="p2">**</ept> menu on the right.

5. 设置“计费选项”为“即用即付” 。

   ![Screenshot of the vm billing options area within the Azure pricing calculator estimate webpage. The highlighted pay as you go billing option indicates how to specify a billing option for a vm within an Azure pricing calculator estimate.](../images/1903.png)

6. **注意**：为创建 Azure 定价计算器估算，本演示提供了 VM 和相关资源的示例配置。

    将 VM 的数量设置为 `1`，并将每月小时数值更改为 `365`。

   ![使用此示例配置或在 Azure 定价计算器中提供有关你实际资源要求的详细信息。](../images/1904.png)

7. 在“托管的 OS 磁盘”窗格中，修改默认的 VM 存储配置。

    | 层 | 磁盘大小 | 磁盘数目 | 快照 | 存储事务 |
    | ---- | --------- | --------------- | -------- | -------------------- |
    | 标准 HDD | S30：1024 GiB | 1 | 关 | 10,000 |

   ![Screenshot of the managed OS Disks options area within the Azure pricing calculator estimate webpage. The highlighted tier type, disk size, number of disks, and number of storage transactions, options indicate how to specify a storage configuration for a vm within an Azure pricing calculator estimate.](../images/1905.png)

8. To add networking bandwidth to your estimate, go to the top of the Azure Pricing Calculator webpage. Click <bpt id="p1">**</bpt>Networking<ept id="p1">**</ept> in the product menu on the left, then click the <bpt id="p2">**</bpt>Bandwidth<ept id="p2">**</ept> tile. In the <bpt id="p1">**</bpt>Bandwidth added<ept id="p1">**</ept> message dialog, click <bpt id="p2">**</bpt>View<ept id="p2">**</ept>.

   ![Screenshot of the networking products area within the Azure pricing calculator webpage. The highlighted networking, add bandwidth, and view bandwidth, tiles indicate how to add and view details of a networking bandwidth configuration in an Azure pricing calculator estimate.](../images/1906.png)

9. 将“你的估算”和“虚拟机”文本替换为 Azure 定价计算器估算和 VM 配置的更具描述性的名称 。

    | 区域 | 区域 1 出站数据传输量 |
    | ------ | -------------------------------------- |
    | 北欧 | 50 GB |

   ![本演示示例使用“我的定价计算器估算”进行估算，Windows VM 进行 VM 配置。](../images/1907.png)

10. To add an Application Gateway, return to the top of the Azure Pricing Calculator webpage. In the <bpt id="p1">**</bpt>Networking<ept id="p1">**</ept> product menu, click the <bpt id="p2">**</bpt>Application Gateway<ept id="p2">**</ept> tile. In the <bpt id="p1">**</bpt>Application Gateway<ept id="p1">**</ept> message dialog, click <bpt id="p2">**</bpt>View<ept id="p2">**</ept>.

    ![此屏幕截图显示了 Azure 定价计算器估算网页中的 VM 配置区域。](../images/1908.png)

11. 突出显示的估算名称和 VM 配置名称指出了如何将估算名称和 VM 配置名称添加到 Azure 定价计算器估算中。

    | 设置 | 值 |
    | -- | -- |
    | 区域 | **北欧** |
    | 层 | **基本** |
    | 大小 | **小型** |
    | 实例数 | **1** |  
    | 小时 |               365 |
    | 已处理的数据 | **50 GB** |
    | 区域 1：北美，欧洲 | **50 GB**|

    ![此屏幕截图显示了 Azure 定价计算器估算网页中的应用程序网关配置区域。](../images/1909.png)


# <a name="task-2-review-the-pricing-estimate"></a>任务 2：查看定价估算

在此任务中，我们将查看 Azure 定价计算器的结果。 

1. 滚动到 Azure 定价计算器网页底部，查看“每月估算成本”。

    <bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: Explore the various options available within the Azure Pricing Calculator. For example, this walkthrough requires you to update the currency to Euro.

2. 将货币更改为欧元，然后选择“导出”以下载 Microsoft Excel (`.xlsx`) 格式的估算副本，以供离线查看。

    ![Screenshot of the total estimated monthly costs within the Azure pricing calculator estimate webpage. The highlighted euro currency option indicates how to modify the currency used in an Azure pricing calculator estimate. The highlighted export option illustrates how to download a copy of an estimate for offline viewing.](../images/1910.png)

    ![此屏幕截图显示了 Microsoft Excel 中的示例 Azure 定价计算器估算。](../images/1911.png)

Congratulations! You downloaded an estimate from the Azure Pricing Calculator.
