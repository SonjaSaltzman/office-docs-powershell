---
title: "Suspend-MailboxImportRequest"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/17/2017
ms.audience: ITPro
ms.topic: reference
ms.prod: exchange-server-itpro
localization_priority: Normal
ms.assetid: 49836c94-b353-49e8-a1f1-ca59e4a37443
description: "This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other."
---

# Suspend-MailboxImportRequest

This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.
  
Use the **Suspend-MailboxImportRequest** cmdlet to suspend an import request any time after the request was created, but before the request reaches the status of `Completed`. You can resume the move request by using the [Resume-MailboxImportRequest](resume-mailboximportrequest.md) cmdlet.
  
> [!NOTE]
> This cmdlet is available only in the Mailbox Import Export role, and by default, that role isn't assigned to a role group. To use this cmdlet, you need to add the Mailbox Import Export role to a role group (for example, to the Organization Management role group). For more information, see the "Add a role to a role group" section in [Manage role groups](https://technet.microsoft.com/library/jj657480.aspx). 
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx).
  
```
Suspend-MailboxImportRequest -Identity <MailboxImportRequestIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-SuspendComment <String>] [-WhatIf [<SwitchParameter>]]

```

## Examples
<a name="Examples"> </a>

### Example 1

This example suspends the second import request for Ayla's mailbox with the identity Ayla\MailboxImport1.
  
```
Suspend-MailboxImportRequest -Identity "Ayla\MailboxImport1"
```

### Example 2

This example suspends all import requests that are in progress by using the [Get-MailboxImportRequest](get-mailboximportrequest.md) cmdlet to retrieve all requests with a Status of `InProgress`, and then pipelining the output to the **Suspend-MailboxImportRequest** cmdlet with the suspend comment "Resume after 22:00 (10 P.M.)".
  
```
Get-MailboxImportRequest -Status InProgress | Suspend-MailboxImportRequest -SuspendComment "Resume after 22:00 (10 P.M.)"
```

## Detailed Description
<a name="DetailedDescription"> </a>

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Required  <br/> |Microsoft.Exchange.MailboxReplicationService.MailboxImportRequestIdParameter  <br/> |The _Identity_ parameter specifies the identity of the import request. By default, import requests are named < _alias_>\MailboxImport _X_ (where _X_ = 0-9). If you created the request by using the _Name_ parameter, use the following syntax: < _alias_>\< _name_>.  <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |This parameter is available only in on-premises Exchange.  <br/> The _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> |
| _SuspendComment_ <br/> |Optional  <br/> |System.String  <br/> |The _SuspendComment_ parameter specifies a description about why the request was suspended. You can only use this parameter if you specify the _Suspend_ parameter. <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.
  
