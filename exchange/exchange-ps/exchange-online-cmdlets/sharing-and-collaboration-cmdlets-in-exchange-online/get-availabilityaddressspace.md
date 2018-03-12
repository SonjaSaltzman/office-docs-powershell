---
title: "Get-AvailabilityAddressSpace"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/16/2018
ms.audience: Developer
ms.topic: reference
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 46777869-f5b1-4eee-8ce6-68c3a9002be4
description: "This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other."
---

# Get-AvailabilityAddressSpace

This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other. 
  
Use the **Get-AvailabilityAddressSpace** cmdlet to view existing availability address space objects that are used to share free/busy data across Exchange organizations.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Get-AvailabilityAddressSpace [-Identity <AvailabilityAddressSpaceIdParameter>] [-DomainController <Fqdn>]

```

## Examples
<a name="Examples"> </a>

### Example 1

This example returns a summary list of all availability address space objects that are configured in your organization.
  
```
Get-AvailabilityAddressSpace
```

### Example 2

This example returns details information for the availability address space object named Contoso.com.
  
```
Get-AvailabilityAddressSpace -Identity Contoso.com | Format-List
```

## Detailed Description
<a name="DetailedDescription"> </a>

In on-premises Exchange organizations, you run the **Remove-AvailabilityAddressSpace** cmdlet on Exchange servers that have the Client Access server role installed.
  
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |This parameter is available only in on-premises Exchange.  <br/> The  _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> |
| _Identity_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.AvailabilityAddressSpaceIdParameter  <br/> | The _Identity_ parameter specifies the availability address space that you want to view. You can use any value that uniquely identifies the object. For example: <br/>  Name <br/>  Distinguished name (DN) <br/>  GUID <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
