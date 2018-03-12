---
title: "Get-AddressRewriteEntry"
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 1/16/2018
ms.audience: Developer
ms.topic: reference
ms.prod: exchange-server-itpro
localization_priority: Normal
ms.assetid: 633abc53-1719-42cb-bf56-077f38dd942e
description: "This cmdlet is available or effective only on Edge Transport servers in on-premises Exchange."
---

# Get-AddressRewriteEntry

This cmdlet is available or effective only on Edge Transport servers in on-premises Exchange.
  
Use the **Get-AddressRewriteEntry** cmdlet to view an existing address rewrite entry that rewrites sender and recipient email addresses in messages sent to or sent from your organization through an Edge Transport server.
  
```
Get-Addressrewriteentry [-Identity <AddressRewriteEntryIdParameter>] [-DomainController <Fqdn>]
```

## Examples
<a name="Examples"> </a>

### Example 1

This example returns a summary listing of all address rewrite entries.
  
```
Get-AddressRewriteEntry
```

### Example 2

This example returns the detailed configuration of a single address rewrite entry by piping the results to the **Format-List** command.
  
```
Get-AddressRewriteEntry "Address rewrite entry for contoso.com" | Format-List
```

## Detailed Description
<a name="DetailedDescription"> </a>

On Edge Transport servers, you need to be a member of the local Administrators group to run this cmdlet.
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |The _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> The _DomainController_ parameter isn't supported on Edge Transport servers. An Edge Transport server uses the local instance of Active Directory Lightweight Directory Services (AD LDS) to read and write data. <br/> |
| _Identity_ <br/> |Optional  <br/> |Microsoft.Exchange.Management.MessagingPolicies.AddressRewrite.AddressRewriteEntryIdParameter  <br/> |The _Identity_ parameter specifies the address rewrite entry to be retrieved. The _Identity_ parameter accepts a GUID or the unique address rewrite name. You can omit the _Identity_ parameter label. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.
  
