---
title: "Get-QuarantineMessage"
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 1/16/2018
ms.audience: Developer
ms.topic: reference
ms.service: eop
localization_priority: Normal
ms.assetid: 88026da1-8dbc-49e7-80e8-112a32773c34
description: "This cmdlet is available only in the cloud-based service."
---

# Get-QuarantineMessage

This cmdlet is available only in the cloud-based service. 
  
Use the **Get-QuarantineMessage** cmdlet to view quarantined messages in your cloud-based organization.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Get-QuarantineMessage [-Direction <Inbound | Outbound>] [-Domain <String[]>] [-EndExpiresDate <DateTime>] [-EndReceivedDate <DateTime>] [-MessageId <String>] [-MyItems <SwitchParameter>] [-Page <Int32>] [-PageSize <Int32>] [-QuarantineTypes <QuarantineMessageTypeEnum[]>] [-RecipientAddress <String[]>] [-Reported <$true | $false>] [-StartExpiresDate <DateTime>] [-StartReceivedDate <DateTime>] [-Subject <String>] [-Type <Spam | TransportRule | Bulk | Phish | Malware>] <COMMON PARAMETERS>

```

## Examples
<a name="Examples"> </a>

### Example 1

This example returns a summary list of messages quarantined between June 13, 2016 and June 15, 2016.
  
```
Get-QuarantineMessage -StartReceivedDate 06/13/2016 -EndReceivedDate 06/15/2016
```

### Example 2

This example returns the quarantined message with the **Message-ID** value `<5c695d7e-6642-4681-a4b0-9e7a86613cb7@contoso.com>`.
  
```
Get-QuarantineMessage -MessageID <5c695d7e-6642-4681-a4b0-9e7a86613cb7@contoso.com>
```

### Example 3

This example returns detailed information for the quarantined message with the specified **Identity** value.
  
```
Get-QuarantineMessage -Identity c14401cf-aa9a-465b-cfd5-08d0f0ca37c5\4c2ca98e-94ea-db3a-7eb8-3b63657d4db7 | Format-List
```

## Detailed Description
<a name="DetailedDescription"> </a>

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Required  <br/> |Microsoft.Exchange.Management.FfoQuarantine.QuarantineMessageIdentity  <br/> |The  _Identity_ parameter specifies the quarantined message that you want to view. The value is a unique quarantined message identifier in the format `GUID1\GUID2` (for example `c14401cf-aa9a-465b-cfd5-08d0f0ca37c5\4c2ca98e-94ea-db3a-7eb8-3b63657d4db7`.  <br/> When you identify the quarantine message by using this parameter, the **RecipientAddress**, **QuarantineUser**, and **ReleasedUser** properties are available. To see these values, you need to use a formatting cmdlet. For example, `Get-QuarantineMessage -Identity <Identity> | Format-List`.  <br/> |
| _Direction_ <br/> |Optional  <br/> |Microsoft.Exchange.Management.FfoQuarantine.QuarantineMessageDirectionEnum  <br/> |The  _Direction_ parameter filters the results by incoming or outgoing messages. Valid values for this parameter are `Inbound` and `Outbound`.  <br/> |
| _Domain_ <br/> |Optional  <br/> |System.String[]  <br/> |The  _Domain_ parameter filters the results by sender or recipient domain. You can specify multiple domain values separated by commas. <br/> |
| _EndExpiresDate_ <br/> |Optional  <br/> |System.DateTime  <br/> |The  _EndExpiresDate_ parameter specifies the latest messages that will automatically be deleted from the quarantine. Use this parameter with the _StartExpiresDate_ parameter. <br/> Use the short date format that's defined in the **Regional Options** settings on the computer where you're running the command. For example, if the computer is configured to use the short date format _mm_/ _dd_/ _yyyy_, enter 09/01/2015 to specify September 1, 2015. You can enter the date only, or you can enter the date and time of day. If you enter the date and time of day, enclose the value in quotation marks ("), for example,"09/01/2015 5:00 PM".  <br/> For example, if you specify the  _StartExpiresDate_ value of today's date, and the _EndExpiresDate_ value of the date three days from today, you will only see messages that will expire from the quarantine in the next three days. <br/> |
| _EndReceivedDate_ <br/> |Optional  <br/> |System.DateTime  <br/> |The  _EndReceivedDate_ parameter specifies the latest messages to return in the results. Use this parameter with the _StartReceivedDate_ parameter. <br/> Use the short date format that's defined in the **Regional Options** settings on the computer where you're running the command. For example, if the computer is configured to use the short date format _mm_/ _dd_/ _yyyy_, enter 09/01/2015 to specify September 1, 2015. You can enter the date only, or you can enter the date and time of day. If you enter the date and time of day, enclose the value in quotation marks ("), for example,"09/01/2015 5:00 PM".  <br/> |
| _MessageId_ <br/> |Optional  <br/> |System.String  <br/> |The  _MessageId_ parameter filters the results by the `Message-ID` header field of the message. This value is also known as the Client ID. The format of the `Message-ID` depends on the messaging server that sent the message. The value should be unique for each message. However, not all messaging servers create values for the `Message-ID` in the same way. Be sure to include the full Message ID string. This may include angle brackets. <br/> |
| _MyItems_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The  _MyItems_ switch filters the results by messages where you (the user that's running the command) are the recipient. You don't need to specify a value with this switch. <br/> |
| _Page_ <br/> |Optional  <br/> |System.Int32  <br/> |The  _Page_ parameter specifies the page number of the results you want to view. Valid input for this parameter is an integer between 1 and 1000. The default value is 1. <br/> |
| _PageSize_ <br/> |Optional  <br/> |System.Int32  <br/> |The  _PageSize_ parameter specifies the maximum number of entries per page. Valid input for this parameter is an integer between 1 and 1000. The default value is 100. <br/> |
| _QuarantineTypes_ <br/> |Optional  <br/> |Microsoft.Exchange.Management.FfoQuarantine.QuarantineMessageTypeEnum[]  <br/> | The _QuarantineTypes_parameter filters the results by what caused the message to be quarantined. Valid values are:  <br/>  `Bulk` <br/>  `Phish` <br/>  `Spam` <br/>  `TransportRule` <br/>  You can specify multiple values separated by commas. <br/>  You don't need to use this parameter with the _Type_ parameter. <br/> |
| _RecipientAddress_ <br/> |Optional  <br/> |System.String[]  <br/> |The  _RecipientAddress_ parameter filters the results by the recipient's email address. You can specify multiple values separated by commas. <br/> |
| _Reported_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _Reported_ parameter filters the results by messages that have already been reported as false positives. Valid values are: <br/>  `$true`: The command only returns quarantined messages that have already been reported as false positives.  <br/>  `$false`: The command only returns quarantined messages that haven't been reported as false positives.  <br/> |
| _SenderAddress_ <br/> |Optional  <br/> |System.String[]  <br/> |The  _SenderAddress_ parameter filters the results by the sender's email address. You can specify multiple values separated by commas. <br/> |
| _StartExpiresDate_ <br/> |Optional  <br/> |System.DateTime  <br/> |The  _StartExpiresDate_ parameter specifies the earliest messages that will automatically be deleted from the quarantine. Use this parameter with the _EndExpiresDate_ parameter. <br/> Use the short date format that's defined in the **Regional Options** settings on the computer where you're running the command. For example, if the computer is configured to use the short date format _mm_/ _dd_/ _yyyy_, enter 09/01/2015 to specify September 1, 2015. You can enter the date only, or you can enter the date and time of day. If you enter the date and time of day, enclose the value in quotation marks ("), for example,"09/01/2015 5:00 PM".  <br/> For example, if you specify the  _StartExpiresDate_ value of today's date, and the _EndExpiresDate_ value of the date three days from today, you will only see messages that will expire from the quarantine in the next three days. <br/> |
| _StartReceivedDate_ <br/> |Optional  <br/> |System.DateTime  <br/> |The  _StartReceivedDate_ parameter specifies the earliest messages to return in the results. Use this parameter with the _EndReceivedDate_ parameter. <br/> Use the short date format that's defined in the **Regional Options** settings on the computer where you're running the command. For example, if the computer is configured to use the short date format _mm_/ _dd_/ _yyyy_, enter 09/01/2015 to specify September 1, 2015. You can enter the date only, or you can enter the date and time of day. If you enter the date and time of day, enclose the value in quotation marks ("), for example,"09/01/2015 5:00 PM".  <br/> |
| _Subject_ <br/> |Optional  <br/> |System.String  <br/> |The  _Subject_ parameter filters the results by the subject field of the message. If the value contains spaces, enclose the value in quotation marks ("). <br/> |
| _Type_ <br/> |Optional  <br/> |Microsoft.Exchange.Management.FfoQuarantine.QuarantineMessageTypeEnum  <br/> | The _Type_ parameter filters the results by what caused the message to be quarantined. Valid values are: <br/>  `Bulk` <br/>  `Phish` <br/>  `Spam` <br/>  `TransportRule` <br/>  You don't need to use this parameter with the _QuarantineTypes_ parameter. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
