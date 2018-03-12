---
title: "Test-IRMConfiguration"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/19/2018
ms.audience: Admin
ms.topic: reference
ms.service: exchange-online
localization_priority: Normal
ms.assetid: a730e7ff-a67f-4360-b5ff-70d171bb5e1d
description: "This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other."
---

# Test-IRMConfiguration

This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.
  
Use the **Test-IRMConfiguration** cmdlet to test Information Rights Management (IRM) configuration and functionality.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx).
  
```
Test-IRMConfiguration [-Identity <OrganizationIdParameter>] [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-Recipient <SmtpAddress[]>] [-RMSOnline <SwitchParameter>] [-RMSOnlineAuthCertThumbprintOverride <String>] [-RMSOnlineOrgOverride <Guid>] [-Sender <SmtpAddress>] [-WhatIf [<SwitchParameter>]]
```

## Examples
<a name="Examples"> </a>

### Example 1

This example tests the IRM configuration for messages sent from the sender adams@contoso.com.
  
```
Test-IRMConfiguration -Sender adams@contoso.com
```

## Detailed Description
<a name="DetailedDescription"> </a>

The **Test-IRMConfiguration** cmdlet performs a series of steps to test IRM configuration and functionality, including availability of an Active Directory Rights Management Services (AD RMS) server, prelicensing, and journal report decryption. In Exchange Online organizations, it checks connectivity to RMS Online and obtains and validates the organization's Trusted Publishing Domain (TPD).
  
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |This parameter is available only in on-premises Exchange.  <br/> The  _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> |
| _Identity_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.OrganizationIdParameter  <br/> |This parameter is available only in on-premises Exchange.  <br/> This parameter is reserved for internal Microsoft use.  <br/> |
| _Recipient_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.SmtpAddress[]  <br/> |The  _Recipient_ parameter specifies the SMTP address of one or more recipients. The cmdlet tests prelicensing for the specified recipients. You can specify multiple recipient addresses separated by commas. <br/> If no recipient is specified, the sender address is used as the recipient.  <br/> |
| _RMSOnline_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |This parameter is available only in the cloud-based service.  <br/> The  _RMSOnline_ switch specifies whether to test connectivity from Exchange Online to RMS Online, obtain your Exchange Online organization's TPD, and test its validity. You don't need to specify a value with this switch. <br/> |
| _RMSOnlineAuthCertThumbprintOverride_ <br/> |Optional  <br/> |System.String  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _RMSOnlineOrgOverride_ <br/> |Optional  <br/> |System.Guid  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _Sender_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.SmtpAddress  <br/> |The  _Sender_ parameter specifies the SMTP address of the sender to be tested. The cmdlet tests prelicensing and journal report decryption for the sender. <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The  _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
