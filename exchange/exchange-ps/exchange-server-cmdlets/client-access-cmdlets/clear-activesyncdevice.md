---
title: "Clear-ActiveSyncDevice"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/16/2018
ms.audience: Developer
ms.topic: reference
ms.prod: exchange-server-itpro
localization_priority: Normal
ms.assetid: 016768f2-98b3-4f71-b15a-830285a6feac
description: "This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other."
---

# Clear-ActiveSyncDevice

This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other. 
  
Use the **Clear-ActiveSyncDevice** cmdlet to delete all data from a mobile device.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
> [!CAUTION]
> The **Clear-ActiveSyncDevice** cmdlet will be removed in a future version of Exchange. Use the **Clear-MobileDevice** cmdlet instead. If you have any scripts that use the **Clear-ActiveSyncDevice** cmdlet, update them to use the **Clear-MobileDevice** cmdlet.
  
```
Clear-ActiveSyncDevice -Identity <MobileDeviceIdParameter> [-Cancel <SwitchParameter>] [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-NotificationEmailAddresses <MultiValuedProperty>] [-WhatIf [<SwitchParameter>]]

```

## Examples
<a name="Examples"> </a>

### Example 1

This example clears all data from the mobile device with the identity WM_JeffHay.
  
```
Clear-ActiveSyncDevice -Identity WM_JeffHay
```

### Example 2

This example clears all data from the mobile device for Tony Smith and sends a confirmation email message to tony@contoso.com.
  
```
Clear-ActiveSyncDevice -Identity WM_TonySmith -NotificationEmailAddresses "tony@contoso.com"
```

### Example 3

This example cancels a previously sent **Clear-ActiveSyncDevice** command request for Tony Smith's mobile device.
  
```
Clear-ActiveSyncDevice -Identity WM_TonySmith -Cancel $true
```

## Detailed Description
<a name="DetailedDescription"> </a>

The **Clear-ActiveSyncDevice** cmdlet deletes all user data from a mobile device the next time the device receives data from the Microsoft Exchange server. This cmdlet sets the _DeviceWipeStatus_ parameter to `$true`. The mobile device acknowledges the cmdlet and records the time stamp in the _DeviceWipeAckTime_ parameter.
  
After you run this cmdlet, you receive a warning that states: "This command will force all the data on the device to be permanently deleted. Do you want to continue?" You must respond to the warning for the cmdlet to run on the mobile phone.
  
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Required  <br/> |Microsoft.Exchange.Configuration.Tasks.MobileDeviceIdParameter  <br/> |The _Identity_ parameter specifies the identity of the device that you want to reset. <br/> |
| _Cancel_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _Cancel_ switch specifies whether the command should be canceled. If you use the _Cancel_ switch, a cancellation request is issued for the remote device wipe. <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |This parameter is available only in on-premises Exchange.  <br/> The _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> |
| _NotificationEmailAddresses_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.MultiValuedProperty  <br/> |The _NotificationEmailAddresses_ parameter specifies the notification email address for the remote device wipe confirmation. <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
