---
title: "Update-DistributionGroupMember"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/16/2018
ms.audience: ITPro
ms.topic: reference
ms.prod: exchange-server-itpro
localization_priority: Normal
ms.assetid: 010394d3-5554-42f6-b0c3-5af5881c75ff

description: "This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other."
---

# Update-DistributionGroupMember

This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other. 
  
Use the **Update-DistributionGroupMember** cmdlet to replace all members of distribution groups and mail-enabled security groups. To add or remove existing group members, use the **Add-DistributionGroupMember** and **Remove-DistributionGroupMember** cmdlets.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Update-DistributionGroupMember -Identity <DistributionGroupIdParameter> [-BypassSecurityGroupManagerCheck <SwitchParameter>] [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-Members <MultiValuedProperty>] [-WhatIf [<SwitchParameter>]]

```

## Examples
<a name="Examples"> </a>

### Example 1

This example replaces the existing members of the distribution group name Research Reports with new members.
  
```
Update-DistributionGroupMember -Identity "Research Reports" -Members chris@contoso.com,michelle@contoso.com,laura@contoso.com,julia@contoso.com
```

## Detailed Description
<a name="DetailedDescription"> </a>

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Required  <br/> |Microsoft.Exchange.Configuration.Tasks.DistributionGroupIdParameter  <br/> | The _Identity_ parameter specifies the distribution group or mail-enabled security group that you want to modify. You can use any value that uniquely identifies the group. <br/>  For example: <br/>  Name <br/>  Display name <br/>  Alias <br/>  Distinguished name (DN) <br/>  Canonical DN <br/>  Email address <br/>  GUID <br/> |
| _BypassSecurityGroupManagerCheck_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _BypassSecurityGroupManagerCheck_ switch specifies whether to allow a user who isn't an owner of the group to modify or delete the group. If you aren't defined in the **ManagedBy** property of the group, you need to use this switch in commands that modify or delete the group. To use this switch, your account requires specific permissions based on the group type: <br/> **Distribution groups or mail-enabled security groups**: You need to be a member of the Organization Management role group or have the Security Group Creation and Membership role assigned.  <br/> **Role groups**: You need to be a member of the Organization Management role group or have the Role Management role assigned.  <br/>  You don't need to specify a value with this switch. <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |This parameter is available only in on-premises Exchange.  <br/> The _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> |
| _Members_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.MultiValuedProperty  <br/> | The _Members_ parameter specifies the recipients (mail-enabled objects) that will replace the current group members. You can use any value that uniquely identifies the recipient. <br/>  For example: <br/>  Name <br/>  Display name <br/>  Alias <br/>  Distinguished name (DN) <br/>  Canonical DN <br/>  Email address <br/>  GUID <br/>  To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax:  `"<value1>","<value2>",..."<valueX>"`.  <br/> > [!NOTE]>  Although it isn't required, it's a good idea to add only security principals (for example, mailboxes and mail users with user accounts or other mail-enabled security groups) to mail-enabled security groups. If you assign permissions to a mail-enabled security group, any members that aren't security principals (for example, mail contacts or distribution groups) won't have the permissions assigned.          |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
