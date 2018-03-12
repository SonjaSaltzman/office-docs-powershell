---
title: "Preview-QuarantineMessage"
ms.author: chrisda
author: chrisda
ms.date: 3/7/2017
ms.audience: Developer
ms.topic: reference
ms.service: eop
localization_priority: Normal
ms.assetid: 0719a273-dc7e-4768-b83e-ec11c3acf833
description: "This cmdlet is available only in the cloud-based service."
---

# Preview-QuarantineMessage

This cmdlet is available only in the cloud-based service.
  
Use the **Preview-QuarantineMessage** cmdlet to preview the contents of quarantined messages in your cloud-based organization.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx).
  
```
Preview-QuarantineMessage -Identity <QuarantineMessageIdentity>
```

## Examples
<a name="Examples"> </a>

### Example 1

This example previews the quarantined message with the **Message-ID** value `<5c695d7e-6642-4681-a4b0-9e7a86613cb7@contoso.com>`.
  
```
Get-QuarantineMessage -MessageID <5c695d7e-6642-4681-a4b0-9e7a86613cb7@contoso.com> | Preview-QuarantineMessage
```

### Example 2

This example previews the quarantined message that has the specified **Identity** value.
  
```
Preview-QuarantineMessage -Identity c14401cf-aa9a-465b-cfd5-08d0f0ca37c5\4c2ca98e-94ea-db3a-7eb8-3b63657d4db7
```

## Detailed Description
<a name="DetailedDescription"> </a>

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Required  <br/> |Microsoft.Exchange.Management.FfoQuarantine.QuarantineMessageIdentity  <br/> |The  _Identity_ parameter specifies the quarantined message that you want to preview. The value is a unique quarantined message identifier in the format `GUID1\GUID2` (for example `c14401cf-aa9a-465b-cfd5-08d0f0ca37c5\4c2ca98e-94ea-db3a-7eb8-3b63657d4db7`.  <br/> You can find the  _Identity_ value for a quarantined message by using the **Get-QuarantineMessage** cmdlet. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
