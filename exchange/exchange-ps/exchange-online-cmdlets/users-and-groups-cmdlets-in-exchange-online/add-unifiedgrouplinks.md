---
title: "Add-UnifiedGroupLinks"
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 11/9/2016
ms.audience: Developer
ms.topic: reference
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 0d7e03d4-b2dc-4a0b-865a-9ff33e53e221
description: "This cmdlet is available only in the cloud-based service."
---

# Add-UnifiedGroupLinks

This cmdlet is available only in the cloud-based service. 
  
Use the **Add-UnifiedGroupLinks** cmdlet to add members, owners and subscribers to Office 365 groups in your cloud-based organization. To remove members, owners and subscribers, use the **Remove-UnifiedGroupLinks** cmdlet. To modify other properties of Office 365 groups, use the **Set-UnifiedGroup** cmdlet.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Add-UnifiedGroupLinks -Identity <UnifiedGroupIdParameter> -Links <RecipientIdParameter[]> -LinkType <Members | Owners | Subscribers | Aggregators | EventSubscribers> [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

```

## Examples
<a name="Examples"> </a>

### Example 1

This example adds members chris@contoso.com and michelle@contoso.com to the Office 365 Group named Legal Department.
  
```
Add-UnifiedGroupLinks -Identity "Legal Department" -LinkType Members -Links chris@contoso.com,michelle@contoso.com
```

## Detailed Description
<a name="DetailedDescription"> </a>

Office 365 groups are group objects that are available across Office 365 services. 
  
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx). 
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Required  <br/> |Microsoft.Exchange.Configuration.Tasks.UnifiedGroupIdParameter  <br/> | The _Identity_ parameter specifies the Office 365 Group that you want to modify. You can use any value that uniquely identifies the Office 365 Group. <br/>  For example: <br/>  Name <br/>  Display name <br/>  Alias <br/>  Distinguished name (DN) <br/>  Canonical DN <br/>  Email address <br/>  GUID <br/> |
| _Links_ <br/> |Required  <br/> |Microsoft.Exchange.Configuration.Tasks.RecipientIdParameter[]  <br/> | The _Links_ parameter specifies the recipients to add to the Office 365 Group. You specify whether these recipients are members, owners, or subscribers by using the _LinkType_ parameter. <br/>  You can use any value that uniquely identifies the recipient. <br/>  For example: <br/>  Name <br/>  Display name <br/>  Alias <br/>  Distinguished name (DN) <br/>  Canonical DN <br/>  Email address <br/>  GUID <br/>  To enter multiple values, use the following syntax: `<value1>,<value2>,...<valueX>`. If the values contain spaces or otherwise require quotation marks, use the following syntax:  `"<value1>","<value2>",..."<valueX>"`.  <br/> |
| _LinkType_ <br/> |Required  <br/> |Microsoft.Exchange.Management.RecipientTasks.LinkType  <br/> | The _LinkType_ parameter specifies the Office 365 Group property that you want to modify. Valid values are: <br/>  `EventSubscribers` <br/>  `Members` <br/>  `Owners` <br/>  `Subscribers` <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The  _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
