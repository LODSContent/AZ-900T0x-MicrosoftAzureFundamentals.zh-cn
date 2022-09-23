---
wts:
  title: 04 - 创建虚拟网络（20 分钟）
  module: Module 02 - Core Azure Services (Workloads)
---
# <a name="04---create-a-virtual-network-20-min"></a>04 - 创建虚拟网络（20 分钟）

在本演练中，我们将创建一个虚拟网络，将两个虚拟机部署到该虚拟网络上，然后配置它们以允许一个虚拟机通过该虚拟网络 ping 至另一个虚拟机。

# <a name="task-1-create-a-virtual-network"></a>任务 1：创建虚拟网络 

在此任务中，我们将创建虚拟网络。 

注意：在开始实验室之前，请通过打开“开始”菜单>“设置”>“网络和 Internet”>“查找 Windows 防火墙”，禁用虚拟机中的公共和专用防火墙

1. 通过 <a href="https://portal.azure.com" target="_blank"><span style="color: #0066cc;" color="#0066cc">https://portal.azure.com</span></a> 登录到 Azure 门户

2. 从“所有服务”边栏选项卡，搜索并选择“虚拟网络”，然后单击“+ 添加、+ 创建、+ 新建”  。 

3. 在“基本”选项卡上，填写以下信息（其他所有设置保留默认值）：

    | 设置 | 值 | 
    | --- | --- |
    | 订阅 | 保留提供的默认值 |
    | 资源组 | **新建资源组** |
    | 名称 | vnet1 |
    | 区域 | **（美国）美国东部** |
    
   
4. Click the <bpt id="p1">**</bpt>Review + create<ept id="p1">**</ept> button. Ensure the validation passes. Then hit create to deploy the resource.


# <a name="task-2-create-two-virtual-machines"></a>任务 2：创建两个虚拟机

在此任务中，我们将在虚拟网络中创建两个虚拟机。 

1. 在“所有服务”边栏选项卡中，搜索“虚拟机”，然后单击“+ 添加、+ 创建、+ 新建”，从下拉列表中选择“虚拟机”   。 

2. 在“基本”选项卡上，填写以下信息（其他所有设置保留默认值）：

   | 设置 | 值 | 
   | --- | --- |
   | 订阅 | 使用提供的默认值 |
   | 资源组 |  选择下拉列表中的默认值 |
   | 虚拟机名称 | **VM1**|
   | 区域 | **（美国）美国东部** |
   | 映像 | Windows Server 2019 Datacenter - Gen2 |
   | 用户名| **azureuser** |
   | 密码| **Pa$$w0rd1234** |
   | 公共入站端口| 选择“允许所选端口”  |
   | 选定的入站端口| **RDP (3389)** |
   

3. Select the <bpt id="p1">**</bpt>Networking<ept id="p1">**</ept> tab. Make sure the virtual machine is placed in the <bpt id="p2">**</bpt>vnet1<ept id="p2">**</ept> virtual network. Review the default settings, but do not make any other changes. 

4. Click <bpt id="p1">**</bpt>Review + create<ept id="p1">**</ept>. After the Validation passes, click <bpt id="p1">**</bpt>Create<ept id="p1">**</ept>. Deployment times can vary but it can generally take between three to six minutes to deploy.

5. 监视你的部署，同时继续执行下一步。 

6. Create a second virtual machine by repeating steps <bpt id="p1">**</bpt>2 to 4<ept id="p1">**</ept> above. Make sure you use a different virtual machine name, that the virtual machine is in the same virtual network, and is using a new public IP address:

    | 设置 | 值 |
    | --- | --- |
    | 资源组 | 选择下拉列表中的默认值（与 Task1-3 和 Task2-2 相同） |
    | 虚拟机名称 |  vm2 |
    | 虚拟网络 | vnet1 |
    | 公共 IP | vm2-ip |

7. 等待两个虚拟机完成部署，其状态显示为“正在运行”。

# <a name="task-3-test-the-connection"></a>任务 3：测试连接 

In this task, we will try to test whether the virtual machines can communicate (ping) each other. If not we will install a rule to allow an ICMP connection. Usually ICMP connections are automatically blocked.

1. From the <bpt id="p1">**</bpt>All resources<ept id="p1">**</ept> blade, search for <bpt id="p2">**</bpt>vm1<ept id="p2">**</ept>, open its <bpt id="p3">**</bpt>Overview<ept id="p3">**</ept> blade, and make sure its <bpt id="p4">**</bpt>Status<ept id="p4">**</ept> is <bpt id="p5">**</bpt>Running<ept id="p5">**</ept>. You may need to <bpt id="p1">**</bpt>Refresh<ept id="p1">**</ept> the page.

2. 在“概述”边栏选项卡上，选择“连接”并选择下拉列表中的“RDP”  。

    **注意**：以下说明介绍如何从 Windows 计算机连接到 VM。 

3. 在“使用 RDP 连接”边栏选项卡上，保留默认选项，按 IP 地址通过端口 3389 进行连接，然后单击“下载 RDP 文件” 。

4. 打开下载的 RDP 文件（位于 VM 的左下角）并在出现提示时单击“连接”。 

5. 在“Windows 安全性”窗口中，键入用户名“azureuser”和密码“Pa$$w0rd1234”，然后单击“确定”   。

6. You may receive a certificate warning during the sign-in process. Click <bpt id="p1">**</bpt>Yes<ept id="p1">**</ept> to create the connection and connect to your deployed VM. You should connect successfully. Close the Windows Server and Dashboard windows that pop up. You should see a Blue Windows background. You are now in your virtual machine.

7. 在两个新创建的虚拟机中，通过 RDP 进行连接，然后通过打开“开始”菜单>“设置”>“网络和 Internet”>“查找 Windows 防火墙”，禁用公共和专用防火墙。

8. 在虚拟机上打开 PowerShell：单击“开始”按钮，在“搜索”中键入“PowerShell”，然后依次右键单击“Windows PowerShell”和“以管理员身份运行”   。

9. 在 Powershell 中，尝试通过键入以下命令来 ping 通 vm2：

   ```PowerShell
   ping vm2
   ```

 10. You should be successful. You have pinged VM2 from VM1.


<bpt id="p1">**</bpt>Congratulations!<ept id="p1">**</ept> You have configured and deployed two virtual machines in a virtual network, and then you were able to connect them.

<bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: To avoid additional costs, you can optionally remove this resource group. Search for resource groups, click your resource group, and then click <bpt id="p1">**</bpt>Delete resource group<ept id="p1">**</ept>. Verify the name of the resource group and then click <bpt id="p1">**</bpt>Delete<ept id="p1">**</ept>. Monitor the <bpt id="p1">**</bpt>Notifications<ept id="p1">**</ept> to see how the delete is proceeding.
