---
title: "New-ConnectSubscription"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 3c2ea368-e6c0-41f8-9509-8a54c268e0a3
description: "This cmdlet is available only in the cloud-based service."
---

# New-ConnectSubscription

This cmdlet is available only in the cloud-based service. 
  
The **New-ConnectSubscription** cmdlet allows a user to create contact integration subscriptions between supported services (for example, Facebook or LinkedIn) and their own cloud-based mailbox. An administrator can't use this cmdlet to create subscriptions in another user's mailbox.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
New-ConnectSubscription -AppAuthorizationCode <String> -Facebook <SwitchParameter> -RedirectUri <String> <COMMON PARAMETERS>

```

## Examples
<a name="Examples"> </a>

### Example 1

This example modifies a people connection to LinkedIn.
  
```
New-ConnectSubscription -LinkedIn $true -OAuthVerifier <OAuthVerifyer value> -RequestSecret <Request Secret value> -RequestToken <Request Token value>
```

## Detailed Description
<a name="DetailedDescription"> </a>

When you set up a contact subscription, contacts from the external networking service are integrated into your cloud-based mailbox.
  
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _AppAuthorizationCode_ <br/> |Required  <br/> |System.String  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _Facebook_ <br/> |Required  <br/> |System.Management.Automation.SwitchParameter  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _LinkedIn_ <br/> |Required  <br/> |System.Management.Automation.SwitchParameter  <br/> |The  _LinkedIn_ parameter specifies whether you want to edit a LinkedIn subscription. <br/> |
| _Mailbox_ <br/> |Required  <br/> |Microsoft.Exchange.Configuration.Tasks.MailboxIdParameter  <br/> | The _Mailbox_ parameter specifies the cloud-based mailbox that will contain the subscription. You can use any value that uniquely identifies the mailbox. <br/>  For example: <br/>  Name <br/>  Display name <br/>  Alias <br/>  Distinguished name (DN) <br/>  Canonical DN <br/>  _\<domain name\>_\ _\<account name\>_ <br/>  Email address <br/>  GUID <br/> **LegacyExchangeDN** <br/> **SamAccountName** <br/>  User ID or user principal name (UPN) <br/> |
| _OAuthVerifier_ <br/> |Required  <br/> |System.String  <br/> |The  _OAuthVerifier_ parameter specifies the verification code associated with the request token. You must provide a value for the _OAuthVerifier_ parameter and the _RequestToken_ parameter values in exchange for an access token. <br/> |
| _RedirectUri_ <br/> |Required  <br/> |System.String  <br/> |The  _RedirectUri_ parameter specifies the host name used to connect to the Exchange server from outside the firewall. <br/> |
| _RequestSecret_ <br/> |Required  <br/> |System.String  <br/> |The  _RequestSecret_ parameter specifies the secret associated with the access token. <br/> |
| _RequestToken_ <br/> |Required  <br/> |System.String  <br/> |The  _RequestToken_ parameter specifies the access token that provides access to protected resources accessible through LinkedIn. You must provide a value for the _OAuthVerifier_ parameter and the _RequestToken_ parameter values in exchange for an access token. <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The  _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
