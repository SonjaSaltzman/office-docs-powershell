---
title: "Import-ContactList"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/16/2018
ms.audience: Developer
ms.topic: reference
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 2a354fe4-34ed-4f8a-bc21-e092b27e133d
description: "This cmdlet is available only in the cloud-based service."
---

# Import-ContactList

This cmdlet is available only in the cloud-based service. 
  
Use the **Import-ContactList** cmdlet and a .csv file to import a user's mail contacts to a cloud-based mailbox. Users can use an email client to export their contacts to a .csv file that is formatted for Microsoft Office Outlook.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Import-ContactList -CSV <SwitchParameter> -CSVData <Byte[]> -Identity <MailboxIdParameter> <COMMON PARAMETERS>

```

## Examples
<a name="Examples"> </a>

### Example

This example imports a list of contacts in a .csv file named TerryAdams.csv to a mailbox for a user whose email address is terrya@contoso.edu.
  
```
Import-ContactList -CSV -CSVData ([System.IO.File]::ReadAllBytes("D:\Users\Administrator\Desktop\TerryAdams.csv")) -Identity terrya@contoso.edu
```

## Detailed Description
<a name="DetailedDescription"> </a>

The **Import-ContactList** cmdlet submits a request to import a list of mail contacts that are contained in a .csv file to a cloud-based mailbox. Many MAPI and Web-based email clients allow users to export contacts to a Microsoft Office Outlook .csv format. Users can then provide that .csv file to you to import contacts to their cloud-based mailbox. During the import process, Microsoft Exchange matches the column names in the header row of the .csv file to the property names of an Exchange contact.
  
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _CSV_ <br/> |Required  <br/> |System.Management.Automation.SwitchParameter  <br/> |The  _CSV_ parameter simply specifies that the contacts will be imported from a .csv file. <br/> |
| _CSVData_ <br/> |Required  <br/> |System.Byte[]  <br/> |The  _CSVData_ parameter specifies the .csv file you want to import. Use the following syntax for this parameter: `([System.IO.File]::ReadAllBytes("<`file name and path `>"))`. For example,  `([System.IO.File]::ReadAllBytes("C:\`My Documents\Contacts `.csv")).` <br/> |
| _CSVStream_ <br/> |Required  <br/> |System.IO.Stream  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _Identity_ <br/> |Required  <br/> |Microsoft.Exchange.Configuration.Tasks.MailboxIdParameter  <br/> | The _Identity_ parameter specifies the target mailbox to which the contacts are imported. You can use any value that uniquely identifies the mailbox. <br/>  For example: <br/>  Name <br/>  Display name <br/>  Alias <br/>  Distinguished name (DN) <br/>  Canonical DN <br/>  _\<domain name\>_\ _\<account name\>_ <br/>  Email address <br/>  GUID <br/> **LegacyExchangeDN** <br/> **SamAccountName** <br/>  User ID or user principal name (UPN) <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The  _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
