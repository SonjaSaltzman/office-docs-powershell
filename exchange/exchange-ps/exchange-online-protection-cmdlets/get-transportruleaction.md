---
title: "Get-TransportRuleAction"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/6/2016
ms.audience: Admin
ms.topic: reference
ms.service: eop
localization_priority: Normal
ms.assetid: 60829f04-94a0-4228-a66c-f467aaca438b
description: "This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other."
---

# Get-TransportRuleAction

This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.
  
Use the **Get-TransportRuleAction** cmdlet to view the actions that are available for transport rules (mail flow rules).
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx).
  
```
Get-TransportRuleAction [-Name <String>]

```

## Examples
<a name="Examples"> </a>

### Example 1

This example returns a summary list of all actions.
  
```
Get-TransportRuleAction
```

### Example 2

This example retrieves detailed information about the action named  `DeleteMessage`.
  
```
Get-TransportRuleAction -Name DeleteMessage | Format-List
```

For more information about pipelining, see [Pipelining](http://technet.microsoft.com/library/59411ed3-926b-4eec-a462-84e6b26056c9.aspx). For more information about how to work with the output of a command, see [Manipulating Command Output](http://technet.microsoft.com/library/8320e1a5-d3f5-4615-878d-b23e2aaa6b1e.aspx).
  
## Detailed Description
<a name="DetailedDescription"> </a>

In on-premises Exchange, the actions that are available on Mailboxes servers and Edge Transports server are different. Also, the names of some of the actions that are returned by this cmdlet are different than the corresponding parameter names in the **New-TransportRule** and **Set-TransportRule** cmdlets.
  
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Name_ <br/> |Optional  <br/> |System.String  <br/> |The  _Name_ parameter specifies the name of the action that you want to view. To see the list of available names, run the command `Get-TransportRuleAction`.  <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
