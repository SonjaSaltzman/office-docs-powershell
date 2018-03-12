---
title: "Set-UMCallAnsweringRule"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 82f55e63-5770-433b-9a14-38f350aa5405
description: "This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other."
---

# Set-UMCallAnsweringRule

This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other. 
  
Use the **Set-UMCallAnsweringRule** cmdlet to change properties of an existing UM call answering rule.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Set-UMCallAnsweringRule -Identity <UMCallAnsweringRuleIdParameter> [-CallerIds <MultiValuedProperty>] [-CallersCanInterruptGreeting <$true | $false>] [-CheckAutomaticReplies <$true | $false>] [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-ExtensionsDialed <MultiValuedProperty>] [-KeyMappings <MultiValuedProperty>] [-Mailbox <MailboxIdParameter>] [-Name <String>] [-Priority <Int32>] [-ScheduleStatus <Int32>] [-TimeOfDay <TimeOfDay>] [-WhatIf [<SwitchParameter>]]

```

## Examples
<a name="Examples"> </a>

### Example 1

This example sets the priority to 2 on the existing call answering rule MyCallAnsweringRule that exists in the mailbox for tonysmith.
  
```
Set-UMCallAnsweringRule -Mailbox tonysmith -Name MyCallAnsweringRule -Priority 2
```

### Example 2

This example performs the following actions on the call answering rule MyCallAnsweringRule in the mailbox for tonysmith:
  
- Sets the call answering rule to two caller IDs.
    
- Sets the priority of the call answering rule to 2.
    
- Sets the call answering rule to allow callers to interrupt the greeting.
    
```
Set-UMCallAnsweringRule -Name MyCallAnsweringRule -CallerIds "1,4255550100,,","1,4255550123,," -Priority 2 -CallersCanInterruptGreeting $true -Mailbox tonysmith
```

### Example 3

This example changes the free/busy status to Out of Office on the call answering rule MyCallAnsweringRule in the mailbox for tonysmith and sets the priority to 2.
  
```
Set-UMCallAnsweringRule -Name MyCallAnsweringRule -Priority 2 -Mailbox tonysmith@contoso.com -ScheduleStatus 0x8
```

### Example 4

This example performs the following actions on the call answering rule MyCallAnsweringRule in the mailbox tonysmith:
  
- Sets the priority of the call answering rule to 2.
    
- Creates key mappings for the call answering rule.
    
- If the caller reaches the voice mail for the user and the status of the user is set to Busy, the caller can:
    
- Press the 1 key and be transferred to a receptionist at extension 45678.
    
- Press the 2 key and the Find Me feature will be used for urgent issues and ring extension 23456 first, and then 45671.
    
```
Set-UMCallAnsweringRule -Name MyCallAnsweringRule -Priority 2 -Mailbox tonysmith -ScheduleStatus 0x4 -KeyMappings "1,1,Receptionist,,,,,45678,","5,2,Urgent Issues,23456,23,45671,50,,"
```

### Example 5

This example performs the following actions on the call answering rule MyCallAnsweringRule in the mailbox for tonysmith:
  
- Sets the priority of the call answering rule to 2.
    
- If the caller reaches voice mail during working hours, the caller is asked to call back later.
    
```
Set-UMCallAnsweringRule -Name MyCallAnsweringRule -Priority 2 -Mailbox tonysmith -TimeOfDay "1,0,,"
```

### Example 6

This example sets a custom period for the time of day on the call answering rule MyCallAnsweringRule in the mailbox for tonysmith and performs the following actions:
  
- Sets the priority of the call answering rule to 2.
    
- If the caller reaches voice mail and the time is between 8:00 A.M. and 12:00 P.M. on Tuesday, ask the caller to call back later.
    
```
Set-UMCallAnsweringRule -Name MyCallAnsweringRule -Priority 2 -Mailbox tonysmith -TimeOfDay "3,4,8:00,12:00"
```

## Detailed Description
<a name="DetailedDescription"> </a>

The  _Set-UMCallAnsweringRule_ cmdlet changes the properties of an existing UM call answering rule stored in a UM enabled user's mailbox. You can use the **Set-UMCallAnsweringRule** cmdlet to specify the following conditions:
  
- Who the incoming call is from
    
- Time of day
    
- Calendar free/busy status
    
- Whether automatic replies are turned on for email
    
You can also specify the following actions:
  
- Find me
    
- Transfer the caller to someone else
    
- Leave a voice message
    
After this task is completed, the cmdlet sets the parameters and the values specified.
  
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Required  <br/> |Microsoft.Exchange.Configuration.Tasks.UMCallAnsweringRuleIdParameter  <br/> |The  _Identity_ parameter specifies the identifier for a call answering rule being changed. <br/> |
| _CallerIds_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.MultiValuedProperty  <br/> |The  _CallerIds_ parameter specifies an entry for the "If the Caller is" condition. Each entry for this parameter can contain a phone number, an Active Directory contact, a personal contact, or the personal Contacts folder. The parameter can contain 50 phone numbers or contact entries and no more than one entry for specifying the default Contacts folder. If the _CallerIds_ parameter doesn't contain a condition, the condition isn't set and is ignored. The default value is `$null`.  <br/> |
| _CallersCanInterruptGreeting_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _CallersCanInterruptGreeting_ parameter specifies whether a caller can interrupt the voice mail greeting while it's being played. The default is `$null`.  <br/> |
| _CheckAutomaticReplies_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _CheckAutomaticReplies_ parameter specifies an entry for the "If My Automatic Replies are Enabled" condition. The default is `$false`.  <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |This parameter is available only in on-premises Exchange.  <br/> The  _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> |
| _ExtensionsDialed_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.MultiValuedProperty  <br/> |The  _ExtensionsDialed_ parameter specifies an entry for the "If the Caller Dials" condition. Each entry must be unique per call answering rule. Each extension must correspond to existing extension numbers assigned to UM-enabled users. The default is `$null`.  <br/> |
| _KeyMappings_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.MultiValuedProperty  <br/> |The  _KeyMappings_ parameter specifies a key mapping entry for a call answering rule. The key mappings are those menu options offered to callers if the call answering rule is set to `$true`. You can configure a maximum of 10 entries. None of the defined key mappings can overlap. The default is  `$null`.  <br/> |
| _Mailbox_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.MailboxIdParameter  <br/> |The  _Mailbox_ parameter specifies the UM-enabled mailbox where the call answering rule will be changed. The default is the user's mailbox that's running the cmdlet. <br/> |
| _Name_ <br/> |Optional  <br/> |System.String  <br/> |The  _Name_ parameter specifies the name of the UM call answering rule or Call Answering Rule ID being modified. The call answering ID or name must be unique per the user's UM-enabled mailbox. The name or ID for the call answering rule can contain up to 255 characters. <br/> |
| _Priority_ <br/> |Optional  <br/> |System.Int32  <br/> |The  _Priority_ parameter specified the order that the call answering rule will be evaluated against other existing call answering rules. Call answering rules are processed in order of increasing priority values. The priority must be unique between all call answering rules in the UM-enabled mailbox. The priority on the call answering rule must be between 1 (highest) and 9 (lowest). The default is 9. <br/> |
| _ScheduleStatus_ <br/> |Optional  <br/> |System.Int32  <br/> | The _ScheduleStatus_ parameter specifies an entry for the "If my Schedule show that I am" condition. Users can specify their free/busy status to be checked. This parameter can be set from 0 through 15 and is interpreted as a 4-bit mask that represents the calendar status including Free, Tentative, Busy, and Out of Office. The following settings can be used to set the schedule status: <br/>  None = 0x0 <br/>  Free = 0x1 <br/>  Tentative = 0x2 <br/>  Busy = 0x4 <br/>  OutOfOffice = 0x8 <br/>  The default setting is `$null`.  <br/> |
| _TimeOfDay_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.TimeOfDay  <br/> |The  _TimeOfDay_ parameter specifies an entry for the "If the Call Arrives During" condition for the call answering rule. You can specify working hours, non-working hours, or custom hours. The default is `$null`.  <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The  _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
