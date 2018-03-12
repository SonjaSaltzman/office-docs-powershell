---
title: "Get-ActiveSyncDevice"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/16/2018
ms.audience: Developer
ms.topic: reference
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 06a82fdc-9bf7-43c7-8471-d977034d3560
description: "This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other."
---

# Get-ActiveSyncDevice

This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other. 
  
Use the **Get-ActiveSyncDevice** cmdlet to retrieve the list of devices in your organization that have active Exchange ActiveSync partnerships.
  
> [!CAUTION]
> The **Get-ActiveSyncDevice** cmdlet will be removed in a future version of Exchange. Use the **Get-MobileDevice** cmdlet instead. If you have any scripts that use the **Get-ActiveSyncDevice** cmdlet, update them to use the **Get-MobileDevice** cmdlet.
  
```
Get-ActiveSyncDevice [-Identity <ActiveSyncDeviceIdParameter>] <COMMON PARAMETERS>

```

## Examples
<a name="Examples"> </a>

### Example 1

This example returns all the Exchange ActiveSync mobile devices that Tony Smith has used that are associated with his mailbox.
  
```
Get-ActiveSyncDevice -Identity "TonySmith"
```

### Example 2

This example returns all the Exchange ActiveSync mobile devices that Tony Smith has used that are associated with his mailbox.
  
```
Get-ActiveSyncDevice -Mailbox "Redmond\TonySmith"
```

## Detailed Description
<a name="DetailedDescription"> </a>

The **Get-ActiveSyncDevice** cmdlet returns identification, configuration, and status information for each device.
  
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Mailbox_ <br/> |Required  <br/> |Microsoft.Exchange.Configuration.Tasks.MailboxIdParameter  <br/> | The _Mailbox_ parameter specifies the mailbox that has the associated ActiveSync device that you want to view. You can use any value that uniquely identifies the mailbox. <br/>  For example: <br/>  Name <br/>  Display name <br/>  Alias <br/>  Distinguished name (DN) <br/>  Canonical DN <br/>  _\<domain name\>_\ _\<account name\>_ <br/>  Email address <br/>  GUID <br/> **LegacyExchangeDN** <br/> **SamAccountName** <br/>  User ID or user principal name (UPN) <br/> |
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |This parameter is available only in on-premises Exchange.  <br/> The  _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> |
| _Filter_ <br/> |Optional  <br/> |System.String  <br/> | The _Filter_ parameter uses OPATH filter syntax to filter the results by the specified properties and values. The search criteria uses the syntax `{<Property> -<Comparison operator> '<Value>'}`.  <br/>  `<Property>` is a filterable property. <br/>  `-<Comparison Operator>` is an OPATH comparison operator. For example `-eq` for equals and `-like` for string comparison. For more information about comparison operators, see[about_Comparison_Operators](https://go.microsoft.com/fwlink/p/?LinkId=620712).  <br/>  `<Value>` is the property value. Text values with or without spaces need to be enclosed in quotation marks ( `'<Value>'`). Don't use quotation marks with integers or the system values  `$true`,  `$false`, or  `$null`.  <br/>  You can chain multiple search criteria together using the logical operators `-and` and `-or`. For example,  `{<Criteria1>) -and <Criteria2>}` or `{(<Criteria1> -and <Criteria2>) -or <Criteria3>}`.  <br/>  You can filter by the following properties: <br/> **ClientType** <br/> **DeviceAccessControlRule** <br/> **DeviceAccessState** <br/> **DeviceAccessStateReason** <br/> **DeviceActiveSyncVersion** <br/> **DeviceId** <br/> **DeviceImei** <br/> **DeviceMobileOperator** <br/> **DeviceModel** <br/> **DeviceOS** <br/> **DeviceOSLanguage** <br/> **DeviceTelephoneNumber** <br/> **DeviceType** <br/> **DeviceUserAgent** <br/> **FirstSyncTime** <br/> ** FriendlyName** <br/> ** ProvisioningFlags** <br/> **UserDisplayName** <br/> |
| _Identity_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.ActiveSyncDeviceIdParameter  <br/> | The _Identity_ parameter specifies the ActiveSync device that you want to view. You can use any value that uniquely identifies the device. For example: <br/>  `GUID` <br/>  `DeviceIdentity` <br/>  `Multi-TenantID` <br/> |
| _Monitoring_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |This parameter is available only in on-premises Exchange.  <br/> The  _Monitoring_ parameter specifies whether mobile devices created by monitoring accounts are included in the **[Get-ActiveSyncDevice]** cmdlet output. The default value is _$false_.  <br/> |
| _OrganizationalUnit_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.OrganizationalUnitIdParameter  <br/> | The _OrganizationalUnit_ parameter filters the results based on the object's location in Active Directory. Only objects that exist in the specified location are returned. Valid input for this parameter is an organizational unit (OU) or domain that's visible using the **Get-OrganizationalUnit** cmdlet. You can use any value that uniquely identifies the OU or domain. For example: <br/>  Name <br/>  Canonical name <br/>  Distinguished name (DN) <br/>  GUID <br/> |
| _ResultSize_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Unlimited  <br/> |The  _ResultSize_ parameter specifies the maximum number of results to return. If you want to return all requests that match the query, use `unlimited` for the value of this parameter. The default value is `1000`.  <br/> |
| _SortBy_ <br/> |Optional  <br/> |System.String  <br/> | The _SortBy_ parameter specifies the property to sort the results by. You can sort by only one property at a time. The results are sorted in ascending order. <br/>  If the default view doesn't include the property you're sorting by, you can append the command with `| Format-Table -Auto <Property1>,<Property2>...` to create a new view that contains all of the properties that you want to see. Wildcards (*) in the property names are supported. <br/>  You can sort by the following properties: <br/> **DeviceAccessControlRule** <br/> **DeviceAccessState** <br/> **DeviceAccessStateReason** <br/> **DeviceId** <br/> **DeviceImei** <br/> **DeviceMobileOperator** <br/> **DeviceModel** <br/> **DeviceOS** <br/> **DeviceOSLanguage** <br/> **DeviceTelephoneNumber** <br/> **DeviceType** <br/> **DeviceUserAgent** <br/> **FirstSyncTime** <br/> **FriendlyName** <br/> **UserDisplayName** <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
