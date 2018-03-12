---
title: "Set-CASMailbox"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/16/2018
ms.audience: Developer
ms.topic: reference
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ff7d4dc5-755e-4005-a0a3-631eed3f9b3b
description: "This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other."
---

# Set-CASMailbox

This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other. 
  
Use the **Set-CASMailbox** cmdlet to configure client access settings on a mailbox. For example, you can configure settings for Exchange ActiveSync, Outlook, Outlook on the web, POP3, and IMAP4.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Set-CASMailbox -Identity <MailboxIdParameter> [-ActiveSyncAllowedDeviceIDs <MultiValuedProperty>] [-ActiveSyncBlockedDeviceIDs <MultiValuedProperty>] [-ActiveSyncDebugLogging <$true | $false>] [-ActiveSyncEnabled <$true | $false>] [-ActiveSyncMailboxPolicy <MailboxPolicyIdParameter>] [-ActiveSyncSuppressReadReceipt <$true | $false>] [-Confirm [<SwitchParameter>]] [-DisplayName <String>] [-DomainController <Fqdn>] [-ECPEnabled <$true | $false>] [-EmailAddresses <ProxyAddressCollection>] [-EwsAllowEntourage <$true | $false>] [-EwsAllowList <MultiValuedProperty>] [-EwsAllowMacOutlook <$true | $false>] [-EwsAllowOutlook <$true | $false>] [-EwsApplicationAccessPolicy <EnforceAllowList | EnforceBlockList>] [-EwsBlockList <MultiValuedProperty>] [-EwsEnabled <$true | $false>] [-IgnoreDefaultScope <SwitchParameter>] [-ImapEnabled <$true | $false>] [-ImapEnableExactRFC822Size <$true | $false>] [-ImapForceICalForCalendarRetrievalOption <$true | $false>] [-ImapMessagesRetrievalMimeFormat <TextOnly | HtmlOnly | HtmlAndTextAlternative | TextEnrichedOnly | TextEnrichedAndTextAlternative | BestBodyFormat | Tnef>] [-ImapSuppressReadReceipt <$true | $false>] [-ImapUseProtocolDefaults <$true | $false>] [-IsOptimizedForAccessibility <$true | $false>] [-MAPIBlockOutlookExternalConnectivity <$true | $false>] [-MAPIBlockOutlookNonCachedMode <$true | $false>] [-MAPIBlockOutlookRpcHttp <$true | $false>] [-MAPIBlockOutlookVersions <String>] [-MAPIEnabled <$true | $false>] [-MapiHttpEnabled <$true | $false>] [-Name <String>] [-OWAEnabled <$true | $false>] [-OWAforDevicesEnabled <$true | $false>] [-OwaMailboxPolicy <MailboxPolicyIdParameter>] [-PopEnabled <$true | $false>] [-PopEnableExactRFC822Size <$true | $false>] [-PopForceICalForCalendarRetrievalOption <$true | $false>] [-PopMessagesRetrievalMimeFormat <TextOnly | HtmlOnly | HtmlAndTextAlternative | TextEnrichedOnly | TextEnrichedAndTextAlternative | BestBodyFormat | Tnef>] [-PopSuppressReadReceipt <$true | $false>] [-PopUseProtocolDefaults <$true | $false>] [-PrimarySmtpAddress <SmtpAddress>] [-ResetAutoBlockedDevices <SwitchParameter>] [-SamAccountName <String>] [-ShowGalAsDefaultView <$true | $false>] [-UniversalOutlookEnabled <$true | $false>] [-WhatIf [<SwitchParameter>]]

```

## Examples
<a name="Examples"> </a>

### Example 1

This example disables Outlook on the web and POP3 access for the user adam@contoso.com.
  
```
Set-CASMailbox adam@contoso.com -OWAEnabled $false -PopEnabled $false
```

### Example 2

This example enables Exchange ActiveSync debug logging and specifies the Exchange ActiveSync mailbox policy named Management for the user adam@contoso.com.
  
```
Set-CASMailbox adam@contoso.com -ActiveSyncDebugLogging $true -ActiveSyncMailboxPolicy Management
```

### Example 3

This example sets the display name and disables Outlook Anywhere access for the user tony@contoso.com.
  
```
Set-CASMailbox tony@contoso.com -DisplayName "Tony Smith" -MAPIBlockOutlookRpcHttp $true
```

## Detailed Description
<a name="DetailedDescription"> </a>

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Required  <br/> |Microsoft.Exchange.Configuration.Tasks.MailboxIdParameter  <br/> | The _Identity_ parameter specifies the mailbox that you want to configure. You can use any value that uniquely identifies the mailbox. <br/>  For example: <br/>  Name <br/>  Display name <br/>  Alias <br/>  Distinguished name (DN) <br/>  Canonical DN <br/>  _\<domain name\>_\ _\<account name\>_ <br/>  Email address <br/>  GUID <br/> **LegacyExchangeDN** <br/> **SamAccountName** <br/>  User ID or user principal name (UPN) <br/> |
| _ActiveSyncAllowedDeviceIDs_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.MultiValuedProperty  <br/> |The _ActiveSyncAllowedDeviceIDs_ parameter specifies one or more Exchange ActiveSync device IDs that are allowed to synchronize with the mailbox. A device ID is a text string that uniquely identifies the device. Use the **Get-MobileDevice** cmdlet to see the devices that have Exchange ActiveSync partnerships with the mailbox. <br/> To enter multiple values and overwrite any existing entries, use the following syntax:  `<value1>,<value2>...`. If the values contain spaces or otherwise require quotation marks, you need to use the following syntax:  `"<value1>","<value2>"...`.  <br/> To add or remove one or more values without affecting any existing entries, use the following syntax:  `@{Add="<value1>","<value2>"...; Remove="<value1>","<value2>"...}`.  <br/> To clear the list of device IDs, use the value  `$null` for this parameter. <br/> |
| _ActiveSyncBlockedDeviceIDs_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.MultiValuedProperty  <br/> |The  _ActiveSyncBlockedDeviceIDs_ parameter specifies one or more Exchange ActiveSync device IDs that aren't allowed to synchronize with the mailbox. A device ID is a text string that uniquely identifies the device. Use the **Get-MobileDevice** cmdlet to see the devices that have Exchange ActiveSync partnerships with the mailbox. <br/> To enter multiple values and overwrite any existing entries, use the following syntax:  `<value1>,<value2>...`. If the values contain spaces or otherwise require quotation marks, you need to use the following syntax:  `"<value1>","<value2>"...`.  <br/> To add or remove one or more values without affecting any existing entries, use the following syntax:  `@{Add="<value1>","<value2>"...; Remove="<value1>","<value2>"...}`.  <br/> To clear the list of device IDs, use the value  `$null` for this parameter. <br/> |
| _ActiveSyncDebugLogging_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _ActiveSyncDebugLogging_ parameter enables or disables Exchange ActiveSync debug logging for the mailbox. Valid input for this parameter is `$true` or `$false`. The default value is  `$false`.  <br/> This parameter is primarily for troubleshooting and will revert to $false in 48 hours for Exchange Online, and in 72 hours for Exchange Server.  <br/> |
| _ActiveSyncEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _ActiveSyncEnabled_ parameter enables or disables Exchange ActiveSync for the mailbox. Valid input for this parameter is `$true` or `$false`. The default value is  `$true`. When you set this parameter to  `$false`, the other Exchange ActiveSync settings in this cmdlet are ignored.  <br/> |
| _ActiveSyncMailboxPolicy_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.MailboxPolicyIdParameter  <br/> | The _ActiveSyncMailboxPolicy_ parameter specifies the Exchange ActiveSync mailbox policy for the mailbox. You can use any value that uniquely identifies the Exchange ActiveSync mailbox policy. For example: <br/>  Name <br/>  Distinguished name (DN) <br/>  GUID <br/>  The name of the default Exchange ActiveSync mailbox policy is `Default`.  <br/> |
| _ActiveSyncSuppressReadReceipt_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _ActiveSyncSuppressReadReceipt_ parameter controls the behavior of read receipts for Exchange ActiveSync clients that access the mailbox. Valid values are: <br/>  `$true`: The user receives a read receipt when the recipient opens the message.  <br/>  `$false`: The user receives two read receipts: one when the message is downloaded and another when the message is opened. This is the default value.  <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _DisplayName_ <br/> |Optional  <br/> |System.String  <br/> |This parameter is available only in on-premises Exchange.  <br/> The  _DisplayName_ parameter specifies the display name of the mailbox. The display name is visible in the Exchange admin center and in address lists. The maximum length is 256 characters. If the value contains spaces, enclose the value in quotation marks ("). <br/> |
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |This parameter is available only in on-premises Exchange.  <br/> The  _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> |
| _ECPEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> |This parameter is available only in on-premises Exchange.  <br/> The  _ECPEnabled_ parameter enables or disables access to the Exchange admin center (EAC) for the specified user. Valid input for this parameter is `$true` or `$false`. The default value is  `$true`.  <br/> |
| _EmailAddresses_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.ProxyAddressCollection  <br/> | This parameter is available only in on-premises Exchange. <br/>  The _EmailAddresses_ parameter specifies all the email addresses (proxy addresses) for the recipient, including the primary SMTP address. In on-premises Exchange organizations, the primary SMTP address and other proxy addresses are typically set by email address policies. However, you can use this parameter to configure other proxy addresses for the recipient. For more information, see[Email address policies in Exchange 2016](https://technet.microsoft.com/library/bb232171.aspx).  <br/>  Valid syntax for this parameter is `<Type>:<emailaddress1>,<Type>:<emailaddress2>...`. The optional  _\<Type\>_ value specifies the type of email address. Some examples of valid values include: <br/>  `SMTP`: The primary SMTP address. You can use this value only once in a command.  <br/>  `smtp`: Other SMTP email addresses.  <br/>  `X400`: X.400 addresses in on-premises Exchange.  <br/>  `X500`: X.500 addresses in on-premises Exchange.  <br/>  If you don't include a _\<Type\>_ value for an email address, the value `smtp` is assumed. Note that Exchange doesn't validate the syntax of custom address types (including X.400 addresses). Therefore, you need to verify that any custom addresses are formatted correctly. <br/>  To specify the primary SMTP email address, you can use any of the following methods: <br/>  Use the _\<Type\>_ value `SMTP` on the address. <br/>  The first email address when you don't use any _\<Type\>_ values, or when you use multiple _\<Type\>_ values of `smtp`.  <br/>  If it's available, use the _PrimarySmtpAddress_ parameter instead. You can't use the _EmailAddresses_ parameter and the _PrimarySmtpAddress_ parameter in the same command. <br/>  To replace all existing proxy email addresses with the values you specify, use the following syntax: `"<Type>:<emailaddress1>","<Type>:<emailaddress2>"...`.  <br/>  To add or remove specify proxy addresses without affecting other existing values, use the following syntax: `@{Add="<Type>:<emailaddress1>","<Type>:<emailaddress2>"...; Remove="<Type>:<emailaddress2>","<Type>:<emailaddress2>"...}`.  <br/> |
| _EwsAllowEntourage_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _EwsAllowEntourage_ parameter enables or disables access to the mailbox by Microsoft Entourage clients that use Exchange Web Services (for example, Entourage 2008 for Mac, Web Services Edition). <br/> Valid input for this parameter is  `$true` or `$false`. The default value is  `$true`.  <br/> |
| _EwsAllowList_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.MultiValuedProperty  <br/> |The  _EwsAllowList_ parameter specifies the Exchange Web Services applications (user agent strings) that are allowed to access the mailbox. <br/> To enter multiple values and overwrite any existing entries, use the following syntax:  `<value1>,<value2>...`. If the values contain spaces or otherwise require quotation marks, you need to use the following syntax:  `"<value1>","<value2>"...`.  <br/> To add or remove one or more values without affecting any existing entries, use the following syntax:  `@{Add="<value1>","<value2>"...; Remove="<value1>","<value2>"...}`.  <br/> This parameter is meaningful only when the  _EwsEnabled_ parameter is set to `$true`, and the  _EwsApplicationAccessPolicy_ parameter is set to `EnforceAllowList`.  <br/> |
| _EwsAllowMacOutlook_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _EwsAllowMacOutlook_ parameter enables or disables access to the mailbox by Outlook for Mac clients that use Exchange Web Services (for example, Outlook for Mac 2011 or later). <br/> Valid input for this parameter is  `$true` or `$false`. The default value is  `$true`.  <br/> |
| _EwsAllowOutlook_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _EwsAllowOutlook_ parameter enables or disables access to the mailbox by Outlook clients that use Exchange Web Services. Outlook uses Exchange Web Services for free/busy, out-of-office settings, and calendar sharing. <br/> |
| _EwsApplicationAccessPolicy_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Directory.EwsApplicationAccessPolicy  <br/> | The _EwsApplicationAccessPolicy_ parameter controls access to the mailbox by using Exchange Web Services applications. <br/>  Valid values for this parameter are: <br/>  `EnforceAllowList`: Only applications specified in the  _EwsAllowList_ parameter are allowed to access the mailbox. <br/>  `EnforceBlockList`: Applications specified in the  _EwsBlockList_ parameter aren't allowed to access the mailbox, but any other applications can access the mailbox. <br/>  This parameter doesn't affect access to the mailbox by using Entourage, Outlook for Mac, and Outlook. Access to the mailbox by using these clients is controlled by the _EwsAllowEntourage_,  _EwsAllowMacOutlook_ and _EwsAllowOutlook_ parameters. <br/> |
| _EwsBlockList_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.MultiValuedProperty  <br/> |The  _EwsBlockList_ parameter specifies the Exchange Web Services applications (user agent strings) that aren't allowed to access the mailbox by using Exchange Web Services. <br/> To enter multiple values and overwrite any existing entries, use the following syntax:  `<value1>,<value2>...`. If the values contain spaces or otherwise require quotation marks, you need to use the following syntax:  `"<value1>","<value2>"...`.  <br/> To add or remove one or more values without affecting any existing entries, use the following syntax:  `@{Add="<value1>","<value2>"...; Remove="<value1>","<value2>"...}`.  <br/> This parameter is meaningful only when the  _EwsEnabled_ parameter is set to `$true`, and the  _EwsApplicationAccessPolicy_ parameter is set to `EnforceBlockList`.  <br/> |
| _EwsEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _EwsEnabled_ parameter enables or disables access to the mailbox by using Exchange Web Services clients. <br/> Valid input for this parameter is  `$true` or `$false`. The default value is  `$true`. Note that when you set this parameter to  `$false`, the other Exchange Web Services settings in this cmdlet are ignored.  <br/> |
| _IgnoreDefaultScope_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | This parameter is available only in on-premises Exchange. <br/>  The _IgnoreDefaultScope_ switch tells the command to ignore the default recipient scope setting for the Exchange Management Shell session, and to use the entire forest as the scope. This allows the command to access Active Directory objects that aren't currently available in the default scope. <br/>  Using the _IgnoreDefaultScope_ switch introduces the following restrictions: <br/>  You can't use the _DomainController_ parameter. The command uses an appropriate global catalog server automatically. <br/>  You can only use the DN for the _Identity_ parameter. Other forms of identification, such as alias or GUID, aren't accepted. <br/> |
| _ImapEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _ImapEnabled_ parameter enables or disables access to the mailbox by using IMAP4 clients. <br/> Valid input for this parameter is  `$true` or `$false`. The default value is  `$true`. Note that when you set this parameter to  `$false`, the other IMAP4 settings in this cmdlet are ignored.  <br/> |
| _ImapEnableExactRFC822Size_ <br/> |Optional  <br/> |System.Boolean  <br/> | This parameter is available only in on-premises Exchange. <br/>  The _ImapEnableExactRFC822Size_ parameter specifies how message sizes are presented to IMAP4 clients that access the mailbox. <br/>  Valid values for this parameter are: <br/>  `$true`: Calculate the exact message size.  <br/>  `$false`: Use an estimated message size.  <br/>  The default value is `$false`.  <br/>  We don't recommend changing this value unless you determine that the default setting causes problems for IMAP4 clients. To change the value of this parameter, you also need to set the value of the _ImapUseProtocolDefaults_ parameter to `$false`.  <br/> |
| _ImapForceICalForCalendarRetrievalOption_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _ImapForceICalForCalendarRetrievalOption_ parameter specifies how meeting requests are presented to IMAP4 clients that access the mailbox. <br/>  Valid values for this parameter are: <br/>  `$true`: All meeting requests are in the iCal format.  <br/>  `$false`: All meeting requests appear as Outlook on the web links.  <br/>  The default value is `$false`.  <br/>  To change the value of this parameter, you also need to set the value of the _ImapUseProtocolDefaults_ parameter to `$false`.  <br/> |
| _ImapMessagesRetrievalMimeFormat_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Directory.SystemConfiguration.MimeTextFormat  <br/> | The _ImapMessagesRetrievalMimeFormat_ parameter specifies the message format for IMAP4 clients that access the mailbox. You can use an integer or a text value. Valid values are: <br/>  0: `TextOnly` <br/>  1: `HtmlOnly` <br/>  2: `HtmlAndTextAlternative` <br/>  3: `TextEnrichedOnly` <br/>  4: `TextEnrichedAndTextAlternative` <br/>  5: `BestBodyFormat` <br/>  6: `Tnef` <br/>  The default value is `BestBodyFormat`.  <br/>  To change the value of this parameter, you also need to set the value of the _ImapUseProtocolDefaults_ parameter to `$false`.  <br/> |
| _ImapSuppressReadReceipt_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _ImapSuppressReadReceipt_ parameter controls the behavior of read receipts for IMAP4 clients that access the mailbox. <br/>  Valid values for this parameter are: <br/>  `$true`: The user receives a read receipt when the recipient opens the message.  <br/>  `$false`: The user receives two read receipts: one when the message is downloaded and another when the message is opened.  <br/>  The default value is `$false`.  <br/>  To change the value of this parameter, you also need to set the value of the _ImapUseProtocolDefaults_ parameter to `$false`.  <br/> |
| _ImapUseProtocolDefaults_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _ImapUseProtocolDefaults_ parameter specifies whether to use the IMAP4 protocol defaults for the mailbox. Valid input for this parameter is `$true` or `$false`. The default value is  `$true`.  <br/>  You need to set the _ImapUseProtocolDefaults_ parameter to `$false` when you use any of the following IMAP4 parameters: <br/>  _ImapEnableExactRFC822Size_ <br/>  _ImapForceICalForCalendarRetrievalOption_ <br/>  _ImapMessagesRetrievalMimeFormat_ <br/>  _ImapSuppressReadReceipt_ <br/> |
| _IsOptimizedForAccessibility_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _IsOptimizedForAccessibility_parameter specifies whether the mailbox is configured to use the light version of Outlook on the web. Valid values are:  <br/>  `$true`: The mailbox is configured to use the light version of Outlook on the web.  <br/>  `$false`: The mailbox isn't configured to use the light version of Outlook on the web.  <br/> |
| _MAPIBlockOutlookExternalConnectivity_ <br/> |Optional  <br/> |System.Boolean  <br/> | This parameter is available only in on-premises Exchange. <br/>  The _MAPIBlockOutlookExternalConnectivity_parameter enables or disables external access to the mailbox in Outlook by removing the external URLs from the Autodiscover response. This setting affects Outlook Anywhere, MAPI over HTTP, and Exchange Web Services (EWS). Valid values are:  <br/>  `$true`: External Outlook clients can't use Outlook Anywhere, MAPI over HTTP, or EWS to access the mailbox.  <br/>  `$false`: External Outlook clients can use Outlook Anywhere, MAPI over HTTP, or EWS to access the mailbox.  <br/> **Note**: If your organization uses the same Autodiscover URL values for internal and external clients, setting this parameter to  `$true` won't block access for external clients. <br/> |
| _MAPIBlockOutlookNonCachedMode_ <br/> |Optional  <br/> |System.Boolean  <br/> | This parameter is available only in on-premises Exchange. <br/>  The _MAPIBlockOutlookNonCachedMode_ parameter controls access to the mailbox by using Outlook in online or offline mode. <br/>  Valid values for this parameter are: <br/>  `$true`: Only Outlook clients that are configured to use Cached Exchange Mode (offline mode) are allowed to access the mailbox.  <br/>  `$false`: The state of the Cached Exchange Mode setting isn't checked before Outlook clients are allowed to access the mailbox (online mode and offline mode are allowed).  <br/>  The default value is `$false`.  <br/> |
| _MAPIBlockOutlookRpcHttp_ <br/> |Optional  <br/> |System.Boolean  <br/> | This parameter is available only in on-premises Exchange. <br/>  The _MAPIBlockOutlookRpcHttp_ parameter enables or disables access to the mailbox in Outlook by using Outlook Anywhere. Valid values are: <br/>  `$true`: Access to the mailbox by using Outlook Anywhere is disabled.  <br/>  `$false`: Access to the mailbox by using Outlook Anywhere is enabled. This is the default value.  <br/> |
| _MAPIBlockOutlookVersions_ <br/> |Optional  <br/> |System.String  <br/> |This parameter is available only in on-premises Exchange.  <br/> The  _MAPIBlockOutlookVersions_ parameter blocks access to the mailbox for specific versions of Outlook. <br/> For example, if you specify the value  `15.0.4569.1503`, only Outlook 2013 Service Pack 1 (SP1) or later clients are allowed to access the mailbox. Earlier versions of Outlook are blocked.  <br/> The default value is blank. To reset this parameter, use the value  `$null`.  <br/> |
| _MAPIEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _MAPIEnabled_ parameter enables or disables access to the mailbox by using MAPI clients (for example, Outlook). <br/> Valid input for this parameter is  `$true` or `$false`. The default value is  `$true`. Note that when you set this parameter to  `$false`, the other MAPI settings in this cmdlet are ignored.  <br/> |
| _MapiHttpEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> | This parameter is available only in on-premises Exchange. <br/>  The _MapiHttpEnabled_ parameter enables or disables access to the mailbox in Outlook by using MAPI over HTTP. Valid values are: <br/>  `$true`: Access to the mailbox by using MAPI over HTTP is enabled.  <br/>  `$false`: Access to the mailbox by using MAPI over HTTP is disabled.  <br/>  `$null` (blank): The setting isn't configured. The mailbox uses the organization setting for MAPI over HTTP (the _MapiHttpEnabled_ parameter on the **Set-OrganizationConfig** cmdlet). This is the default value. <br/> |
| _Name_ <br/> |Optional  <br/> |System.String  <br/> |This parameter is available only in on-premises Exchange.  <br/> The  _Name_ parameter specifies the unique name of the mailbox. The maximum length is 64 characters. If the value contains spaces, enclose the value in quotation marks ("). <br/> |
| _OWAEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _OWAEnabled_ parameter enables or disables access to the mailbox by using Outlook on the web. <br/> Valid input for this parameter is  `$true` or `$false`. The default value is  `$true`. Note that when you set this parameter to  `$false`, the other Outlook on the web settings in this cmdlet are ignored.  <br/> |
| _OWAforDevicesEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _OWAforDevicesEnabled_ parameter enables or disables access to the mailbox by using Outlook on the web for devices. <br/> Valid input for this parameter is  `$true` or `$false`. The default value is  `$true`.  <br/> |
| _OwaMailboxPolicy_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.MailboxPolicyIdParameter  <br/> | The _OwaMailboxPolicy_ parameter specifies the Outlook on the web mailbox policy for the mailbox. You can use any value that uniquely identifies the Outlook on the web mailbox policy. For example: <br/>  Name <br/>  Distinguished name (DN) <br/>  GUID <br/>  The name of the default Outlook on the web mailbox policy is `Default`.  <br/> |
| _PopEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _PopEnabled_ parameter enables or disables access to the mailbox by using POP3 clients. <br/> Valid input for this parameter is  `$true` or `$false`. The default value is  `$true`. Note that when you set this parameter to  `$false`, the other POP3 settings in this cmdlet are ignored.  <br/> |
| _PopEnableExactRFC822Size_ <br/> |Optional  <br/> |System.Boolean  <br/> | This parameter is available only in on-premises Exchange. <br/>  The _PopEnableExactRFC822Size_ parameter specifies how message sizes are presented to POP3 clients that access the mailbox. <br/>  Valid values for this parameter are: <br/>  `$true`: Calculate the exact message size.  <br/>  `$false`: Use an estimated message size.  <br/>  The default value is `$false`.  <br/>  We don't recommend changing this value unless you determine that the default setting causes problems for POP3 clients. To change the value of this parameter, you also need to set the value of the _PopUseProtocolDefaults_ parameter to `$false`.  <br/> |
| _PopForceICalForCalendarRetrievalOption_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _PopForceICalForCalendarRetrievalOption_ parameter specifies how meeting requests are presented to POP3 clients that access the mailbox. <br/>  Valid values for this parameter are: <br/>  `$true`: All meeting requests are in the iCal format.  <br/>  `$false`: All meeting requests appear as Outlook on the web links.  <br/>  The default value is `$false`.  <br/>  To change the value of this parameter, you also need to set the value of the _PopUseProtocolDefaults_ parameter to `$false`.  <br/> |
| _PopMessagesRetrievalMimeFormat_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Directory.SystemConfiguration.MimeTextFormat  <br/> | The _PopMessagesRetrievalMimeFormat_ parameter specifies the message format for POP3 clients that access the mailbox. You can use an integer or a text value. Valid values are: <br/>  0: `TextOnly` <br/>  1: `HtmlOnly` <br/>  2: `HtmlAndTextAlternative` <br/>  3: `TextEnrichedOnly` <br/>  4: `TextEnrichedAndTextAlternative` <br/>  5: `BestBodyFormat` <br/>  6: `Tnef` <br/>  The default value is `BestBodyFormat`.  <br/>  To change the value of this parameter, you also need to set the value of the _PopUseProtocolDefaults_ parameter to `$false`.  <br/> |
| _PopSuppressReadReceipt_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _PopSuppressReadReceipt_ parameter controls the behavior of read receipts for POP3 clients that access the mailbox. <br/>  Valid values for this parameter are: <br/>  `$true`: The user receives a read receipt when the recipient opens the message.  <br/>  `$false`: The user receives two read receipts: one when the message is downloaded and another when the message is opened.  <br/>  The default value is `$false`.  <br/>  To change the value of this parameter, you also need to set the value of the _PopUseProtocolDefaults_ parameter to `$false`.  <br/> |
| _PopUseProtocolDefaults_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _PopUseProtocolDefaults_ parameter specifies whether to use the POP3 protocol defaults for the mailbox. <br/>  Valid input for this parameter is `$true` or `$false`. The default value is  `$true`. You need to set the  _PopUseProtocolDefaults_ parameter to `$false` when you use any of following parameters: <br/>  _PopEnableExactRFC822Size_ <br/>  _PopForceICalForCalendarRetrievalOption_ <br/>  _PopMessagesRetrievalMimeFormat_ <br/>  _PopSuppressReadReceipt_ <br/> |
| _PrimarySmtpAddress_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.SmtpAddress  <br/> |This parameter is available only in on-premises Exchange.  <br/> The  _PrimarySmtpAddress_ parameter specifies the primary return email address that's used for the recipient. If it's available on this cmdlet, you can't use the _EmailAddresses_ and _PrimarySmtpAddress_ parameters in the same command. <br/> |
| _ResetAutoBlockedDevices_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |This parameter is available only in on-premises Exchange.  <br/> The  _ResetAutoBlockedDevices_ switch resets the status of blocked mobile devices that have exceeded the limits defined by the **Set-ActiveSyncDeviceAutoblockThreshold** cmdlet. You don't need to specify a value with this switch. <br/> |
| _SamAccountName_ <br/> |Optional  <br/> |System.String  <br/> |This parameter is available only in on-premises Exchange.  <br/> The  _SamAccountName_ parameter (also known as the pre-Windows 2000 user account or group name) specifies an object identifier that's compatible with older versions of Microsoft Windows client and server operating systems. The value can contain letters, numbers, spaces, periods (.), and the characters !, #, $, %, ^, &amp;, -, _, {, }, and ~. The last character can't be a period. Unicode characters are allowed, but accented characters may generate collisions (for example, o and ö match). The maximum length is 20 characters. <br/> |
| _ShowGalAsDefaultView_ <br/> |Optional  <br/> |System.Boolean  <br/> |The  _ShowGalAsDefaultView_ parameter shows the global address list (GAL) as the default recipient picker for messages. Valid input for this parameter is `$true` or `$false`. The default value is  `$true`.  <br/> |
| _UniversalOutlookEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> | This parameter is available only in the cloud-based service. <br/>  The _UniversalOutlookEnabled_ parameter enables or disables access to the mailbox by using Mail and Calendar. Valid values are: <br/>  `$true`: Access to the mailbox in Mail and Calendar is enabled. This is the default value.  <br/>  `$false`: Access to the mailbox in Mail and Calendar is disabled.  <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The  _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
