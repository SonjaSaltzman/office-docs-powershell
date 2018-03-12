---
title: "Remove-ADPermission"
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 1/19/2018
ms.audience: ITPro
ms.topic: reference
ms.prod: exchange-server-itpro
localization_priority: Normal
ms.assetid: 0e45951a-2b5a-4aa9-a709-def61d7d4972
description: "This cmdlet is available only in on-premises Exchange."
---

# Remove-ADPermission

This cmdlet is available only in on-premises Exchange. 
  
Use the **Remove-ADPermission** cmdlet to remove permissions from an Active Directory object.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Remove-ADPermission -Identity <ADRawEntryIdParameter> -User <SecurityPrincipalIdParameter> [-AccessRights <ActiveDirectoryRights[]>] [-ChildObjectTypes <ADSchemaObjectIdParameter[]>] [-Deny <SwitchParameter>] [-ExtendedRights <ExtendedRightIdParameter[]>] [-InheritanceType <None | All | Descendents | SelfAndChildren | Children>] [-InheritedObjectType <ADSchemaObjectIdParameter>] [-Properties <ADSchemaObjectIdParameter[]>] <COMMON PARAMETERS>

```

## Examples
<a name="Examples"> </a>

### Example 1

This example removes the Send As permissions from user Kim on the user Administrator.
  
```
Remove-ADPermission -Identity Administrator -User Kim -ExtendedRights "Send As"
```

### Example 2

This example removes the ability for anonymous users to send messages through the Receive connector IP Secured Inbound.
  
```
Remove-ADPermission "IP Secured Inbound" -User "NT AUTHORITY\ANONYMOUS LOGON" -ExtendedRights ms-Exch-SMTP-Submit,ms-Exch-SMTP-Accept-Any-Recipient,ms-Exch-Bypass-Anti-Spam
```

## Detailed Description
<a name="DetailedDescription"> </a>

The **ADPermission** cmdlets can be used to directly modify Active Directory access control lists (ACLs). Although some Microsoft Exchange features may continue to use the **ADPermission** cmdlets to manage permissions (for example Send and Receive connectors) Exchange 2013 and later versions no longer use customized ACLs to manage administrative permissions. If you want to grant or deny administrative permissions in Exchange 2013 or later, you need to use Role Based Access Control (RBAC). For more information about RBAC, see **Permissions**. 
  
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Required  <br/> |Microsoft.Exchange.Configuration.Tasks.ADRawEntryIdParameter  <br/> |The _Identity_ parameter specifies the object from which the permission should be removed. <br/> You can specify either the distinguished name (DN) of the object or the object's name if it's unique. If the DN or name contains spaces, enclose the name in quotation marks (").  <br/> |
| _Instance_ <br/> |Required  <br/> |Microsoft.Exchange.Management.RecipientTasks.ADAcePresentationObject  <br/> |The _Instance_ parameter enables you to pass an entire object to the command to be processed. It's mainly used in scripts where an entire object must be passed to the command. <br/> |
| _User_ <br/> |Required  <br/> |Microsoft.Exchange.Configuration.Tasks.SecurityPrincipalIdParameter  <br/> |The _User_ parameter specifies the user object that will have permissions removed. <br/> |
| _AccessRights_ <br/> |Optional  <br/> |System.DirectoryServices.ActiveDirectoryRights[]  <br/> | The _AccessRights_ parameter specifies the rights needed to perform the operation. Valid values include: <br/>  `CreateChild` <br/>  `DeleteChild` <br/>  `ListChildren` <br/>  `Self` <br/>  `ReadProperty` <br/>  `WriteProperty` <br/>  `DeleteTree` <br/>  `ListObject` <br/>  `ExtendedRight` <br/>  `Delete` <br/>  `ReadControl` <br/>  `GenericExecute` <br/>  `GenericWrite` <br/>  `GenericRead` <br/>  `WriteDacl` <br/>  `WriteOwner` <br/>  `GenericAll` <br/>  `Synchronize` <br/>  `AccessSystemSecurity` <br/> |
| _ChildObjectTypes_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.ADSchemaObjectIdParameter[]  <br/> |The _ChildObjectTypes_ parameter specifies what type of object the permission should be removed from. <br/> The _ChildObjectTypes_ parameter can only be used if the _AccessRights_ parameter is set to `CreateChild` or `DeleteChild`.  <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _Deny_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _Deny_ switch specifies whether the permission to remove is a deny permission. <br/> |
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |The _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> The _DomainController_ parameter isn't supported on Edge Transport servers. An Edge Transport server uses the local instance of Active Directory Lightweight Directory Services (AD LDS) to read and write data. <br/> |
| _ExtendedRights_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.ExtendedRightIdParameter[]  <br/> |The _ExtendedRights_ parameter specifies the extended rights to remove. <br/> |
| _InheritanceType_ <br/> |Optional  <br/> |System.DirectoryServices.ActiveDirectorySecurityInheritance  <br/> |The _InheritanceType_ parameter specifies whether permissions are inherited. <br/> |
| _InheritedObjectType_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.ADSchemaObjectIdParameter  <br/> |The _InheritedObjectType_ parameter specifies what kind of object inherits this access control entry (ACE). <br/> |
| _Properties_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.ADSchemaObjectIdParameter[]  <br/> |The _Properties_ parameter specifies what properties the object contains. <br/> The _Properties_ parameter can only be used if the _AccessRights_ parameter is set to `ReadProperty`,  `WriteProperty`, or  `Self`.  <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
