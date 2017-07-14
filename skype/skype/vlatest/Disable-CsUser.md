---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015
schema: 2.0.0
---

# Disable-CsUser

## SYNOPSIS
**Below Content Applies To:** Lync Server 2010

Modifies the Active Directory account of the specified user or users; this modification prevents users from using Microsoft Lync Server 2010 clients such as Microsoft Lync 2010.
Disable-CsUser only restricts activity related to Lync Server 2010; it does not disable or remove a user's Active Directory account.

**Below Content Applies To:** Lync Server 2013

Modifies the Active Directory account of the specified user or users; this modification prevents users from using Lync Server clients such as Microsoft Lync 2013 Preview.
Disable-CsUser only restricts activity related to Lync Server; it does not disable or remove a user's Active Directory account.
This cmdlet was introduced in Lync Server 2010.

**Below Content Applies To:** Skype for Business Server 2015

Modifies the Active Directory account of the specified user or users; this modification prevents users from using Skype for Business Server 2015 clients such as Skype for Business.
The Disable-CsUser cmdlet only restricts activity related to Skype for Business Server 2015; it does not disable or remove a user's Active Directory account.
This cmdlet was introduced in Lync Server 2010.



## SYNTAX

```
Disable-CsUser [-Identity] <UserIdParameter> [-DomainController <Fqdn>] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
**Below Content Applies To:** Lync Server 2010

The Disable-CsUser cmdlet deletes all the attribute information related to Lync Server from an Active Directory user account; this prevents the user from logging on to Lync Server.
When you run Disable-CsUser all the Lync Server-related attributes are removed from an account, including the Identities of any per-user policies that have been assigned to that account.
You can later re-enable the account by using the Enable-CsUser cmdlet.
However, all the Lync Server-related information (such as policy assignments) previously associated with that account will have to be re-created.
If you want to prevent a user from logging on to Lync Server, but do not want to lose all of their account information, use Set-CsUser instead.
For details, see the Set-CsUser help topic.

After an account has been disabled with Disable-CsUser, the affected user will no longer be returned by the Get-CsUser cmdlet; that's because that user no longer has a valid Lync Server account.
To retrieve information for the disabled user account, use Get-CsAdUser.

In addition, user data belonging to the deleted user account will be removed from the backend databases; for example, the user will be removed from Contacts lists in the organization, and any conferences scheduled by that user will be deleted.

Who can run this cmdlet: By default, members of the following groups are authorized to run the Disable-CsUser cmdlet locally: RTCUniversalUserAdmins.
To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object  {$_.Cmdlets -match "Disable-CsUser"}

**Below Content Applies To:** Lync Server 2013

The Disable-CsUser cmdlet deletes all the attribute information related to Lync Server from an Active Directory user account; this prevents the user from logging on to Lync Server.
When you run Disable-CsUser all the Lync Server-related attributes are removed from an account, including the Identities of any per-user policies that have been assigned to that account.
You can later re-enable the account by using the Enable-CsUser cmdlet.
However, all the Lync Server-related information (such as policy assignments) previously associated with that account will have to be re-created.
If you want to prevent a user from logging on to Lync Server, but do not want to lose all of their account information, use Set-CsUser instead.
For details, see the Set-CsUser help topic.

After an account has been disabled with Disable-CsUser, the affected user will no longer be returned by the Get-CsUser cmdlet; that's because that user no longer has a valid Lync Server account.
To retrieve information for the disabled user account, use Get-CsAdUser.

In addition, user data belonging to the deleted user account will be removed from the backend databases; for example, the user will be removed from Contacts lists in the organization, and any conferences scheduled by that user will be deleted.

Who can run this cmdlet: By default, members of the following groups are authorized to run the Disable-CsUser cmdlet locally: RTCUniversalUserAdmins.
To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Disable-CsUser"}

**Below Content Applies To:** Skype for Business Server 2015

The Disable-CsUser cmdlet deletes all the attribute information related to Skype for Business Server 2015 from an Active Directory user account; this prevents the user from logging on to Skype for Business Server 2015.
When you run the Disable-CsUser cmdlet all the Skype for Business Server 2015-related attributes are removed from an account, including the Identities of any per-user policies that have been assigned to that account.
You can later re-enable the account by using the Enable-CsUser cmdlet.
However, all the Skype for Business Server 2015-related information (such as policy assignments) previously associated with that account will have to be re-created.
If you want to prevent a user from logging on to Skype for Business Server 2015, but do not want to lose all of their account information, use the Set-CsUser cmdlet instead.
For details, see the Set-CsUser cmdlet help topic.

After an account has been disabled with the Disable-CsUser cmdlet, the affected user will no longer be returned by the Get-CsUser cmdlet; that's because that user no longer has a valid Skype for Business Server 2015 account.
To retrieve information for the disabled user account, use the Get-CsAdUser cmdlet.

In addition, user data belonging to the deleted user account will be removed from the backend databases; for example, the user will be removed from Contacts lists in the organization, and any conferences scheduled by that user will be deleted.



## EXAMPLES

### -------------------------- Example 1 -------------------------- (Lync Server 2010)
```
Disable-CsUser -Identity "Ken Myer"
```

The preceding Example disables the Lync Server account for the user Ken Myer.
In this example, the user's display name is used to indicate his Identity.

### -------------------------- EXAMPLE 1 -------------------------- (Lync Server 2013)
```

```

Example 1 disables the Lync Server account for the user Ken Myer.
In this example, the user's display name is used to indicate his Identity.

Disable-CsUser -Identity "Ken Myer"

### -------------------------- EXAMPLE 1 -------------------------- (Skype for Business Server 2015)
```

```

Example 1 disables the Skype for Business Server 2015 account for the user Ken Myer.
In this example, the user's display name is used to indicate his Identity.

Disable-CsUser -Identity "Ken Myer"

### -------------------------- Example 2 -------------------------- (Lync Server 2010)
```
Get-CsUser -LDAPFilter "Department=Finance" | Disable-CsUser
```

In Example 2, all the users in the Finance department have their Lync Server accounts disabled.
To carry out this task, the command first uses the Get-CsUser cmdlet and the LDAPFilter parameter to return a collection of all the users who belong to the Finance department.
That collection is then piped to Disable-CsUser, which disables each account in the collection.

### -------------------------- EXAMPLE 2 -------------------------- (Lync Server 2013)
```

```

In Example 2, all the users in the Finance department have their Lync Server accounts disabled.
To carry out this task, the command first uses the Get-CsUser cmdlet and the LdapFilter parameter to return a collection of all the users who belong to the Finance department.
That collection is then piped to Disable-CsUser, which disables each account in the collection.

Get-CsUser -LdapFilter "Department=Finance" | Disable-CsUser

### -------------------------- EXAMPLE 2 -------------------------- (Skype for Business Server 2015)
```

```

In Example 2, all the users in the Finance department have their Skype for Business Server 2015 accounts disabled.
To carry out this task, the command first uses the Get-CsUser cmdlet and the LdapFilter parameter to return a collection of all the users who belong to the Finance department.
That collection is then piped to the Disable-CsUser cmdlet, which disables each account in the collection.

Get-CsUser -LdapFilter "Department=Finance" | Disable-CsUser

### -------------------------- Example 3 -------------------------- (Lync Server 2010)
```
Get-CsUser -UnassignedUser | Disable-CsUser
```

In the preceding example, all the user accounts not currently assigned to a Registrar pool are disabled.
To do this, Get-CsUser is called, along with the UnassignedUser parameter.
This parameter restricts the returned data to users who have valid user accounts but are not assigned to a Registrar pool.
That collection is then piped to Disable-CsUser, which disables each account in the collection.

### -------------------------- EXAMPLE 3 -------------------------- (Lync Server 2013)
```

```

In this example, all the user accounts not currently assigned to a Registrar pool are disabled.
To do this, Get-CsUser is called, along with the UnassignedUser parameter.
This parameter restricts the returned data to users who have valid user accounts but are not assigned to a Registrar pool.
That collection is then piped to Disable-CsUser, which disables each account in the collection.

Get-CsUser -UnassignedUser | Disable-CsUser

### -------------------------- EXAMPLE 3 -------------------------- (Skype for Business Server 2015)
```

```

In this example, all the user accounts not currently assigned to a Registrar pool are disabled.
To do this, the Get-CsUser cmdlet is called, along with the UnassignedUser parameter.
This parameter restricts the returned data to users who have valid user accounts but are not assigned to a Registrar pool.
That collection is then piped to the Disable-CsUser cmdlet, which disables each account in the collection.

Get-CsUser -UnassignedUser | Disable-CsUser

## PARAMETERS

### -Identity
Indicates the Identity of the user account to be disabled.
User Identities can be specified by using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer).
You can also reference a user account by using the Active Directory distinguished name.

You can use the asterisk (*) wildcard character when using the Display Name as the user Identity.
For example, the Identity "* Smith" returns all the users who have a display name that ends with the string value " Smith".

```yaml
Type: UserIdParameter
Parameter Sets: (All)
Aliases: 
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DomainController
Enables you to connect to the specified domain controller in order to disable a user account.
To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-cs-001) or its fully qualified domain name (FQDN) (for example, atl-cs-001.litwareinc.com).

```yaml
Type: Fqdn
Parameter Sets: (All)
Aliases: 
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Enables you to pass a user object through the pipeline that represents the user account being disabled.
By default, the Disable-CsUser cmdlet does not pass objects through the pipeline.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Describes what would happen if you executed the command without actually executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
String or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object.
Disable-CsUser accepts a pipelined string value representing the Identity of a user account that has been enabled for Lync Server.
The cmdlet also accepts pipelined instances if the Active Directory user object.

###  
String or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object.
Disable-CsUser accepts a pipelined string value representing the Identity of a user account that has been enabled for Lync Server.
The cmdlet also accepts pipelined instances of the Active Directory user object.

###  
String or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object.
The Disable-CsUser cmdlet accepts a pipelined string value representing the Identity of a user account that has been enabled for Skype for Business Server 2015.
The cmdlet also accepts pipelined instances of the Active Directory user object.

## OUTPUTS

###  
Disable-CsUser does not return a value or object.
Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.ADConnect.Schema.ADUser object.

###  
The Disable-CsUser cmdlet does not return a value or object.
Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.ADConnect.Schema.ADUser object.

## NOTES

## RELATED LINKS

[Online Version](http://technet.microsoft.com/EN-US/library/92e7e29e-2620-4852-9e4a-2fd3569bb095(OCS.14).aspx)

[Enable-CsUser]()

[Get-CsUser]()

[Online Version](http://technet.microsoft.com/EN-US/library/92e7e29e-2620-4852-9e4a-2fd3569bb095(OCS.15).aspx)

[Online Version](http://technet.microsoft.com/EN-US/library/92e7e29e-2620-4852-9e4a-2fd3569bb095(OCS.16).aspx)
