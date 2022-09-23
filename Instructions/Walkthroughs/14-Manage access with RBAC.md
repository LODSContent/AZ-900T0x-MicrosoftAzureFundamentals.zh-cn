---
wts:
  title: 14 - 使用 RBAC 管理访问权限（5 分钟）
  module: 'Module 05: Describe identity, governance, privacy, and compliance features'
---
# <a name="14---manage-access-with-rbac-5-min"></a>14 - 使用 RBAC 管理访问权限（5 分钟）

在本演练中，我们将为资源分配权限角色并查看日志。

# <a name="task-1-view-and-assign-roles"></a>任务 1：查看和分配角色

在此任务中，我们将分配虚拟机参与者角色。 

1. 登录 [Azure 门户](https://portal.azure.com)。

2. 在“所有服务”边栏选项卡中，搜索并选择“资源组”，然后单击“+ 添加 + 新建 + 创建”  。

3. Create a new resource group. Click <bpt id="p1">**</bpt>Create<ept id="p1">**</ept> when you are finished. 

    | 设置 | 值 |
    | -- | -- |
    | 订阅 | 使用提供的默认值 |
    | 资源组 | myRGRBAC |
    | 区域 | **（美国）美国东部** |
   

4. 单击“查看 + 创建”，然后点击“创建” 。

5. 刷新资源组页面，并单击表示新创建的资源组的条目。

6. Click on the <bpt id="p1">**</bpt>Access control (IAM)<ept id="p1">**</ept> blade, and then switch to the <bpt id="p2">**</bpt>Roles<ept id="p2">**</ept> tab. Scroll through the large number of roles definitions that are available. Use the Informational icons to get an idea of each role's permissions. Notice there is also information on the number of users and groups that are assigned to each role.
7. 
![image](https://user-images.githubusercontent.com/89808319/144266949-f19d91ab-31d6-4c8b-af36-c00035925cf0.png)

7. Switch to the <bpt id="p1">**</bpt>Role assignments<ept id="p1">**</ept> tab of the <bpt id="p2">**</bpt>myRGRBAC - Access control (IAM)<ept id="p2">**</ept> blade, click <bpt id="p3">**</bpt>+ Add<ept id="p3">**</ept> and then click <bpt id="p4">**</bpt>Add role assignment<ept id="p4">**</ept>. Search for the Virtual Machine Contributor role and select. Switch to the "Members" tab and Assign access to: User, group, or service principal. Then click + Select members and type in your name to the popup search function and hit 'select.' Then hit 'Review and Assign'

    
    ![image](https://user-images.githubusercontent.com/89808319/144266255-3a0f8574-9358-4c21-8f95-3503747e77c8.png)

 

    **注意：** 通过虚拟机参与者角色，你可以管理虚拟机，但不能访问它们的操作系统，也不能管理它们所连接的虚拟网络和存储帐户。

  

8. “刷新”角色分配页面，并确保你现已列为虚拟机参与者。 

    **注意**：由于你的帐户已具有所有者角色，而该角色包含与参与者角色相关联的所有特权，因此该分配实际上不会向你授予任何其他特权。

# <a name="task-2-monitor-role-assignments-and-remove-a-role"></a>任务 2：监视角色分配并删除角色

在此任务中，我们将查看活动日志以验证角色是否分配，然后删除角色。 

1. 在 myRGRBAC 资源组边栏选项卡上，单击“活动日志”。

2. 单击“添加筛选器”，选择“操作”，然后选择“创建角色分配”。

    ![此屏幕截图显示了“活动日志”页面，其中已配置筛选器。](../images/1503.png)

3. 验证活动日志是否显示你的角色分配。 

    **注意**：你知道如何删除角色分配吗？

Congratulations! You created a resource group, assigned an access role to it and viewed activity logs. 

<bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: To avoid additional costs, you can optionally remove this resource group. Search for resource groups, click your resource group, and then click <bpt id="p1">**</bpt>Delete resource group<ept id="p1">**</ept>. Verify the name of the resource group and then click <bpt id="p1">**</bpt>Delete<ept id="p1">**</ept>. Monitor the <bpt id="p1">**</bpt>Notifications<ept id="p1">**</ept> to see how the delete is proceeding.

