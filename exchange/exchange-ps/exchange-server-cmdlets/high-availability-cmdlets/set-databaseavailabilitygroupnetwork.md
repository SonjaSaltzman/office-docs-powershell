---
title: "Set-DatabaseAvailabilityGroupNetwork"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/16/2018
ms.audience: Developer
ms.topic: reference
ms.prod: exchange-server-itpro
localization_priority: Normal
ms.assetid: 5c6add57-eef9-4af5-9cf3-54fd910dfe93
description: "This cmdlet is available only in on-premises Exchange."
---

# Set-DatabaseAvailabilityGroupNetwork

This cmdlet is available only in on-premises Exchange. 
  
Use the **Set-DatabaseAvailabilityGroupNetwork** cmdlet to configure a network for a database availability group (DAG).
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Set-DatabaseAvailabilityGroupNetwork -Identity <DatabaseAvailabilityGroupNetworkIdParameter> [-Confirm [<SwitchParameter>]] [-Description <String>] [-DomainController <Fqdn>] [-IgnoreNetwork <$true | $false>] [-Name <String>] [-ReplicationEnabled <$true | $false>] [-Subnets <DatabaseAvailabilityGroupSubnetId[]>] [-WhatIf [<SwitchParameter>]]

```

## Examples
<a name="Examples"> </a>

### Example 1

This example enables the DAG network DAGNetwork01 in the DAG DAG1 for replication.
  
```
Set-DatabaseAvailabilityGroupNetwork -Identity DAG1\DAGNetwork01 -ReplicationEnabled:$true
```

### Example 2

This example disables the DAG network DAGNetwork02 in the DAG DAG2 for replication and configures the DAG to ignore the network.
  
```
Set-DatabaseAvailabilityGroupNetwork -Identity DAG2\DAGNetwork02 -ReplicationEnabled:$false -IgnoreNetwork:$true
```

## Detailed Description
<a name="DetailedDescription"> </a>

You can configure a variety of network properties, such as the name for the network, a description of the network, a list of one or more subnets that comprise the network, and whether the network is enabled for replication (log shipping and seeding).
  
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Required  <br/> |Microsoft.Exchange.Configuration.Tasks.DatabaseAvailabilityGroupNetworkIdParameter  <br/> |The _Identity_ parameter specifies the DAG network being configured. <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _Description_ <br/> |Optional  <br/> |System.String  <br/> |The _Description_ parameter specifies an optional description for the DAG network. <br/> |
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |The _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> |
| _IgnoreNetwork_ <br/> |Optional  <br/> |System.Boolean  <br/> |The _IgnoreNetwork_ parameter indicates that the specified network should be ignored and not used by the DAG. <br/> |
| _Name_ <br/> |Optional  <br/> |System.String  <br/> |The _Name_ parameter provides a name for the DAG network. <br/> |
| _ReplicationEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> |The _ReplicationEnabled_ parameter specifies whether the network can be used for replication activity. If this parameter isn't specified, the default behavior is to enable the network for replication. <br/> |
| _Subnets_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.DatabaseAvailabilityGroupSubnetId[]  <br/> |The _Subnets_ parameter specifies one or more subnets that are associated with the DAG network. <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
