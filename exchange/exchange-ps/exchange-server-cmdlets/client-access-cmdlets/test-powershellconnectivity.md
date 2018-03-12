---
title: "Test-PowerShellConnectivity"
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 1/19/2018
ms.audience: Developer
ms.topic: reference
ms.prod: exchange-server-itpro
localization_priority: Normal
ms.assetid: 2a876f48-9431-47fa-b65a-f3ea57c7f220
description: "This cmdlet is available only in on-premises Exchange."
---

# Test-PowerShellConnectivity

This cmdlet is available only in on-premises Exchange. 
  
Use the **Test-PowerShellConnectivity** cmdlet to test client connectivity to Exchange remote PowerShell virtual directories.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Test-PowerShellConnectivity [-ClientAccessServer <ServerIdParameter>] [-TestType <Internal | External>] [-VirtualDirectoryName <String>] <COMMON PARAMETERS>

```

## Examples
<a name="Examples"> </a>

### Example 1

This example tests the PowerShell (Default Web Site) virtual directory on the MBX2 server. The _TrustAnySSLCertificate_ switch is used to skip the certificate check during connection.
  
```
Test-PowerShellConnectivity -ClientAccessServer MBX2 -VirtualDirectoryName "PowerShell (Default Web Site)" -TrustAnySSLCertificate
```

### Example 2

This example tests the remote PowerShell virtual directory that's available at  `https://contoso.com/powershell`. A mismatch between the SSL certificate and the URL isn't expected, so the _TrustAnySSLCertificate_ switch isn't used. The virtual directoryis configured to use Basic authentication.
  
The credentials that are used to connect to the virtual directory are stored in the _$UserCredentials_ variable. The test is then run as previously described.
  
```
$UserCredentials = Get-Credential; Test-PowerShellConnectivity -ConnectionUri https://contoso.com/powershell -TestCredential $UserCredentials -Authentication Basic
```

## Detailed Description
<a name="DetailedDescription"> </a>

The **Test-PowerShellConnectivity** cmdlet tests Exchange remote PowerShell connectivity by connecting to a specified remote PowerShell virtual directory, to any remote PowerShell virtual directories on a specified Exchange server, or to any remote PowerShell virtual directories that are available in the local Active Directory site.
  
The first time you use this cmdlet, you might be required to create a test user. To create a test user, run the following command.
  
```
&amp; $env:ExchangeInstallPath\Scripts\New-TestCasConnectivityUser.ps1
```

The test results are displayed on-screen. The cmdlet returns the following information.
  
- **CasServer**: The Exchange server that the client connected to.
    
- **LocalSite**: The name of the local Active Directory site.
    
- **Scenario**: The operations that are tested. Values are:  `Logon User`.
    
- **Result**: The values returned are typically  `Success`,  `Skipped`, or  `Failure`.
    
- **Latency(MS)**: The time required to complete the test in milliseconds.
    
- **Error**: Any error messages that were encountered.
    
You can write the results to a file by piping the output to **ConvertTo-Html** or **ConvertTo-Csv** and adding `> <filename>` to the command. For example:
  
```
Test-PowerShellConnectivity -ClientAccessServer MBX01 | ConvertTo-Html > "C:\My Documents\PowerShell Test.html"
```

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _ConnectionUri_ <br/> |Required  <br/> |System.Uri  <br/> |The _ConnectionUri_ parameter specifies the URL of the remote PowerShell virtual directory to test, for example, `https://contoso.com/powershell`.  <br/> You can't use this parameter with the _ClientAccessServer_ parameter. <br/> |
| _TestCredential_ <br/> |Required  <br/> |System.Management.Automation.PSCredential  <br/> |The _TestCredential_ parameter specifies the credentials to use for the test. <br/> This parameter requires you to create a credentials object by using the **Get-Credential** cmdlet. For more information, see[Get-Credential](https://go.microsoft.com/fwlink/p/?linkId=142122).  <br/>  You can only use this parameter with the _ConnectionUri_ parameter. <br/> |
| _Authentication_ <br/> |Optional  <br/> |System.Management.Automation.Runspaces.AuthenticationMechanism  <br/> | The _Authentication_ parameter specifies the type of authentication that's used to connect. Valid values are: <br/>  `Default` <br/>  `Basic` <br/>  `Credssp` <br/>  `Digest` <br/>  `Kerberos` <br/>  `Negotiate` <br/> |
| _ClientAccessServer_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.ServerIdParameter  <br/> | The _ClientAccessServer_ parameter specifies the Exchange server to test. This server has the Client Access server role installed, and is responsible for accepting client connections. <br/>  You can use any value that uniquely identifies the server. For example: <br/>  Name <br/>  Distinguished name (DN) <br/> **ExchangeLegacyDN** <br/>  GUID <br/>  You can't use this parameter with the _ConnectionUri_ parameter. <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |The _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> |
| _MailboxServer_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.ServerIdParameter  <br/> | The _MailboxServer_ parameter specifies the Exchange 2016 or Exchange 2013 Mailbox server that you want to test. This parameter identifies the backend server that accepts proxied connections from the frontend server where clients connect. <br/>  You can use any value that uniquely identifies the server. For example: <br/>  Name <br/>  Distinguished name (DN) <br/> **ExchangeLegacyDN** <br/>  GUID <br/>  If you don't use this parameter, connections to all Mailbox servers in the local Active Directory site are tested. <br/> |
| _MonitoringContext_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _MonitoringContext_ switch includes the associated monitoring events and performance counters in the results. Typically, you include the monitoring events and performance counters in the results when the output is passed to MicrosoftSystem Center Operations Manager (SCOM). You don't need to specify a value with this switch. <br/> |
| _ResetTestAccountCredentials_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _ResetTestAccountCredentials_ switch resets the password for the test account that's used to run this command. The password for the test account is typically reset every seven days. Use this switch to force a password reset any time it's required for security reasons. <br/> |
| _TestType_ <br/> |Optional  <br/> |Microsoft.Exchange.Monitoring.OwaConnectivityTestType  <br/> |The _TestType_ parameter specifies whether the command tests internal or external URLs. Values are `Internal` and `External`. The default value is  `Internal`.  <br/> You can only use this parameter with the _ClientAccessServer_ parameter. <br/> |
| _TrustAnySSLCertificate_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _TrustAnySSLCertificate_ switch specifies whether to ignore Secure Sockets Layer (SSL) certificate validation failures. You don't need to specify a value with this switch. <br/> This switch is useful for testing internal URLs, because a URL that has an associated certificate is typically an external URL. This switch lets the task check an internal URL without generating an error when the certificate doesn't match the URL.  <br/> |
| _VirtualDirectoryName_ <br/> |Optional  <br/> |System.String  <br/> |The _VirtualDirectoryName_ parameter specifies the name of the remote PowerShell virtual directory that you want to test. Enclose values that contain spaces in quotation marks ("). <br/> You can only use this parameter with the _ClientAccessServer_ parameter. If you don't use this parameter, all available remote PowerShell virtual directories on the server are tested. <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
