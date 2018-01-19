---
UID : NF:wdm.ZwSetValueKey
title : ZwSetValueKey function
author : windows-driver-content
description : The ZwSetValueKey routine creates or replaces a registry key's value entry.
old-location : kernel\zwsetvaluekey.htm
old-project : kernel
ms.assetid : 5e0bcf87-5776-4465-849c-6d4c06832797
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ZwSetValueKey
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : ZwSetValueKey,NtSetValueKey
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : IrqlZwPassive, PowerIrpDDis, ZwRegistryCreate, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate(storport), ZwRegistryOpen(storport)
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# ZwSetValueKey function
The <b>ZwSetValueKey</b> routine creates or replaces a registry key's value entry.

## Syntax

````
NTSTATUS ZwSetValueKey(
  _In_     HANDLE          KeyHandle,
  _In_     PUNICODE_STRING ValueName,
  _In_opt_ ULONG           TitleIndex,
  _In_     ULONG           Type,
  _In_opt_ PVOID           Data,
  _In_     ULONG           DataSize
);
````

## Parameters

`KeyHandle`

Handle to the registry key to write a value entry for. This handle is created by a successful call to <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a> or <a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>.

`ValueName`

Pointer to the name of the value entry for which the data is to be written. This parameter can be a <b>NULL</b> pointer if the value entry has no name. If a name string is specified and the given name is not unique relative to its containing key, the data for an existing value entry is replaced.

`TitleIndex`

This parameter is reserved. Device and intermediate drivers should set this parameter to zero.

`Type`

One of the following system-defined types of data to write.

<table>
<tr>
<th><i>Type</i> Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
REG_BINARY

</td>
<td>
Binary data in any form.

</td>
</tr>
<tr>
<td>
REG_DWORD

</td>
<td>
A 4-byte numerical value.

</td>
</tr>
<tr>
<td>
REG_DWORD_LITTLE_ENDIAN

</td>
<td>
A 4-byte numerical value with the least significant byte at the lowest address. Identical to REG_DWORD.

</td>
</tr>
<tr>
<td>
REG_DWORD_BIG_ENDIAN

</td>
<td>
A 4-byte numerical  value with the least significant byte at the highest address.

</td>
</tr>
<tr>
<td>
REG_EXPAND_SZ

</td>
<td>
A null-terminated Unicode string that contains unexpanded references to environment variables, such as "%PATH%".

</td>
</tr>
<tr>
<td>
REG_LINK

</td>
<td>
A Unicode string that names a symbolic link. This type is irrelevant to device and intermediate drivers.

</td>
</tr>
<tr>
<td>
REG_MULTI_SZ

</td>
<td>
An array of null-terminated strings, terminated by another zero.

</td>
</tr>
<tr>
<td>
REG_NONE

</td>
<td>
Data with no particular type.

</td>
</tr>
<tr>
<td>
REG_SZ

</td>
<td>
A null-terminated Unicode string.

</td>
</tr>
<tr>
<td>
REG_RESOURCE_LIST

</td>
<td>
A device driver's list of hardware resources, used by the driver or one of the physical devices it controls, in the <b>\ResourceMap</b> tree

</td>
</tr>
<tr>
<td>
REG_RESOURCE_REQUIREMENTS_LIST

</td>
<td>
A device driver's list of possible hardware resources it or one of the physical devices it controls can use, from which the system writes a subset into the <b>\ResourceMap</b> tree

</td>
</tr>
<tr>
<td>
REG_FULL_RESOURCE_DESCRIPTOR

</td>
<td>
A list of hardware resources that a physical device is using, detected and written into the <b>\HardwareDescription</b> tree by the system

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>   Device drivers should not attempt to call <b>ZwSetValueKey</b> to explicitly write value entries in a subkey of the <b>\Registry...\ResourceMap</b> key. Only the system can write value entries to the <b>\Registry...\HardwareDescription</b> tree.</div>
<div> </div>

`Data`

Pointer to a caller-allocated buffer that contains the data for the value entry.

`DataSize`

Specifies the size, in bytes, of the <i>Data</i> buffer. If <i>Type</i> is REG_<i>XXX</i>_SZ, this value must include space for any terminating zeros.


## Return Value

<b>ZwSetValueKey</b> returns an NTSTATUS value. Possible return values include:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>

## Remarks

The<i> KeyHandle</i> passed to <b>ZwSetValueKey</b> must have been opened with the KEY_SET_VALUE <i>DesiredAccess</i> flag set for this call to succeed. For a description of possible values for <i>DesiredAccess</i>, see <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>.

If the given key has no existing value entry with a name matching the given <i>ValueName</i>, <b>ZwSetValueKey</b> creates a new value entry with the given name. If a matching value entry name exists, this routine overwrites the original value entry for the given <i>ValueName</i>. Thus, <b>ZwSetValueKey</b> preserves a unique name for each value entry of any particular key. While each value entry name must be unique to its containing key, many different keys in the registry can have value entries with the same names.

For more information about working with registry keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlZwPassive, PowerIrpDDis, ZwRegistryCreate, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate(storport), ZwRegistryOpen(storport) |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546580">HalAssignSlotResources</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548285">IoAssignResources</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549453">IoQueryDeviceDescription</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549616">IoReportResourceUsage</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwflushkey.md">ZwFlushKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwSetValueKey routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>