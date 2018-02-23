---
UID: NF:wdm.ZwCreateKey
title: ZwCreateKey function
author: windows-driver-content
description: The ZwCreateKey routine creates a new registry key or opens an existing one.
old-location: kernel\zwcreatekey.htm
old-project: kernel
ms.assetid: 333f54e8-738e-4d1f-8fd7-93f282d9b9d8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ZwCreateKey routine [Kernel-Mode Driver Architecture], wdm/ZwCreateKey, kernel.zwcreatekey, ZwCreateKey, k111_1ab9fba3-0c39-45b8-9a79-d33ad73c0642.xml, NtCreateKey, wdm/NtCreateKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlZwPassive, PowerIrpDDis, ZwRegistryCreate, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwCreateKey
-	NtCreateKey
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ZwCreateKey function
The <b>ZwCreateKey</b> routine creates a new registry key or opens an existing one.

## Syntax

````
NTSTATUS ZwCreateKey(
  _Out_      PHANDLE            KeyHandle,
  _In_       ACCESS_MASK        DesiredAccess,
  _In_       POBJECT_ATTRIBUTES ObjectAttributes,
  _Reserved_ ULONG              TitleIndex,
  _In_opt_   PUNICODE_STRING    Class,
  _In_       ULONG              CreateOptions,
  _Out_opt_  PULONG             Disposition
);
````

## Parameters

`KeyHandle`

Pointer to a HANDLE variable that receives a handle to the key.

`DesiredAccess`

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that determines the requested access to the object. In addition to the access rights that are defined for all types of objects (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>), the caller can specify one or more of the following access rights, which are specific to object directories:

<table>
<tr>
<th><i>DesiredAccess </i>flag</th>
<th>Allows caller to do this</th>
</tr>
<tr>
<td>
KEY_QUERY_VALUE

</td>
<td>
Read key values.

</td>
</tr>
<tr>
<td>
KEY_SET_VALUE

</td>
<td>
Write key values.

</td>
</tr>
<tr>
<td>
KEY_CREATE_SUB_KEY

</td>
<td>
Create subkeys for the key.

</td>
</tr>
<tr>
<td>
KEY_ENUMERATE_SUB_KEYS

</td>
<td>
Read the key's subkeys.

</td>
</tr>
<tr>
<td>
KEY_CREATE_LINK

</td>
<td>
Create a symbolic link to the key. This flag is not used by device and intermediate drivers.

</td>
</tr>
<tr>
<td>
KEY_NOTIFY

</td>
<td>
Ask to receive notification when the name, value, or attributes of the key change. For more information, see <a href="..\ntifs\nf-ntifs-zwnotifychangekey.md">ZwNotifyChangeKey</a>.

</td>
</tr>
</table>
 

The caller can also specify one of the following constants, which combines several ACCESS_MASK flags.

<table>
<tr>
<th>Constant</th>
<th>Consists of these ACCESS_MASK flags</th>
</tr>
<tr>
<td>
KEY_READ

</td>
<td>
STANDARD_RIGHTS_READ, KEY_QUERY_VALUE, KEY_ENUMERATE_SUB_KEYS, and KEY_NOTIFY

</td>
</tr>
<tr>
<td>
KEY_WRITE

</td>
<td>
STANDARD_RIGHTS_WRITE, KEY_SET_VALUE, and KEY_CREATE_SUBKEY

</td>
</tr>
<tr>
<td>
KEY_EXECUTE

</td>
<td>
Same as KEY_READ.

</td>
</tr>
<tr>
<td>
KEY_ALL_ACCESS

</td>
<td>
STANDARD_RIGHTS_ALL, KEY_QUERY_VALUE, KEY_SET_VALUE, KEY_CREATE_SUB_KEY, KEY_ENUMERATE_SUB_KEYS, KEY_NOTIFY, and KEY_CREATE_LINK

</td>
</tr>
</table>

`ObjectAttributes`

Pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>.

`TitleIndex`

Device and intermediate drivers set this parameter to zero.

`Class`

Pointer to a Unicode string that contains the key's object class. This information is used by the configuration manager.

`CreateOptions`

Specifies the options to apply when creating or opening a key, specified as a compatible combination of the following flags.

<table>
<tr>
<th><i>CreateOptions</i> flag</th>
<th>Description</th>
</tr>
<tr>
<td>
REG_OPTION_VOLATILE

</td>
<td>
Key is not preserved when the system is rebooted.

</td>
</tr>
<tr>
<td>
REG_OPTION_NON_VOLATILE

</td>
<td>
Key is preserved when the system is rebooted.

</td>
</tr>
<tr>
<td>
REG_OPTION_CREATE_LINK

</td>
<td>
The newly created key is a symbolic link. This flag is not used by device and intermediate drivers.

</td>
</tr>
<tr>
<td>
REG_OPTION_BACKUP_RESTORE

</td>
<td>
Key should be created or opened with special privileges that allow backup and restore operations. This flag is not used by device and intermediate drivers.

</td>
</tr>
</table>

`Disposition`

Pointer to a variable that receives a value indicating whether a new key was created or an existing one opened.

<table>
<tr>
<th><i>Disposition</i> value</th>
<th>Description</th>
</tr>
<tr>
<td>
REG_CREATED_NEW_KEY

</td>
<td>
A new key was created.

</td>
</tr>
<tr>
<td>
REG_OPENED_EXISTING_KEY

</td>
<td>
An existing key was opened.

</td>
</tr>
</table>


## Return Value

<b>ZwCreateKey</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.

## Remarks

<b>ZwCreateKey</b> supplies a handle that the caller can use to manipulate a registry key. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>.

Once the handle pointed to by <i>KeyHandle</i> is no longer in use, the driver must call <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> to close it.

There are two alternate ways to specify the name of the file to be created or opened with <b>ZwCreateKey</b>:

<ol>
<li>
As a fully qualified pathname, supplied in the <b>ObjectName</b> member of the input <i>ObjectAttributes</i>. The pathnames of registry keys begin with <b>\Registry</b>.

</li>
<li>
As pathname relative to another registry key, represented by the handle in the <b>RootDirectory</b> member of the input <i>ObjectAttributes</i>. 

</li>
</ol>
If the key specified by <i>ObjectAttributes</i> does not exist, the routine attempts to create the key. For this attempt to succeed, the new key must be a direct subkey of the key that is referred to by <b>RootDirectory</b>, and the key that <b>RootDirectory</b> refers to must have been opened for KEY_CREATE_SUB_KEY access.

If the specified key already exists, it is opened and its value is not affected in any way.

The security attributes specified by <i>ObjectAttributes</i> when a key is created determine whether the specified <i>DesiredAccess</i> is granted on subsequent calls to <b>ZwCreateKey</b> and <a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>.

For more information about working with registry keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtCreateKey</b>" instead of "<b>ZwCreateKey</b>".</div>
<div> </div>
The <b>NtCreateKey</b> routine in the Windows kernel is not directly accessible to kernel-mode drivers. 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlZwPassive, PowerIrpDDis, ZwRegistryCreate, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate(storport) |

## See Also

<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="..\wdm\nf-wdm-zwenumeratekey.md">ZwEnumerateKey</a>



<a href="..\wdm\nf-wdm-zwqueryvaluekey.md">ZwQueryValueKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="..\wdm\nf-wdm-zwenumeratevaluekey.md">ZwEnumerateValueKey</a>



<a href="..\wdm\nf-wdm-zwsetvaluekey.md">ZwSetValueKey</a>



<a href="..\wdm\nf-wdm-zwdeletekey.md">ZwDeleteKey</a>



<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>



<a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>



<a href="..\wdm\nf-wdm-zwflushkey.md">ZwFlushKey</a>



<a href="..\ntifs\nf-ntifs-zwnotifychangekey.md">ZwNotifyChangeKey</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwCreateKey routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>