---
title: "Get-InboundConnector"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ad72a9d6-4bac-4dd5-ae22-3246e05aac4e
description: "This cmdlet is available only in the cloud-based service."
---

# Get-InboundConnector

This cmdlet is available only in the cloud-based service. 
  
Use the **Get-InboundConnector** cmdlet to view the settings for an Inbound connector in your cloud-based organization.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Get-InboundConnector [-Identity <InboundConnectorIdParameter>]

```

## Examples
<a name="Examples"> </a>

### Example 1

This example displays detailed configuration information for the Inbound connector named Inbound Connector for Contoso.com.
  
```
Get-InboundConnector "Inbound Connector for Contoso.com" | Format-List
```

### Example 2

This example lists all the Inbound connectors configured in your cloud-based organization.
  
```
Get-InboundConnector
```

## Detailed Description
<a name="DetailedDescription"> </a>

Inbound connectors accept email messages from remote domains that require specific configuration options.
  
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.InboundConnectorIdParameter  <br/> |The  _Identity_ parameter specifies the name, or GUID of the Inbound connector. If the _Identity_ name contains spaces, enclose the name in quotation marks ("). You can omit the _Identity_ parameter label. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
