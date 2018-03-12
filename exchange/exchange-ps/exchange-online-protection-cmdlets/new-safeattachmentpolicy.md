---
title: "New-SafeAttachmentPolicy"
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 1/12/2018
ms.audience: Developer
ms.topic: reference
ms.service: eop
localization_priority: Normal
ms.assetid: ef3b8cad-176b-485f-833d-73cba4cfa3f3
description: "This cmdlet is available only in the cloud-based service."
---

# New-SafeAttachmentPolicy

This cmdlet is available only in the cloud-based service. 
  
Use the **New-SafeAttachmentPolicy** cmdlet to create Safe Attachments policies in your cloud-based organization.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
New-SafeAttachmentPolicy -Name <String> [-Action <Block | Replace | Allow | DynamicDelivery>] [-ActionOnError <$true | $false>] [-AdminDisplayName <String>] [-Confirm [<SwitchParameter>]] [-Enable <$true | $false>] [-Redirect <$true | $false>] [-RedirectAddress <SmtpAddress>] [-WhatIf [<SwitchParameter>]]

```

## Examples
<a name="Examples"> </a>

### Example 1

This example creates a new Safe Attachments policy named Marketing Block Attachments with the following options:
  
- The policy is enabled.
    
- The action is  `Block`. This is the default value of the  _Action_ parameter, so you don't need to specify it.
    
- If Safe Attachments scanning isn't available or encounters errors, deliver the message as normal. The default value of the  _ActionOnError_ parameter is `$false`, so you don't need to specify it.
    
- Redirect detected malware messages to admin@contoso.com.
    
```
New-SafeAttachmentPolicy -Name "Marketing Block Attachments" -Enable $true -Redirect $true -RedirectAddress admin@contoso.com
```

## Detailed Description
<a name="DetailedDescription"> </a>

New Safe Attachments policies aren't valid and aren't applied until you add a Safe Attachments rule to the policy by using the **New-SafeAttachmentRule** cmdlet.
  
Safe Attachments is a feature in Advanced Threat Protection that opens email attachments in a special hypervisor environment to detect malicious activity. 
  
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx). 
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Name_ <br/> |Required  <br/> |System.String  <br/> |The  _Name_ parameter specifies a unique name for the Safe Attachments policy. If the value contains spaces, enclose the value in quotation marks ("). <br/> |
| _Action_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Directory.SystemConfiguration.SafeAttachmentAction  <br/> | The _Action_parameter specifies the action for the Safe Attachments policy. Valid values are:  <br/>  `Allow`: Deliver the email message, including the malware attachment.  <br/>  `Block`: Block the email message that contains the malware attachment. This is the default value.  <br/>  `Replace`: Deliver the email message, but remove the malware attachment and replace it with warning text.  <br/>  The results of all actions are available in message trace. <br/> |
| _ActionOnError_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _ActionOnError_ parameter specifies the error handling option for Safe Attachments scanning (what to do if scanning times out or an error occurs). Valid values are: <br/>  `$true`: The action specified by the  _Action_ parameter is applied to messages even when the attachments aren't successfully scanned. <br/>  `$false`: The action specified by the  _Action_ parameter isn't applied to messages when the attachments aren't successfully scanned. This is the default value. <br/> |
| _AdminDisplayName_ <br/> |Optional  <br/> |System.String  <br/> |The  _AdminDisplayName_parameter specifies a description for the policy. If the value contains spaces, enclose the value in quotation marks (").  <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _Enable_ <br/> |Optional  <br/> |System.Boolean  <br/> | This parameter specifies whether the rule or policy is enabled. Valid values are: <br/>  `$true`: The rule or policy is enabled.  <br/>  `$false`: The rule or policy is disabled.  <br/>  The default value is `$false`.  <br/> |
| _Redirect_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _Redirect_ parameter specifies whether to send detected malware attachments to another email address. Valid values are: <br/>  `$true`: Malware attachments are sent to the email address specified by the  _RedirectAddress_ parameter. <br/>  `$false`: Malware attachments aren't sent to another email address. This is the default value.  <br/> |
| _RedirectAddress_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.SmtpAddress  <br/> |The  _RedirectAddress_parameter specifies the email address where detected malware attachments are sent when the  _Redirect_ parameter is set to the value `$true`.  <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The  _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
