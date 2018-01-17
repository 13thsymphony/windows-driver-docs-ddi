---
UID: NE:wdm._REG_NOTIFY_CLASS
title: _REG_NOTIFY_CLASS
author: windows-driver-content
description: The REG_NOTIFY_CLASS enumeration type specifies the type of registry operation that the configuration manager is passing to a RegistryCallback routine.
old-location: kernel\reg_notify_class.htm
old-project: kernel
ms.assetid: 2ec47d47-1de3-43af-9a71-7fa366ba2d1a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _REG_NOTIFY_CLASS, REG_NOTIFY_CLASS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available for Windows XP and later versions of the Windows operating system, but some enumeration values are available only for specified later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: REG_NOTIFY_CLASS
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: REG_NOTIFY_CLASS
req.product: Windows 10 or later.
---

# _REG_NOTIFY_CLASS enumeration



## -description
The <b>REG_NOTIFY_CLASS</b> enumeration type specifies the type of registry operation that the configuration manager is passing to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine.



## -syntax

````
enum REG_NOTIFY_CLASS {
  RegNtDeleteKey, 
  RegNtPreDeleteKey                  = RegNtDeleteKey, 
  RegNtSetValueKey, 
  RegNtPreSetValueKey                = RegNtSetValueKey, 
  RegNtDeleteValueKey, 
  RegNtPreDeleteValueKey             = RegNtDeleteValueKey, 
  RegNtSetInformationKey, 
  RegNtPreSetInformationKey          = RegNtSetInformationKey, 
  RegNtRenameKey, 
  RegNtPreRenameKey                  = RegNtRenameKey, 
  RegNtEnumerateKey, 
  RegNtPreEnumerateKey               = RegNtEnumerateKey, 
  RegNtEnumerateValueKey, 
  RegNtPreEnumerateValueKey          = RegNtEnumerateValueKey, 
  RegNtQueryKey, 
  RegNtPreQueryKey                   = RegNtQueryKey, 
  RegNtQueryValueKey, 
  RegNtPreQueryValueKey              = RegNtQueryValueKey, 
  RegNtQueryMultipleValueKey, 
  RegNtPreQueryMultipleValueKey      = RegNtQueryMultipleValueKey, 
  RegNtPreCreateKey, 
  RegNtPostCreateKey, 
  RegNtPreOpenKey, 
  RegNtPostOpenKey, 
  RegNtKeyHandleClose, 
  RegNtPreKeyHandleClose             = RegNtKeyHandleClose, 
  RegNtPostDeleteKey, 
  RegNtPostSetValueKey, 
  RegNtPostDeleteValueKey, 
  RegNtPostSetInformationKey, 
  RegNtPostRenameKey, 
  RegNtPostEnumerateKey, 
  RegNtPostEnumerateValueKey, 
  RegNtPostQueryKey, 
  RegNtPostQueryValueKey, 
  RegNtPostQueryMultipleValueKey, 
  RegNtPostKeyHandleClose, 
  RegNtPreCreateKeyEx, 
  RegNtPostCreateKeyEx, 
  RegNtPreOpenKeyEx, 
  RegNtPostOpenKeyEx, 
  RegNtPreFlushKey, 
  RegNtPostFlushKey, 
  RegNtPreLoadKey, 
  RegNtPostLoadKey, 
  RegNtPreUnLoadKey, 
  RegNtPostUnLoadKey, 
  RegNtPreQueryKeySecurity, 
  RegNtPostQueryKeySecurity, 
  RegNtPreSetKeySecurity, 
  RegNtPostSetKeySecurity, 
  RegNtCallbackObjectContextCleanup, 
  RegNtPreRestoreKey, 
  RegNtPostRestoreKey, 
  RegNtPreSaveKey, 
  RegNtPostSaveKey, 
  RegNtPreReplaceKey, 
  RegNtPostReplaceKey, 
  RegNtPreQueryKeyName, 
  RegNtPostQueryKeyName, 
  MaxRegNtNotifyClass 

};
````


## -enum-fields

### -field RegNtDeleteKey

Specifies that a thread is attempting to delete a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreDeleteKey

Specifies that a thread is attempting to delete a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtSetValueKey

Specifies that a thread is attempting to set a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreSetValueKey

Specifies that a thread is attempting to set a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtDeleteValueKey

Specifies that a thread is attempting to delete a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreDeleteValueKey

Specifies that a thread is attempting to delete a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtSetInformationKey

Specifies that a thread is attempting to set the metadata for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreSetInformationKey

Specifies that a thread is attempting to set the metadata for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtRenameKey

Specifies that a thread is attempting to rename a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreRenameKey

Specifies that a thread is attempting to rename a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtEnumerateKey

Specifies that a thread is attempting to enumerate a subkey of a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreEnumerateKey

Specifies that a thread is attempting to enumerate a subkey of a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtEnumerateValueKey

Specifies that a thread is attempting to enumerate a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreEnumerateValueKey

Specifies that a thread is attempting to enumerate a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtQueryKey

Specifies that a thread is attempting to read the metadata for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreQueryKey

Specifies that a thread is attempting to read the metadata for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtQueryValueKey

Specifies that a thread is attempting to read a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreQueryValueKey

Specifies that a thread is attempting to read a value entry for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtQueryMultipleValueKey

Specifies that a thread is attempting to query multiple value entries for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on only Windows XP.


### -field RegNtPreQueryMultipleValueKey

Specifies that a thread is attempting to query multiple value entries for a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPreCreateKey

Specifies that a thread is attempting to create a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows XP and later versions of the Windows operating system.


### -field RegNtPostCreateKey

Specifies that a thread has successfully created a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows XP and later versions of the Windows operating system.


### -field RegNtPreOpenKey

Specifies that a thread is attempting to open an existing key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows XP and later versions of the Windows operating system.


### -field RegNtPostOpenKey

Specifies that a thread has successfully opened an existing key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows XP and later versions of the Windows operating system.


### -field RegNtKeyHandleClose

Specifies that a thread is attempting to close a key handle. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value only on Windows XP.


### -field RegNtPreKeyHandleClose

Specifies that a thread is attempting to close a key handle. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system. Drivers can monitor this registry operation but they cannot block or modify it.


### -field RegNtPostDeleteKey

Specifies that the system has attempted to delete the key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostSetValueKey

Specifies that the system has attempted to set a value entry for a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostDeleteValueKey

Specifies that the system has attempted to delete a value entry for a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostSetInformationKey

Specifies that the system has attempted to set the key's metadata. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostRenameKey

Specifies that the system has attempted to rename the key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostEnumerateKey

Specifies that the system has attempted to enumerate the subkey of a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostEnumerateValueKey

Specifies that the system has attempted to enumerate the value entry of a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostQueryKey

Specifies that the system has attempted to query the metadata for a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostQueryValueKey

Specifies that the system has attempted to query a value entry for the key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostQueryMultipleValueKey

Specifies that the system has attempted to query multiple value entries for the key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostKeyHandleClose

Specifies that the system has attempted to close a key handle. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPreCreateKeyEx

Specifies that a thread is attempting to create a key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostCreateKeyEx

Specifies that the system has attempted to create a key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPreOpenKeyEx

Specifies that a thread is attempting to open an existing key. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPostOpenKeyEx

Specifies that the system has attempted to open an existing key. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Server 2003 and later versions of the Windows operating system.


### -field RegNtPreFlushKey

Specifies that a thread is attempting to write a key to disk. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPostFlushKey

Specifies that the system has attempted to write a key to disk. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPreLoadKey

Specifies that a thread is attempting to load a registry hive from a file. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPostLoadKey

Specifies that the system has attempted to load a registry hive from a file. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPreUnLoadKey

Specifies that a thread is attempting to unload a registry hive. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPostUnLoadKey

Specifies that the system has attempted to unload a registry hive. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPreQueryKeySecurity

Specifies that a thread is attempting to obtain a registry key's security information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPostQueryKeySecurity

Specifies that a thread has attempted to obtain a registry key's security information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPreSetKeySecurity

Specifies that a thread is attempting to set a registry key's security information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPostSetKeySecurity

Specifies that a thread has attempted to set a registry key's security information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtCallbackObjectContextCleanup


      Specifies that the driver has called <a href="..\wdm\nf-wdm-cmunregistercallback.md">CmUnRegisterCallback</a> or the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine has just finished processing a <b>RegNtPreKeyHandleClose</b> class value. Use this value on Windows Vista and later versions of the Windows operating system.


### -field RegNtPreRestoreKey

Specifies that a thread is attempting to restore a registry key's information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system. 


### -field RegNtPostRestoreKey

Specifies that a thread has attempted to restore a registry key's information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


### -field RegNtPreSaveKey

Specifies that a thread is attempting to save a registry key's information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


### -field RegNtPostSaveKey

Specifies that a thread has attempted to save a registry key's information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


### -field RegNtPreReplaceKey

Specifies that a thread is attempting to replace a registry key's information. This value indicates a pre-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


### -field RegNtPostReplaceKey

Specifies that a thread has attempted to replace a registry key's information. This value indicates a post-notification call to <i>RegistryCallback</i>. Use this value on Windows Vista SP2 and later versions of the Windows operating system.


### -field RegNtPreQueryKeyName

Specifies that a thread is attempting to obtain the full path of a registry key. Use this value on Windows 10 and later versions of the Windows operating system.


### -field RegNtPostQueryKeyName

Specifies that a thread has attempted to obtain the full path of a registry key. Use this value on Windows 10 and later versions of the Windows operating system.


### -field MaxRegNtNotifyClass

Specifies the maximum value in this enumeration type.


## -remarks
When the configuration manager calls a driver's <i>RegistryCallback</i> routine, it passes a <b>REG_NOTIFY_CLASS</b> enumeration value to the routine. The configuration manager also passes a notification-specific structure that contains information about the notification. For a list of these structures, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-cmunregistercallback.md">CmUnRegisterCallback</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_NOTIFY_CLASS enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

