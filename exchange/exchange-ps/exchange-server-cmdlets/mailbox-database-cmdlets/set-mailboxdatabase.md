---
title: "Set-MailboxDatabase"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/16/2018
ms.audience: ITPro
ms.topic: reference
ms.prod: exchange-server-itpro
localization_priority: Normal
ms.assetid: a01edc66-bc10-4f65-9df4-432cb9e88f58

description: "This cmdlet is available only in on-premises Exchange."
---

# Set-MailboxDatabase

This cmdlet is available only in on-premises Exchange. 
  
Use the **Set-MailboxDatabase** cmdlet to configure a variety of properties for a mailbox database.
  
For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://technet.microsoft.com/library/bb123552.aspx). 
  
```
Set-MailboxDatabase -Identity <DatabaseIdParameter> [-AllowFileRestore <$true | $false>] [-AutoDagExcludeFromMonitoring <$true | $false>] [-AutoDatabaseMountDial <Lossless | GoodAvailability | BestAvailability>] [-BackgroundDatabaseMaintenance <$true | $false>] [-BackgroundDatabaseMaintenanceDelay <Int32>] [-BackgroundDatabaseMaintenanceSerialization <$true | $false>] [-CachedClosedTables <Int32>] [-CachePriority <Int32>] [-CafeEndpoints <String[]>] [-CalendarLoggingQuota <Unlimited>] [-CircularLoggingEnabled <$true | $false>] [-Confirm [<SwitchParameter>]] [-DatabaseExtensionSize <Int32>] [-DatabaseGroup <String>] [-DataMoveReplicationConstraint <None | SecondCopy | SecondDatacenter | AllDatacenters | AllCopies | CINoReplication | CISecondCopy | CISecondDatacenter | CIAllDatacenters | CIAllCopies>] [-DeletedItemRetention <EnhancedTimeSpan>] [-DomainController <Fqdn>] [-EventHistoryRetentionPeriod <EnhancedTimeSpan>] [-IndexEnabled <$true | $false>] [-IsExcludedFromInitialProvisioning <$true | $false>] [-IsExcludedFromProvisioning <$true | $false>] [-IsExcludedFromProvisioningByOperator <$true | $false>] [-IsExcludedFromProvisioningDueToLogicalCorruption <$true | $false>] [-IsExcludedFromProvisioningReason <String>] [-IssueWarningQuota <Unlimited>] [-IsSuspendedFromProvisioning <$true | $false>] [-JournalRecipient <RecipientIdParameter>] [-LogBuffers <Int32>] [-LogCheckpointDepth <Int32>] [-MailboxLoadBalanceEnabled <$true | $false>] [-MailboxLoadBalanceMaximumEdbFileSize <ByteQuantifiedSize>] [-MailboxLoadBalanceOverloadedThreshold <Int32>] [-MailboxLoadBalanceRelativeLoadCapacity <Int32>] [-MailboxLoadBalanceUnderloadedThreshold <Int32>] [-MailboxProvisioningAttributes <MailboxProvisioningAttributes>] [-MailboxRetention <EnhancedTimeSpan>] [-MaintenanceSchedule <Schedule>] [-MasterDatabaseAvailabilityGroup <DatabaseAvailabilityGroupIdParameter>] [-MasterServer <ServerIdParameter>] [-MaximumBackgroundDatabaseMaintenanceInterval <Int32>] [-MaximumCursors <Int32>] [-MaximumOpenTables <Int32>] [-MaximumPreReadPages <Int32>] [-MaximumReplayPreReadPages <Int32>] [-MaximumSessions <Int32>] [-MaximumTemporaryTables <Int32>] [-MaximumVersionStorePages <Int32>] [-MetaCacheDatabaseMaxCapacityInBytes <Int64>] [-MimimumBackgroundDatabaseMaintenanceInterval <Int32>] [-MountAtStartup <$true | $false>] [-Name <String>] [-OfflineAddressBook <OfflineAddressBookIdParameter>] [-PreferredVersionStorePages <Int32>] [-ProhibitSendQuota <Unlimited>] [-ProhibitSendReceiveQuota <Unlimited>] [-PublicFolderDatabase <DatabaseIdParameter>] [-QuotaNotificationSchedule <Schedule>] [-RecoverableItemsQuota <Unlimited>] [-RecoverableItemsWarningQuota <Unlimited>] [-ReplayBackgroundDatabaseMaintenance <$true | $false>] [-ReplayBackgroundDatabaseMaintenanceDelay <Int32>] [-ReplayCachePriority <Int32>] [-ReplayCheckpointDepth <Int32>] [-RetainDeletedItemsUntilBackup <$true | $false>] [-WhatIf [<SwitchParameter>]]

```

## Examples
<a name="Examples"> </a>

### Example 1

This example sets the length of time that deleted items are retained. If a specific mailbox has its own item retention set, that value is used instead of this value, which is set on the mailbox database.
  
```
Set-MailboxDatabase "Mailbox Database01" -DeletedItemRetention 7.00:00:00
```

## Detailed Description
<a name="DetailedDescription"> </a>

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://technet.microsoft.com/library/mt432940.aspx).
  
## Parameters
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _Identity_ <br/> |Required  <br/> |Microsoft.Exchange.Configuration.Tasks.DatabaseIdParameter  <br/> | The _Identity_ parameter specifies the mailbox database that you want to modify. You can use any value that uniquely identifies the database. For example: <br/>  Name <br/>  Distinguished name (DN) <br/>  GUID <br/> |
| _AllowFileRestore_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _AllowFileRestore_ parameter specifies whether to allow a database to be restored from a backup. Valid values are: <br/>  `$true`: You can replace an existing database with a newly-created database. You can mount a database that doesn't match the database entry in Active Directory.  <br/>  `$false`: You can't replace an existing database with a newly-created database. You can't mount a database that doesn't match the database entry in Active Directory. This is the default value.  <br/> |
| _AutoDagExcludeFromMonitoring_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _AutoDagExcludedFromMonitoring_parameter specifies whether to exclude the mailbox database from the **ServerOneCopyMonitor**, which alerts an administrator when a replicated database has only one healthy copy available. Valid values are: <br/>  `$true`: No alert is issued when there's only one healthy copy of the replicated database.  <br/>  `$false`: An alert is issued when there's only one healthy copy of the replicated database. This is the default value.  <br/> |
| _AutoDatabaseMountDial_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Directory.SystemConfiguration.AutoDatabaseMountDial  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _BackgroundDatabaseMaintenance_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _BackgroundDatabaseMaintenance_ parameter specifies whether the Extensible Storage Engine (ESE) performs database maintenance. Valid values are: <br/>  `$true`: The mailbox database reads the object during database mount and initializes the database to perform background maintenance. This is the default value.  <br/>  `$false`: The mailbox database reads the object during database mount and initializes the database without the option to perform background maintenance.  <br/> |
| _BackgroundDatabaseMaintenanceDelay_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _BackgroundDatabaseMaintenanceSerialization_ <br/> |Optional  <br/> |System.Boolean  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _CachedClosedTables_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _CachePriority_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _CafeEndpoints_ <br/> |Optional  <br/> |System.String[]  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _CalendarLoggingQuota_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Unlimited  <br/> | The _CalendarLoggingQuota_ parameter specifies the maximum size of the log in the Recoverable Items folder of the mailbox that stores changes to calendar items. When the log exceeds this size, calendar logging is disabled until messaging records management (MRM) removes older calendar logs to free up more space. <br/>  A valid value is a number up to 1.999999999 terabytes (2199023254528 bytes) or the value `unlimited`. The default value is 6 gigabytes (6442450944 bytes).  <br/>  When you enter a value, qualify the value with one of the following units: <br/>  `B` (bytes) <br/>  `KB` (kilobytes) <br/>  `MB` (megabytes) <br/>  `GB` (gigabytes) <br/>  `TB` (terabytes) <br/>  Unqualified values are typically treated as bytes, but small values may be rounded up to the nearest kilobyte. <br/>  The value of this parameter must be less than or equal to the value of the _RecoverableItemsQuota_ parameter. <br/>  This setting applies to all mailboxes in the database that don't have their own calendar logging quota configured. <br/> |
| _CircularLoggingEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _CircularLoggingEnabled_ parameter specifies whether circular logging is enabled for the database. Valid values are: <br/>  `$true`: Circular logging is enabled.  <br/>  `$false`: Circular logging is disabled. This is the default value.  <br/>  For more information about circular logging, see[Exchange Native Data Protection](https://technet.microsoft.com/library/394fc4ed-fa02-41fa-9159-cc2754ff8875.aspx#ENDP).  <br/> |
| _Confirm_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | The _Confirm_ switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding. <br/>  Destructive cmdlets (for example, **Remove-\*** cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.  <br/>  Most other cmdlets (for example, **New-\*** and **Set-\*** cmdlets) don't have a built-in pause. For these cmdlets, specifying the _Confirm_ switch without a value introduces a pause that forces you acknowledge the command before proceeding. <br/> |
| _DatabaseExtensionSize_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _DatabaseGroup_ <br/> |Optional  <br/> |System.String  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _DataMoveReplicationConstraint_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Directory.SystemConfiguration.DataMoveReplicationConstraintParameter  <br/> | The _DataMoveReplicationConstraint_ parameter specifies the throttling behavior for high availability mailbox moves. Valid values are: <br/>  `None`: Moves shouldn't be throttled to ensure high availability. Use this setting if the database isn't part of a database availability group (DAG).  <br/>  `SecondCopy`: At least one passive mailbox database copy must have the most recent changes synchronized. This is the default value. Use this setting to indicate that the database is replicated to one or more mailbox database copies.  <br/>  `SecondDatacenter`: At least one passive mailbox database copy in another Active Directory site must have the most recent changes replicated. Use this setting to indicate that the database is replicated to database copies in multiple Active Directory sites.  <br/> > [!NOTE]>  Any value other than `None` enables the Microsoft Exchange Mailbox Replication service to coordinate with Active Manager. For more information, see[Active Manager](https://technet.microsoft.com/library/f4be27b7-1d7c-47b4-87ac-bfdfcc046f00.aspx).           |
| _DeletedItemRetention_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.EnhancedTimeSpan  <br/> |The _DeletedItemRetention_ parameter specifies the length of time to keep deleted items in the **Recoverable Items\Deletions** folder in mailboxes. Items are moved to this folder when the user deletes items from the Deleted Items folder, empties the Deleted Items folder, or deletes items by using Shift+Delete. <br/> To specify a value, enter it as a time span:  `dd.hh:mm:ss` where `dd` = days, `hh` = hours, `mm` = minutes, and `ss` = seconds. <br/> Valid values are  `00:00:00` to `24855.03:14:07`. The default value is  `14.00:00:00` (14 days). <br/>  This setting applies to all mailboxes in the database that don't have their own deleted item retention value configured. <br/> For more information, see [Recoverable Items Folder](https://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx).  <br/> |
| _DomainController_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Fqdn  <br/> |The _DomainController_ parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, `dc01.contoso.com`.  <br/> |
| _EventHistoryRetentionPeriod_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.EnhancedTimeSpan  <br/> |The _EventHistoryRetentionPeriod_ parameter specifies the length of time to keep event data. This event data is stored in the event history table in the Exchange store. It includes information about changes to various objects in the mailbox database. You can use this parameter to prevent the event history table from becoming too large and using too much disk space. <br/> To specify a value, enter it as a time span:  `dd.hh:mm:ss` where `dd` = days, `hh` = hours, `mm` = minutes, and `ss` = seconds. <br/> Valid values are  `00:00:01` to `30.00:00:00`. The default value is  `7.00:00:00` (7 days). <br/> |
| _IndexEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _IndexEnabled_ parameter specifies whether Exchange Search indexes the mailbox database. Valid values are: <br/>  `$true`: Exchange Search indexes the mailbox database. This is the default value.  <br/>  `$false`: Exchange Search doesn't index the mailbox database.  <br/> |
| _IsExcludedFromInitialProvisioning_ <br/> |Optional  <br/> |System.Boolean  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _IsExcludedFromProvisioning_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _IsExcludedFromProvisioning_ parameter specifies whether to exclude the database from the mailbox provisioning load balancer that distributes new mailboxes randomly and evenly across the available databases. Valid values are: <br/>  `$true`: The database is excluded from new or move mailbox operations when you don't specify the target mailbox database.  <br/>  `$false`: The database can be used in new or move mailbox operations when you don't specify the target mailbox database. This is the default value.  <br/>  The value is automatically set to `$true` when you set the _IsExcludedFromProvisioningDueToLogicalCorruption_ parameter to `$true`, and isn't changed back to  `$false` when you set the _IsExcludedFromProvisioningDueToLogicalCorruption_ parameter back to `$false`. In the case of database corruption, you should set the _IsExcludedFromProvisioning_ parameter back to `$false` only after you fix the corruption issue or recreate the database. <br/> |
| _IsExcludedFromProvisioningByOperator_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _IIsExcludedFromProvisioningByOperator_ parameter specifies whether to exclude the database from the mailbox provisioning load balancer that distributes new mailboxes randomly and evenly across the available databases. <br/>  Valid values are: <br/>  `$true`: Indicates that you manually excluded the database. The database is excluded from new or move mailbox operations when you don't specify the target mailbox database.  <br/>  `$false`: The database can be used in new or move mailbox operations when you don't specify the target mailbox database. This is the default value.  <br/>  Note that setting this parameter to the value `$true` has these additional effects on the database: <br/>  The _IsExcludedFromProvisioningReason_ parameter requires a value if it doesn't already have one. <br/>  The unmodifiable **IsExcludedFromProvisioningBy** property is populated with your user account. <br/> |
| _IsExcludedFromProvisioningDueToLogicalCorruption_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _IsExcludedFromProvisioningDueToLogicalCorruption_ parameter specifies whether to exclude the database from the mailbox provisioning load balancer that distributes new mailboxes randomly and evenly across the available databases. <br/>  Valid values are: <br/>  `$true`: Indicates that you excluded the database due to database corruption. The database is excluded from new or move mailbox operations when you don't specify the target mailbox database.  <br/>  `$false`: This is the default value. The database can be used in new or move mailbox operations when you don't specify the target mailbox database. You should manually configure this value only after the database corruption is fixed, or after the database is recreated.  <br/>  Note that setting this parameter to the value `$true` has these additional effects on the database: <br/>  The _IsExcludedFromProvisioningReason_ parameter requires a value if it doesn't already have one. <br/>  The unmodifiable **IsExcludedFromProvisioningBy** property is populated with your user account. <br/>  The **IsExcludedFromProvisioning** property is automatically set to `$true`.  <br/> |
| _IsExcludedFromProvisioningReason_ <br/> |Optional  <br/> |System.String  <br/> | The _IsExcludedFromProvisioningReason_ parameter specifies the reason why you excluded the mailbox database from the mailbox provisioning load balancer. If the value contains spaces, enclose the value in quotation marks ("). The value must contain at least 10 characters. <br/>  This parameter requires a value when you set any of the following parameters to `$true`:  <br/> _IsExcludedFromProvisioning_ <br/> _IsExcludedFromProvisioningByOperator_ <br/> _IsSuspendedFromProvisioning_ <br/> |
| _IssueWarningQuota_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Unlimited  <br/> | The _IssueWarningQuota_ parameter specifies the warning threshold for the size of the mailbox. If the mailbox reaches or exceeds this size, the user receives a descriptive warning message. <br/>  A valid value is a number up to 1.999999999 terabytes (2199023254528 bytes) or the value `unlimited`. When you enter a number, you can qualify it with one of the following units:  <br/>  `B` (bytes) <br/>  `KB` (kilobytes) <br/>  `MB` (megabytes) <br/>  `GB` (gigabytes) <br/>  `TB` (terabytes) <br/>  Unqualified values are typically treated as bytes, but small values may be rounded up to the nearest kilobyte. <br/>  The _IssueWarningQuota_ value must be less than or equal to the _ProhibitSendReceiveQuota_ value. <br/>  This setting applies to all mailboxes in the database that don't have their own warning quota configured. The default value is 1.899 gigabytes (2,039,480,320 bytes). <br/> |
| _IsSuspendedFromProvisioning_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _IsSuspendedFromProvisioning_ parameter specifies whether to exclude the database from the mailbox provisioning load balancer that distributes new mailboxes randomly and evenly across the available databases. Valid values are: <br/>  `$true`: Indicates that you don't want the exclusion to be permanent. The database is excluded from new or move mailbox operations when you don't specify the target mailbox database.  <br/>  `$false`: The database can be used in new or move mailbox operations when you don't specify the target mailbox database. This is the default value.  <br/>  Note that setting this parameter to the value `$true` has these additional effects on the database: <br/>  The _IsExcludedFromProvisioningReason_ parameter requires a value if it doesn't already have one. <br/>  The unmodifiable **IsExcludedFromProvisioningBy** property is populated with your user account. <br/> |
| _JournalRecipient_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.RecipientIdParameter  <br/> | The _JournalRecipient_ parameter specifies the journal recipient to use for per-database journaling for all mailboxes on the database. You can use any value that uniquely identifies the recipient. For example: <br/>  For example: <br/>  Name <br/>  Display name <br/>  Alias <br/>  Distinguished name (DN) <br/>  Canonical DN <br/>  Email address <br/>  GUID <br/> |
| _LogBuffers_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _LogCheckpointDepth_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MailboxLoadBalanceEnabled_ <br/> |Optional  <br/> |System.Boolean  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MailboxLoadBalanceMaximumEdbFileSize_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.ByteQuantifiedSize  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MailboxLoadBalanceOverloadedThreshold_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MailboxLoadBalanceRelativeLoadCapacity_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MailboxLoadBalanceUnderloadedThreshold_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MailboxProvisioningAttributes_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Directory.SystemConfiguration.MailboxProvisioningAttributes  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MailboxRetention_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.EnhancedTimeSpan  <br/> |The _MailboxRetention_ parameter specifies the length of time to keep deleted mailboxes before they are permanently deleted orpurged.  <br/> To specify a value, enter it as a time span:  `dd.hh:mm:ss` where `dd` = days, `hh` = hours, `mm` = minutes, and `ss` = seconds. <br/> Valid values are  `00:00:00` to `24855.03:14:07`. The default value is  `30.00:00:00` (30 days). <br/> |
| _MaintenanceSchedule_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Schedule  <br/> |This parameter has been deprecated and is no longer used.  <br/> Although you can use this parameter to change the **MaintenanceSchedule** property of the database, the value is ignored. <br/> |
| _MasterDatabaseAvailabilityGroup_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.DatabaseAvailabilityGroupIdParameter  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MasterServer_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.ServerIdParameter  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MaximumBackgroundDatabaseMaintenanceInterval_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MaximumCursors_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MaximumOpenTables_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MaximumPreReadPages_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MaximumReplayPreReadPages_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MaximumSessions_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MaximumTemporaryTables_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MaximumVersionStorePages_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MetaCacheDatabaseMaxCapacityInBytes_ <br/> |Optional  <br/> |System.Int64  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MimimumBackgroundDatabaseMaintenanceInterval_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _MountAtStartup_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _MountAtStartup_ parameter specifies whether to mount the mailbox database when the Microsoft Exchange Information Store service starts. Valid values are: <br/>  `$true`: The database is mounted when the service starts. This is the default value.  <br/>  `$false`: The database isn't mounted when the service starts.  <br/> |
| _Name_ <br/> |Optional  <br/> |System.String  <br/> |The _Name_ parameter specifies the unique name of the mailbox database. The maximum length is 64 characters. If the value contains spaces, enclose the value in quotation marks ("). <br/> |
| _OfflineAddressBook_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.OfflineAddressBookIdParameter  <br/> | The _OfflineAddressBook_ parameter specifies the offline address book that's associated with the mailbox database. You can use any value that uniquely identifies the offline address book. For example: <br/>  Name <br/>  Distinguished name (DN) <br/>  GUID <br/>  By default, this setting is blank ( `$null`).  <br/> |
| _PreferredVersionStorePages_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _ProhibitSendQuota_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Unlimited  <br/> | The _ProhibitSendQuota_ parameter specifies a size limit for the mailbox. If the mailbox reaches or exceeds this size, the mailbox can't send new messages, and the user receives a descriptive warning message. <br/>  A valid value is a number up to 1.999999999 terabytes (2199023254528 bytes) or the value `unlimited`. When you enter a number, you can qualify it with one of the following units:  <br/>  `B` (bytes) <br/>  `KB` (kilobytes) <br/>  `MB` (megabytes) <br/>  `GB` (gigabytes) <br/>  `TB` (terabytes) <br/>  Unqualified values are typically treated as bytes, but small values may be rounded up to the nearest kilobyte. <br/>  The _ProhibitSendQuota_ value must be less than or equal to the _ProhibitSendReceiveQuota_ value. <br/>  This settings applies to all mailboxes in the database that don't have their own prohibit send quota configured. The default value is 2 gigabytes (2147483648 bytes). <br/> |
| _ProhibitSendReceiveQuota_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Unlimited  <br/> | The _ProhibitSendReceiveQuota_ parameter specifies a size limit for the mailbox. If the mailbox reaches or exceeds this size, the mailbox can't send or receive new messages. Messages sent to the mailbox are returned to the sender with a descriptive error message. This value effectively determines the maximum size of the mailbox. <br/>  A valid value is a number up to 1.999999999 terabytes (2199023254528 bytes) or the value `unlimited`. When you enter a number, you can qualify it with one of the following units:  <br/>  `B` (bytes) <br/>  `KB` (kilobytes) <br/>  `MB` (megabytes) <br/>  `GB` (gigabytes) <br/>  `TB` (terabytes) <br/>  Unqualified values are typically treated as bytes, but small values may be rounded up to the nearest kilobyte. <br/>  The value must be greater than or equal to the _ProhibitSendQuota_ or _IssueWarningQuota_ values. <br/>  This setting applies to all mailboxes in the database that don't have their own prohibit send receive quota configured. The default value is 2.99804 gigabytes (2469396480 bytes) <br/> |
| _PublicFolderDatabase_ <br/> |Optional  <br/> |Microsoft.Exchange.Configuration.Tasks.DatabaseIdParameter  <br/> |This parameter has been deprecated and is no longer used.  <br/> |
| _QuotaNotificationSchedule_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Schedule  <br/> |This parameter has been deprecated and is no longer used.  <br/> |
| _RecoverableItemsQuota_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Unlimited  <br/> | The _RecoverableItemsQuota_ parameter specifies the maximum size for the Recoverable Items folder of the mailbox. If the Recoverable Items folder reaches or exceeds this size, it no longer accepts messages. <br/>  A valid value is a number up to 1.999999999 terabytes (2199023254528 bytes) or the value `unlimited`. The default value is 30 gigabytes (32212254720 bytes).  <br/>  When you enter a number, you can qualify it with one of the following units: <br/>  `B` (bytes) <br/>  `KB` (kilobytes) <br/>  `MB` (megabytes) <br/>  `GB` (gigabytes) <br/>  `TB` (terabytes) <br/>  Unqualified values are typically treated as bytes, but small values may be rounded up to the nearest kilobyte. <br/>  The _RecoverableItemsQuota_ value must be greater than or equal to the _RecoverableItemsWarningQuota_ value. <br/>  This settings applies to all mailboxes in the database that don't have their own Recoverable Items quota configured. <br/> |
| _RecoverableItemsWarningQuota_ <br/> |Optional  <br/> |Microsoft.Exchange.Data.Unlimited  <br/> | The _RecoverableItemsWarningQuota_ parameter specifies the warning threshold for the size of the Recoverable Items folder for the mailbox. If the Recoverable Items folder reaches or exceeds this size, Exchange logs an event to the application event log. <br/>  A valid value is a number up to 1.999999999 terabytes (2199023254528 bytes) or the value `unlimited`. The default value is 20 gigabytes (21474836480 bytes).  <br/>  When you enter a number, you can qualify it with one of the following units: <br/>  `B` (bytes) <br/>  `KB` (kilobytes) <br/>  `MB` (megabytes) <br/>  `GB` (gigabytes) <br/>  `TB` (terabytes) <br/>  Unqualified values are typically treated as bytes, but small values may be rounded up to the nearest kilobyte. <br/>  The _RecoverableItemsWarningQuota_ value must be less than or equal to the _RecoverableItemsQuota_ value. <br/>  This settings applies to all mailboxes in the database that don't have their own Recoverable Items warning quota configured. <br/> |
| _ReplayBackgroundDatabaseMaintenance_ <br/> |Optional  <br/> |System.Boolean  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _ReplayBackgroundDatabaseMaintenanceDelay_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _ReplayCachePriority_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _ReplayCheckpointDepth_ <br/> |Optional  <br/> |System.Int32  <br/> |This parameter is reserved for internal Microsoft use.  <br/> |
| _RetainDeletedItemsUntilBackup_ <br/> |Optional  <br/> |System.Boolean  <br/> | The _RetainDeletedItemsUntilBackup_ parameter specifies whether to keep items in the **Recoverable Items\Deletions** folder of the mailbox until the next database backup occurs. Valid values are: <br/>  `$true`: Deleted items are kept until the next mailbox database backup. This value could effectively override the deleted item retention and recoverable items quota values.  <br/>  `$false`: Retention of deleted items doesn't depend on a backup of the mailbox database. This is the default value.  <br/>  For more information, see[Recoverable Items folder in Exchange 2016](https://technet.microsoft.com/library/ee364755.aspx).  <br/>  This settings applies to all mailboxes in the database that don't have this value specifically configured. <br/> |
| _WhatIf_ <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |The _WhatIf_ switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch. <br/> |
   
## Input Types
<a name="InputTypes"> </a>

To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data. 
  
## Return Types
<a name="ReturnTypes"> </a>

To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](http://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data. 
  
