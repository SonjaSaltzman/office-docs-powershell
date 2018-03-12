---
title: "New-HoldComplianceRule"
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 1/25/2018
ms.audience: Developer
ms.topic: reference
ms.service: o365-security-and-compliance
localization_priority: Normal
ms.assetid: e177cc45-e29a-4352-8c4d-dfcc6f9d3b75
description: "This cmdlet is available only in the Office 365 Security &amp; Compliance Center. For more information, see Office 365 Security &amp; Compliance Center PowerShell."
---

# New-HoldComplianceRule

This cmdlet is available only in the Office 365 Security &amp; Compliance Center. For more information, see [Office 365 Security &amp; Compliance Center PowerShell](https://technet.microsoft.com/library/mt587091.aspx). 
  
Use the **New-HoldComplianceRule** cmdlet to create new preservation rules in the Security &amp; Compliance Center.
  
> [!NOTE]
> The **New-HoldComplianceRule** cmdlet has been replaced by the **New-RetentionComplianceRule** cmdlet. If you have any scripts that use the **New-HoldComplianceRule** cmdlet, update them to use the **New-RetentionComplianceRule** cmdlet.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
New-HoldComplianceRule -Name <String> -Policy <PolicyIdParameter> [-Comment <String>] [-ContentDateFrom <DateTime>] [-ContentDateTo <DateTime>] [-ContentMatchQuery <String>] [-Disabled <$true | $false>] [-HoldContent <Unlimited>] [-HoldDurationDisplayHint <Days | Months | Years>] <COMMON PARAMETERS>

```

## Examples
<a name="Examples"> </a>

### Example 1

This example creates a new preservation rule named SeptOneYear and adds it to the existing preservation policy named "Internal Company Policy". Content created or updated between the specified dates will be held indefinitely.
  
```
New-HoldComplianceRule -Name SeptOneYear -Policy "Internal Company Policy" -ContentDateFrom "09/10/14 5:00 PM" -ContentDateTo "09/10/15 5:00 PM" -HoldContent Unlimited
```

## Detailed Description
<a name="DetailedDescription"> </a>

The preservation rule must be added to an existing preservation policy using the  _Policy_ parameter. Only one rule can be added to each preservation policy.
  
You need to be assigned permissions in the Office 365 Security &amp; Compliance Center before you can use this cmdlet. For more information, see [Permissions in Office 365 Security &amp; Compliance Center](https://go.microsoft.com/fwlink/p/?LinkId=511920). 
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Name_ <br/> |Required  <br/> |System.String  <br/> |The  _Name_ parameter specifies a unique name for the preservation rule. If the value contains spaces, enclose the value in quotation marks. <br/> |
| _Policy_ <br/> |Required  <br/> |Microsoft.Office.CompliancePolicy.Tasks.PolicyIdParameter  <br/> |The  _Policy_ parameter specifies the policy to contain the rule. <br/> |
| _Comment_ <br/> |Optional  <br/> |System.String  <br/> |The  _Comment_ parameter specifies an optional comment. If you specify a value that contains spaces, enclose the value in quotation marks ("), for example: `"This is an admin note"`.  <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _ContentDateFrom_ <br/> |Optional  <br/> |System.DateTime  <br/> |The  _ContentDateFrom_ parameter specifies the start date of the date range for content to include. <br/> Use the short date format that's defined in the **Regional Options** settings on the computer where you're running the command. For example, if the computer is configured to use the short date format _mm_/ _dd_/ _yyyy_, enter 09/01/2015 to specify September 1, 2015. You can enter the date only, or you can enter the date and time of day. If you enter the date and time of day, enclose the value in quotation marks ("), for example,"09/01/2015 5:00 PM".  <br/> |
| _ContentDateTo_ <br/> |Optional  <br/> |System.DateTime  <br/> |The  _ContentDateTo_ parameter specifies the end date of the date range for content to include. <br/> Use the short date format that's defined in the **Regional Options** settings on the computer where you're running the command. For example, if the computer is configured to use the short date format _mm_/ _dd_/ _yyyy_, enter 09/01/2015 to specify September 1, 2015. You can enter the date only, or you can enter the date and time of day. If you enter the date and time of day, enclose the value in quotation marks ("), for example,"09/01/2015 5:00 PM".  <br/> |
| _ContentMatchQuery_ <br/> |Optional  <br/> |System.String  <br/> |The  _ContentMatchQuery_ parameter specifies a content search filter. <br/> This parameter uses a text search string or a query that's formatted by using the Keyword Query Language (KQL). For more information about KQL, see [Keyword Query Language syntax reference](https://go.microsoft.com/fwlink/?LinkId=269603).  <br/> |
| _Disabled_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _Disabled_ parameter specifies whether the preservation rule is enabled or disabled. Valid input for this parameter is `$true` or `$false`. The default value is  `$false`.  <br/> |
| _HoldContent_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Unlimited  <br/> | The _HoldContent_ parameter specifies the hold duration for the preservation rule. Valid values are: <br/>  _An integer_: The hold duration in days.  <br/>  `Unlimited`: The content is held indefinitely.  <br/> |
| _HoldDurationDisplayHint_ <br/> |Optional  <br/> |Microsoft.Office.CompliancePolicy.PolicyEvaluation.HoldDurationHint  <br/> | The _HoldDurationDisplayHint_ parameter specifies the units that are used to display the preservation duration in the Security &amp; Compliance Center. Valid values are: <br/>  `Days` <br/>  `Months` <br/>  `Years` <br/>  For example, if this parameter is set to the value `Years`, and the  _HoldContent_ parameter is set to the value `365`, the Security &amp; Compliance Center will display **1 year** as the content hold duration. <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
