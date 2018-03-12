---
title: "Set-PopSettings"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/16/2018
ms.audience: ITPro
ms.topic: reference
ms.prod: exchange-server-itpro
localization_priority: Normal
ms.assetid: 307a1dd0-3a4c-4431-bd9f-35aa5cb57aad
description: "This cmdlet is available only in on-premises Exchange."
---

# Set-PopSettings

This cmdlet is available only in on-premises Exchange. 
  
Use the **Set-PopSettings** cmdlet to modify the configuration of the Microsoft Exchange POP3 service. This service exists on Exchange servers that have the Client Access server role installed, and is used by POP3 clients to connect to Exchange.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Set-PopSettings [-AuthenticatedConnectionTimeout <EnhancedTimeSpan>] [-Banner <String>] [-CalendarItemRetrievalOption <iCalendar | intranetUrl | InternetUrl | Custom>] [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-EnableExactRFC822Size <$true | $false>] [-EnableGSSAPIAndNTLMAuth <$true | $false>] [-EnforceCertificateErrors <$true | $false>] [-ExtendedProtectionPolicy <None | Allow | Require>] [-ExternalConnectionSettings <MultiValuedProperty>] [-InternalConnectionSettings <MultiValuedProperty>] [-LogFileLocation <String>] [-LogFileRollOverSettings <Hourly | Daily | Weekly | Monthly>] [-LoginType <PlainTextLogin | PlainTextAuthentication | SecureLogin>] [-LogPerFileSizeQuota <Unlimited>] [-MaxCommandSize <Int32>] [-MaxConnectionFromSingleIP <Int32>] [-MaxConnections <Int32>] [-MaxConnectionsPerUser <Int32>] [-MessageRetrievalMimeFormat <TextOnly | HtmlOnly | HtmlAndTextAlternative | TextEnrichedOnly | TextEnrichedAndTextAlternative | BestBodyFormat | Tnef>] [-MessageRetrievalSortOrder <Ascending | Descending>] [-OwaServerUrl <Uri>] [-PreAuthenticatedConnectionTimeout <EnhancedTimeSpan>] [-ProtocolLogEnabled <$true | $false>] [-ProxyTargetPort <Int32>] [-Server <ServerIdParameter>] [-SSLBindings <MultiValuedProperty>] [-SuppressReadReceipt <$true | $false>] [-UnencryptedOrTLSBindings <MultiValuedProperty>] [-WhatIf [<SwitchParameter>]] [-X509CertificateName <String>]

```

## Examples
<a name="Examples"> </a>

### Example 1

This example configures the unencrypted or **STARTTLS** encrypted POP3 connection to the server named MBX01 by using the local IP address 10.0.0.0 on TCP port 110.
  
```
Set-PopSettings -Server "MBX01" -UnencryptedOrTLSBindings 10.0.0.0:110
```

### Example 2

This example turns on POP3 protocol logging. It also changes the POP3 protocol logging directory to C:\Pop3Logging.
  
```
Set-PopSettings -ProtocolLogEnabled $true -LogFileLocation "C:\Pop3Logging"
```

### Example 3

This example changes the POP3 protocol logging to create a new log file when a log file reaches 2 megabytes (MB).
  
```
Set-PopSettings -LogPerFileSizeQuota 2MB
```

### Example 4

This example changes the POP3 protocol logging to create a new log file every hour.
  
```
Set-PopSettings -LogPerFileSizeQuota 0 -LogFileRollOverSettings Hourly
```

## Detailed Description
<a name="DetailedDescription"> </a>

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _AuthenticatedConnectionTimeout_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.EnhancedTimeSpan  <br/> |The _AuthenticatedConnectionTimeout_ parameter specifies the time to wait before closing an idle authenticated connection. <br/> To specify a value, enter it as a time span:  `dd.hh:mm:ss` where `dd` = days, `hh` = hours, `mm` = minutes, and `ss` = seconds. <br/> Valid values are  `00:00:30` to `1:00:00`. The default value is  `00:30:00` (30 minutes). <br/> |
| _Banner_ <br/> |Optional  <br/> |System.String  <br/> |The _Banner_ parameter specifies the text string that's displayed to connecting POP3 clients. The default value is: `The Microsoft Exchange POP3 service is ready.` <br/> |
| _CalendarItemRetrievalOption_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Directory.SystemConfiguration.CalendarItemRetrievalOptions  <br/> | The _CalendarItemRetrievalOption_ parameter specifies how calendar items are presented to POP3 clients.. Valid values are: <br/>  `0` or `iCalendar`. This is the default value.  <br/>  `1` or `IntranetUrl`.  <br/>  `2` or `InternetUrl`.  <br/>  `3` or `Custom`.  <br/>  If you specify `3` or `Custom`, you need to specify a value for the _OwaServerUrl_ parameter. <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |The _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> |
| _EnableExactRFC822Size_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _EnableExactRFC822Size_ parameter specifies how message sizes are presented to POP3 clients. Valid values are: <br/>  `$true`: Calculate the exact message size. Because this setting can negatively affect performance, you should configure it only if it's required by your POP3 clients.  <br/>  `$false`: Use an estimated message size. This is the default value.  <br/> |
| _EnableGSSAPIAndNTLMAuth_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _EnableGSSAPIAndNTLMAuth_ parameter specifies whether connections can use Integrated Windows authentication (NTLM) by using the Generic Security Services application programming interface (GSSAPI). This setting applies to connections where Transport Layer Security (TLS) is disabled. Valid values are: <br/>  `$true`: NTLM for POP3 connections is enabled. This is the default value.  <br/>  `$false`: NTLM for POP3 connections is disabled.  <br/> |
| _EnforceCertificateErrors_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _EnforceCertificateErrors_ parameter specifies whether to enforce Secure Sockets Layer (SSL) certificate validation failures. Valid values are: <br/>  `$true`: If the certificate isn't valid or doesn't match the target POP3 server's FQDN, the connection attempt fails.  <br/>  `$false`: The server doesn't deny POP3 connections based on certificate errors. This is the default value.  <br/> |
| _ExtendedProtectionPolicy_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Directory.SystemConfiguration.ExtendedProtectionTokenCheckingMode  <br/> | The _ExtendedProtectionPolicy_ parameter specifies how Extended Protection for Authentication is used for POP3 connections. Valid values are: <br/>  `None`: Extended Protection for Authentication isn't used. This is the default value.  <br/>  `Allow`: Extended Protection for Authentication is used only if it's supported by the incoming POP3 connection. If it's not, Extended Protection for Authentication isn't used.  <br/>  `Require`: Extended Protection for Authentication is required for all POP3 connections. If the incoming POP3 connection doesn't support it, the connection is rejected.  <br/>  Extended Protection for Authentication enhances the protection and handling of credentials by Integrated Windows authentication (also known as NTLM), so we strongly recommend that you use it if it's supported by your clients (default installations of Windows 7 or later and Windows Server 2008 R2 or later support it). <br/> |
| _ExternalConnectionSettings_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.MultiValuedProperty  <br/> |The _ExternalConnectionSettings_ parameter specifies the host name, port, and encryption method that's used by external POP3 clients (POP3 connections from outside your corporate network). <br/> This parameter uses the syntax  `<HostName>:<Port>:[<TLS | SSL>]`. The encryption method value is optional (blank indicates unencrypted connections).  <br/> The default value is blank ( `$null`), which means no external POP3 connection settings are configured.  <br/> To enter multiple values and overwrite any existing entries, use the following syntax:  `<value1>,<value2>...`. If the values contain spaces or otherwise require quotation marks, you need to use the following syntax:  `"<value1>","<value2>"...`.  <br/> To add or remove one or more values without affecting any existing entries, use the following syntax:  `@{Add="<value1>","<value2>"...; Remove="<value1>","<value2>"...}`.  <br/> The combination of encryption methods and ports that are specified for this parameter need to match the corresponding encryption methods and ports that are specified by the _SSLBindings_ and _UnencryptedOrTLSBindings_ parameters. <br/> |
| _InternalConnectionSettings_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.MultiValuedProperty  <br/> |The _InternalConnectionSettings_ parameter specifies the host name, port, and encryption method that's used by internal POP3 clients (POP3 connections from inside your corporate network). This setting is also used when a POP3 connection is forwarded to another Exchange server that's running the Microsoft Exchange POP3 service. <br/> This parameter uses the syntax  `<HostName>:<Port>:[<TLS | SSL>]`. The encryption method value is optional (blank indicates unencrypted connections).  <br/> The default value is  `<ServerFQDN>:995:SSL,<ServerFQDN>:110:TLS`.  <br/> To enter multiple values and overwrite any existing entries, use the following syntax:  `<value1>,<value2>...`. If the values contain spaces or otherwise require quotation marks, you need to use the following syntax:  `"<value1>","<value2>"...`.  <br/> To add or remove one or more values without affecting any existing entries, use the following syntax:  `@{Add="<value1>","<value2>"...; Remove="<value1>","<value2>"...}`.  <br/> The combination of encryption methods and ports that are specified for this parameter need to match the corresponding encryption methods and ports that are specified by the _SSLBindings_ and _UnencryptedOrTLSBindings_ parameters. <br/> |
| _LogFileLocation_ <br/> |Optional  <br/> |System.String  <br/> |The _LogFileLocation_ parameter specifies the location for the POP3 protocol log files. The default location is `%ExchangeInstallPath%Logging\Pop3`.  <br/> This parameter is only meaningful when the _ProtocolLogEnabled_ parameter value is `$true`.  <br/> |
| _LogFileRollOverSettings_ <br/> |Optional  <br/> |Microsoft.Exchange.Diagnostics.LogFileRollOver  <br/> | The _LogFileRollOverSettings_ parameter defines how frequently POP3 protocol logging creates a new log file. Valid values are: <br/>  `1` or `Hourly`.  <br/>  `2` or `Daily`. This is the default value.  <br/>  `3` or `Weekly`.  <br/>  `4` or `Monthly`.  <br/>  This parameter is only meaningful when the _LogPerFileSizeQuota_ parameter value is `0`, and the _ProtocolLogEnabled_ parameter value is `$true`.  <br/> |
| _LoginType_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Directory.SystemConfiguration.LoginOptions  <br/> | The _LoginType_ parameter specifies the authentication method for POP3 connections. Valid values are: <br/>  `1` or `PlainTextLogin`.  <br/>  `2` or `PlainTextAuthentication`.  <br/>  `3` or `SecureLogin`. This is the default value.  <br/> |
| _LogPerFileSizeQuota_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Unlimited  <br/> | The _LogPerFileSizeQuota_ parameter specifies the maximum size of a POP3 protocol log file. <br/>  When you enter a value, qualify the value with one of the following units: <br/>  `B` (bytes) <br/>  `KB` (kilobytes) <br/>  `MB` (megabytes) <br/>  `GB` (gigabytes) <br/>  `TB` (terabytes) <br/>  Unqualified values are typically treated as bytes, but small values may be rounded up to the nearest kilobyte. <br/>  The default value is 0, which means a new POP3 protocol log file is created at the frequency that's specified by the _LogFileRollOverSettings_ parameter. <br/>  This parameter is only meaningful when the _ProtocolLogEnabled_ parameter value is `$true`.  <br/> |
| _MaxCommandSize_ <br/> |Optional  <br/> |System.Int32  <br/> |The _MaxCommandSize_ parameter specifies the maximum size in bytes of a single POP3 command. Valid values are from 40 through 1024. The default value is 512. <br/> |
| _MaxConnectionFromSingleIP_ <br/> |Optional  <br/> |System.Int32  <br/> |The _MaxConnectionFromSingleIP_ parameter specifies the maximum number of POP3 connections that are accepted by the Exchange server from a single IP address. Valid values are from 1 through 2147483647. The default value is `2147483647`.  <br/> |
| _MaxConnections_ <br/> |Optional  <br/> |System.Int32  <br/> |The _MaxConnections_ parameter specifies the maximum number of POP3 connections that are accepted by the Exchange server. Valid values are from 1 through 2147483647. The default value is `2147483647`.  <br/> |
| _MaxConnectionsPerUser_ <br/> |Optional  <br/> |System.Int32  <br/> |The _MaxConnectionsPerUser_ parameter specifies the maximum number of POP3 connections that are allowed for each user. Valid values are from 1 through 2147483647. The default value is `16`.  <br/> |
| _MessageRetrievalMimeFormat_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Directory.SystemConfiguration.MimeTextFormat  <br/> | The _MessageRetrievalMimeFormat_ parameter specifies the MIME encoding of messages. Valid values are: <br/>  `0` or `TextOnly`.  <br/>  `1` or `HtmlOnly`.  <br/>  `2` or `HtmlAndTextAlternative`.  <br/>  `3` or `TextEnrichedOnly`.  <br/>  `4` or `TextEnrichedAndTextAlternative`.  <br/>  `5` or `BestBodyFormat`. This is the default value.  <br/>  `6` or `Tnef`.  <br/> |
| _MessageRetrievalSortOrder_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.SortOrder  <br/> | The _MessageRetrievalSortOrder_ parameter specifies how retrieved messages are sorted. Valid values are: <br/>  `0` or `Ascending`. This is the default value.  <br/>  `1` or `Descending`.  <br/> |
| _OwaServerUrl_ <br/> |Optional  <br/> |System.Uri  <br/> |The _OwaServerUrl_ parameter specifies the URL that's used to retrieve calendar information for instances of custom Outlook on the web calendar items. <br/> |
| _PreAuthenticatedConnectionTimeout_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.EnhancedTimeSpan  <br/> |The _PreAuthenticatedConnectionTimeout_ parameter specifies the time to wait before closing an idle POP3 connection that isn't authenticated. <br/> To specify a value, enter it as a time span:  `dd.hh:mm:ss` where `dd` = days, `hh` = hours, `mm` = minutes, and `ss` = seconds. <br/> Valid values are from `00:00:30` to `1:00:00`. The default value is  `00:01:00` (one minute). <br/> |
| _ProtocolLogEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _ProtocolLogEnabled_ parameter specifies whether to enable protocol logging for POP3. Valid values are: <br/>  `$true`: POP3 protocol logging is enabled.  <br/>  `$false`: POP3 protocol logging is disabled. This is the default value.  <br/> |
| _ProxyTargetPort_ <br/> |Optional  <br/> |System.Int32  <br/> |The _ProxyTargetPort_ parameter specifies the port on the Microsoft Exchange POP3 Backend service that listens for client connections that are proxied from the Microsoft Exchange POP3 service. The default value is 1995. <br/> |
| _Server_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.ServerIdParameter  <br/> | The _Server_ parameter specifies the Exchange server where you want to run this command. You can use any value that uniquely identifies the server. For example: <br/>  Name <br/>  FQDN <br/>  Distinguished name (DN) <br/>  Exchange Legacy DN <br/>  If you don't use this parameter, the command is run on the local server. <br/> |
| _SSLBindings_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.MultiValuedProperty  <br/> |The _SSLBindings_ parameter specifies the IP address and TCP port that's used for an POP3 connection that's always encrypted by SSL/TLS. This parameter uses the syntax `<IPv4OrIPv6Address>:<Port>`.  <br/> The default value is  `[::]:995,0.0.0.0:995`.  <br/> To enter multiple values and overwrite any existing entries, use the following syntax:  `<value1>,<value2>...`. If the values contain spaces or otherwise require quotation marks, you need to use the following syntax:  `"<value1>","<value2>"...`.  <br/> To add or remove one or more values without affecting any existing entries, use the following syntax:  `@{Add="<value1>","<value2>"...; Remove="<value1>","<value2>"...}`.  <br/> |
| _SuppressReadReceipt_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _SuppressReadReceipt_ parameter specifies whether to stop duplicate read receipts from being sent to POP3 clients that have the **Send read receipts for messages I send** setting configured in their POP3 email program. Valid values are: <br/>  `$true`: The sender receives a read receipt only when the recipient opens the message.  <br/>  `$false`: The sender receives a read receipt when the recipient downloads the message, and when the recipient opens the message. This is the default value.  <br/> |
| _UnencryptedOrTLSBindings_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.MultiValuedProperty  <br/> |The _UnencryptedOrTLSBindings_ parameter specifies the IP address and TCP port that's used for unencrypted POP3 connections, or POP3 connections that are encrypted by using opportunistic TLS ( **STARTTLS** ) after the initial unencrypted protocol handshake. This parameter uses the syntax `<IPv4OrIPv6Address>:<Port>`.  <br/> The default value is  `[::]:110, 0.0.0.0:110`.  <br/> To enter multiple values and overwrite any existing entries, use the following syntax:  `<value1>,<value2>...`. If the values contain spaces or otherwise require quotation marks, you need to use the following syntax:  `"<value1>","<value2>"...`.  <br/> To add or remove one or more values without affecting any existing entries, use the following syntax:  `@{Add="<value1>","<value2>"...; Remove="<value1>","<value2>"...}`.  <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
| _X509CertificateName_ <br/> |Optional  <br/> |System.String  <br/> |The _X509CertificateName_ parameter specifies the certificate that's used for encrypting POP3 client connections. <br/> A valid value for this parameter is the FQDN from the _ExternalConnectionSettings_ or _InternalConnectionSettings_ parameters (for example, mail.contoso.com or mailbox01.contoso.com). <br/> If you use a single subject certificate or a subject alternative name (SAN) certificate, you also need to assign the certificate to the Exchange POP service by using the **Enable-ExchangeCertificate** cmdlet. <br/> If you use a wildcard certificate, you don't need to assign the certificate to the Exchange POP service.  <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
