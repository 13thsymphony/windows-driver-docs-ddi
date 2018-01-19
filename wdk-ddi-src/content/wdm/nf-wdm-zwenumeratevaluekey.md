---
UID : NF:wdm.ZwEnumerateValueKey
title : ZwEnumerateValueKey function
author : windows-driver-content
description : The ZwEnumerateValueKey routine gets information about the value entries of an open key.
old-location : kernel\zwenumeratevaluekey.htm
old-project : kernel
ms.assetid : 4e94c9cc-eaa9-4de1-8f17-d24a5ed19507
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ZwEnumerateValueKey
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
req.alt-api : ZwEnumerateValueKey,NtEnumerateValueKey
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


# ZwEnumerateValueKey function
The <b>ZwEnumerateValueKey</b> routine gets information about the value entries of an open key.

## Syntax

````
NTSTATUS ZwEnumerateValueKey(
  _In_      HANDLE                      KeyHandle,
  _In_      ULONG                       Index,
  _In_      KEY_VALUE_INFORMATION_CLASS KeyValueInformationClass,
  _Out_opt_ PVOID                       KeyValueInformation,
  _In_      ULONG                       Length,
  _Out_     PULONG                      ResultLength
);
````

## Parameters

`KeyHandle`

Handle to the registry key that you want to enumerate value entries for. A successful call to <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a> or <a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a> creates this handle.

`Index`

The zero-based index of the subkey that you want value information for.

`KeyValueInformationClass`

Specifies a <a href="..\wdm\ne-wdm-_key_value_information_class.md">KEY_VALUE_INFORMATION_CLASS</a> value that determines the type of information returned in the <i>KeyValueInformation</i> buffer.

`KeyValueInformation`

Pointer to a caller-allocated buffer that receives the requested information.

`Length`

Specifies the size, in bytes, of the <i>KeyValueInformation</i> buffer.

`ResultLength`

Pointer to a variable that receives the size, in bytes, of the value information. If this routine returns STATUS_SUCCESS, the variable indicates the amount of data returned. If this routine returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL, the variable indicates the buffer size that is required to hold the value information.


## Return Value

<b>ZwEnumerateValueKey</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure. Possible error code values include:
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>The buffer supplied is too small, and only partial data has been written to the buffer. *<i>ResultLength</i> is set to the minimum size required to hold the requested information. 
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The buffer supplied is too small, and no data has been written to the buffer. *<i>ResultLength</i> is set to the minimum size required to hold the requested information. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>KeyInformationClass</i> parameter is not a valid KEY_VALUE_INFORMATION_CLASS value. 
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>The <i>Index</i> value is out of range for the registry key specified by <i>KeyHandle</i>. For example, if a key has <i>n</i> subkeys, then for any value greater than <i>n</i>-1 the routine returns STATUS_NO_MORE_ENTRIES.

## Remarks

The<i> KeyHandle</i> passed to <b>ZwEnumerateValueKey</b> must have been opened with KEY_QUERY_VALUE access. This is accomplished by passing KEY_QUERY_VALUE, KEY_READ, or KEY_ALL_ACCESS as the <i>DesiredAccess</i> parameter to <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a> or <a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>.

The <i>Index</i> is simply a way to select among subkeys with value entries. Two calls to <b>ZwEnumerateValueKey</b> with the same <i>Index</i> are not guaranteed to return the same results.

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
<a href="..\wdm\ns-wdm-_key_value_basic_information.md">KEY_VALUE_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_key_value_full_information.md">KEY_VALUE_FULL_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_key_value_partial_information.md">KEY_VALUE_PARTIAL_INFORMATION</a>
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
<a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwqueryvaluekey.md">ZwQueryValueKey</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwEnumerateValueKey routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>