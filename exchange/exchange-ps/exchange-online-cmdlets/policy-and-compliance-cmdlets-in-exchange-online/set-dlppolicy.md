---
title: "Set-DlpPolicy"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/16/2018
ms.audience: Developer
ms.topic: reference
ms.service: exchange-online
localization_priority: Normal
ms.assetid: f44e276c-b9cb-4bfc-a815-ab866446ffdd
description: "This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other."
---

# Set-DlpPolicy

This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other. 
  
Use the **Set-DlpPolicy** cmdlet to modify data loss prevention (DLP) policies in your organization.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Set-DlpPolicy -Identity <DlpPolicyIdParameter> [-Confirm [<SwitchParameter>]] [-Description <String>] [-DomainController <Fqdn>] [-Mode <Audit | AuditAndNotify | Enforce>] [-Name <String>] [-State <Enabled | Disabled>] [-WhatIf [<SwitchParameter>]]

```

## Examples
<a name="Examples"> </a>

### Example 1

This example disables the DLP policy named Employee Numbers.
  
```
Set-DlpPolicy "Employee Numbers" -State Disabled
```

## Detailed Description
<a name="DetailedDescription"> </a>

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Required  <br/> |Microsoft.Exchange.MessagingPolicies.CompliancePrograms.Tasks.DlpPolicyIdParameter  <br/> |The  _Identity_ parameter specifies the DLP policy you want to modify. You can use any value that uniquely identifies the DLP policy. For example, you can specify the name, GUID, or distinguished name (DN) of the DLP policy. <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _Description_ <br/> |Optional  <br/> |System.String  <br/> |The  _Description_ parameter specifies an optional description for the DLP policy. <br/> |
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |This parameter is available only in on-premises Exchange.  <br/> The  _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> |
| _Mode_ <br/> |Optional  <br/> |Microsoft.Exchange.MessagingPolicies.Rules.RuleMode  <br/> | The _Mode_ parameter specifies the action and notification level of the DLP policy. Valid values for this parameter are: <br/>  `Audit`: When a message matches the conditions specified by the DLP policy, the actions specified by the policy aren't enforced, and no notification emails are sent.  <br/>  `AuditAndNotify`: When a message matches the conditions specified by the DLP policy, the actions specified by the policy aren't enforced, but notification emails are sent.  <br/>  `Enforce`: When a message matches the conditions specified by the DLP policy, the actions specified by the policy are enforced, and notification emails are sent.  <br/>  If the _State_ parameter is set to `Disabled`, the value of the  _Mode_ parameter is irrelevant. <br/> |
| _Name_ <br/> |Optional  <br/> |System.String  <br/> |The  _Name_ parameter specifies a unique name for the DLP policy. <br/> |
| _State_ <br/> |Optional  <br/> |Microsoft.Exchange.MessagingPolicies.Rules.RuleState  <br/> |The  _State_ parameter enables or disables the DLP policy. Valid input for this parameter is `Enabled` or `Disabled`.  <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The  _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
