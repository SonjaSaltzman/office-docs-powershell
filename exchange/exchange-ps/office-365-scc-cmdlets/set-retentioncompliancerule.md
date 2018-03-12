---
title: "Set-RetentionComplianceRule"
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 1/12/2018
ms.audience: Developer
ms.topic: reference
ms.service: o365-security-and-compliance
localization_priority: Normal
ms.assetid: ad2b541a-4168-4b5b-868d-3e2e42042e2d
description: "This cmdlet is available only in the Office 365 Security &amp; Compliance Center. For more information, see Office 365 Security &amp; Compliance Center PowerShell."
---

# Set-RetentionComplianceRule

This cmdlet is available only in the Office 365 Security &amp; Compliance Center. For more information, see [Office 365 Security &amp; Compliance Center PowerShell](https://technet.microsoft.com/library/mt587091.aspx). 
  
Use the **Set-RetentionComplianceRule** cmdlet to modify existing retention rules in the Security &amp; Compliance Center.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Set-RetentionComplianceRule -Identity <ComplianceRuleIdParameter> <COMMON PARAMETERS>

```

## Examples
<a name="Examples"> </a>

### Example 1

This example changes the hold duration for the existing retention rule named "Internal Company Rule".
  
```
Set-RetentionComplianceRule -Identity "Internal Company Rule" -RetentionDuration 180 RetentionDurationDisplayHint Days
```

## Detailed Description
<a name="DetailedDescription"> </a>

You need to be assigned permissions in the Office 365 Security &amp; Compliance Center before you can use this cmdlet. For more information, see [Permissions in Office 365 Security &amp; Compliance Center](https://go.microsoft.com/fwlink/p/?LinkId=511920). 
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Required  <br/> |Microsoft.Office.CompliancePolicy.Tasks.ComplianceRuleIdParameter  <br/> | The _Identity_ parameter specifies the retention rule that you want to modify. You can use any value that uniquely identifies the rule. For example: <br/>  Name <br/>  Distinguished name (DN) <br/>  GUID <br/> |
| _ApplyComplianceTag_ <br/> |Optional  <br/> |System.String  <br/> |The  _ApplyComplianceTag_ parameter specifies the label that's applied to email messages or documents by the rule (which affects how long the content is retained). A valid value for this parameter is the name of an existing label. If the value contains spaces, enclose the value in quotation marks. <br/>  You view and create labels by using the **Get-ComplianceTag** and **New-ComplianceTag** cmdlets. <br/> You can't use this parameter with the  _Name_ or _PublishComplianceTag_ parameters. <br/> |
| _Comment_ <br/> |Optional  <br/> |System.String  <br/> |The  _Comment_ parameter specifies an optional comment. If you specify a value that contains spaces, enclose the value in quotation marks ("), for example: `"This is an admin note"`.  <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _ContentContainsSensitiveInformation_ <br/> |Optional  <br/> |Microsoft.Office.CompliancePolicy.Tasks.PswsHashtable[]  <br/> |The  _ContentContainsSensitiveInformation_ parameter specifies a condition for the rule that's based on a sensitive information type match in content. The rule is applied to content that contains the specified sensitive information type. <br/> This parameter uses the basic syntax  `@(@{Name="<SensitiveInformationType1>";[minCount="<Value>"],@{Name="<SensitiveInformationType2>";[minCount="<Value>"],...)`. For example,  `@(@{Name="U.S. Social Security Number (SSN)"; minCount="2"},@{Name="Credit Card Number"})`.  <br/> Use the **Get-DLPSensitiveInformationType** cmdlet to list the sensitive information types for your organization. For more information on sensitive information types, see[Sensitive information types inventory](https://go.microsoft.com/fwlink/p/?LinkId=529420).  <br/> |
| _ContentDateFrom_ <br/> |Optional  <br/> |System.DateTime  <br/> |The  _ContentDateFrom_ parameter specifies the start date of the date range for content to include. <br/> Use the short date format that's defined in the **Regional Options** settings on the computer where you're running the command. For example, if the computer is configured to use the short date format _mm_/ _dd_/ _yyyy_, enter 09/01/2015 to specify September 1, 2015. You can enter the date only, or you can enter the date and time of day. If you enter the date and time of day, enclose the value in quotation marks ("), for example,"09/01/2015 5:00 PM".  <br/> |
| _ContentDateTo_ <br/> |Optional  <br/> |System.DateTime  <br/> |The  _ContentDateTo_ parameter specifies the end date of the date range for content to include. <br/> Use the short date format that's defined in the **Regional Options** settings on the computer where you're running the command. For example, if the computer is configured to use the short date format _mm_/ _dd_/ _yyyy_, enter 09/01/2015 to specify September 1, 2015. You can enter the date only, or you can enter the date and time of day. If you enter the date and time of day, enclose the value in quotation marks ("), for example,"09/01/2015 5:00 PM".  <br/> |
| _ContentMatchQuery_ <br/> |Optional  <br/> |System.String  <br/> |The  _ContentMatchQuery_ parameter specifies a content search filter. <br/> This parameter uses a text search string or a query that's formatted by using the Keyword Query Language (KQL). For more information about KQL, see [Keyword Query Language syntax reference](https://go.microsoft.com/fwlink/?LinkId=269603).  <br/> |
| _ExcludedItemClasses_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.MultiValuedProperty  <br/> | The _ExcludedItemClasses_ parameter specifies the types of messages to exclude from the rule. You can use this parameter only to exclude items from a hold policy, which excludes the specified item class from being held. Using this parameter won't exclude items from deletion policies. Typically, you use this parameter to exclude voicemail messages, IM conversations, and other Skype for Business Online content from being held by a hold policy. Common Skype for Business values include: <br/>  `IPM.Note.Microsoft.Conversation` <br/>  `IPM.Note.Microsoft.Conversation.Voice` <br/>  `IPM.Note.Microsoft.Missed` <br/>  `IPM.Note.Microsoft.Missed.Voice` <br/>  `IPM.Note.Microsoft.Voicemail` <br/>  `IPM.Note.Microsoft.VoiceMessage.UA` <br/>  `IPM.Note.Microsoft.Voicemail.UM` <br/>  `IPM.Note.Microsoft.Voicemail.UM.CA` <br/>  You can specify multiple item class values by using the syntax `"Value1","Value2"...`.  <br/> |
| _ExpirationDateOption_ <br/> |Optional  <br/> |System.String  <br/> | The _ExpirationDateOption_parameter specifies whether the expiration date is calculated from the content creation date or last modification date. Valid values are:  <br/>  `CreationAgeInDays` <br/>  `ModificationAgeInDays` <br/> |
| _RetentionComplianceAction_ <br/> |Optional  <br/> |System.String  <br/> | The _RetentionComplianceAction_parameter specifies the retention action for the rule. Valid values are:  <br/>  `Delete` <br/>  `Keep` <br/>  `KeepAndDelete` <br/> |
| _RetentionDuration_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Unlimited  <br/> | The _RetentionDuration_ parameter specifies the hold duration for the retention rule. Valid values are: <br/>  _An integer_: The hold duration in days.  <br/>  `Unlimited`: The content is held indefinitely.  <br/> |
| _RetentionDurationDisplayHint_ <br/> |Optional  <br/> |Microsoft.Office.CompliancePolicy.PolicyEvaluation.HoldDurationHint  <br/> | The _RetentionDurationDisplayHint_ parameter specifies the units that are used to display the retention duration in the Security &amp; Compliance Center. Valid values are `Days`,  `Months` or `Years`.  <br/>  `Days` <br/>  `Months` <br/>  `Years` <br/>  For example, if this parameter is set to the value `Years`, and the  _RetentionDuration_ parameter is set to the value `365`, the Security &amp; Compliance Center will display **1 year** as the content hold duration. <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
