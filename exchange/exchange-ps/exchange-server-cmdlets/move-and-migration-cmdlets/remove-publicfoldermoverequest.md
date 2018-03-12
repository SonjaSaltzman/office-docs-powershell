---
title: "Remove-PublicFolderMoveRequest"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/16/2018
ms.audience: ITPro
ms.topic: reference
ms.prod: exchange-server-itpro
localization_priority: Normal
ms.assetid: 4b32356b-c893-41ad-80ab-4a7dbce54bbc
description: "This cmdlet is available only in on-premises Exchange."
---

# Remove-PublicFolderMoveRequest

This cmdlet is available only in on-premises Exchange. 
  
Use the **Remove-PublicFolderMoveRequest** cmdlet to cancel a mailbox move initiated using the[New-MoveRequest](new-moverequest.md) cmdlet. After the move has been finalized, you can't undo the move request.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Remove-PublicFolderMoveRequest -Identity <PublicFolderMoveRequestIdParameter> [-Force <SwitchParameter>] <COMMON PARAMETERS>

```

## Examples
<a name="Examples"> </a>

### Example 1

This example removes the public folder move request \PublicFolderMove.
  
```
Remove-PublicFolderMoveRequest -Identity \PublicFolderMove
```

### Example 2

This example cancels a public folder move by using the _RequestGuid_ parameter for a public folder move request on MBXDB01.
  
> [!NOTE]
> The _RequestGuid_ and _RequestQueue_ parameters are for debugging purposes only.
  
```
Remove-PublicFolderMoveRequest -RequestQueue MBXDB01 -RequestGuid 25e0eaf2-6cc2-4353-b83e-5cb7b72d441f
```

## Detailed Description
<a name="DetailedDescription"> </a>

The _RequestQueue_ and _RequestGuid_ parameters are for debugging purposes only.
  
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Required  <br/> |Microsoft.Exchange.MailboxReplicationService.PublicFolderMoveRequestIdParameter  <br/> |The _Identity_ parameter specifies the identity of the public folder move request. The default identity is \PublicFolderMove. <br/> You can't use this parameter in conjunction with the _RequestGuid_ or _RequestQueue_ parameter. <br/> |
| _RequestGuid_ <br/> |Required  <br/> |System.Guid  <br/> |The _RequestGuid_ parameter specifies the GUID of the public folder move request. If you specify the _RequestGuid_ parameter, you must also specify the _RequestQueue_ parameter. <br/> You can't use this parameter in conjunction with the _Identity_ parameter. <br/> |
| _RequestQueue_ <br/> |Required  <br/> |Microsoft.Exchange.Configuration.Tasks.DatabaseIdParameter  <br/> | The _RequestQueue_ parameter identifies the request based on the mailbox database where the request is being run. You can use any value that uniquely identifies the database. For example: <br/>  Database GUID <br/>  Database name <br/>  You can't use this parameter with the _Identity_ parameter. <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |The _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> |
| _Force_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _Force_ switch specifies whether to suppress warning or confirmation messages. You can use this switch to run tasks programmatically where prompting for administrative input is inappropriate. You don't need to specify a value with this switch. <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
