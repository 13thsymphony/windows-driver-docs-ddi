---
UID: NF:wdm.NtOpenTransactionManager
title: NtOpenTransactionManager function
author: windows-driver-content
description: The ZwOpenTransactionManager routine obtains a handle to an existing transaction manager object.
old-location: kernel\zwopentransactionmanager.htm
old-project: kernel
ms.assetid: b3eb40ad-cda9-4a2f-a794-670bd2ee9102
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: NtOpenTransactionManager, ZwOpenTransactionManager, ZwOpenTransactionManager routine [Kernel-Mode Driver Architecture], kernel.zwopentransactionmanager, ktm_ref_26c2e5a4-0a1b-4d75-994a-88f45e213fe3.xml, wdm/NtOpenTransactionManager, wdm/ZwOpenTransactionManager
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwOpenTransactionManager
-	NtOpenTransactionManager
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# NtOpenTransactionManager function
The <b>ZwOpenTransactionManager</b> routine obtains a handle to an existing transaction manager object.

## Syntax

````
NTSTATUS ZwOpenTransactionManager(
  _Out_    PHANDLE            TmHandle,
  _In_     ACCESS_MASK        DesiredAccess,
  _In_opt_ POBJECT_ATTRIBUTES ObjectAttributes,
  _In_opt_ PUNICODE_STRING    LogFileName,
  _In_opt_ LPGUID             TmIdentity,
  _In_opt_ ULONG              OpenOptions
);
````

## Parameters

`TmHandle`

A pointer to a caller-allocated variable that receives a handle to the <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a> if <b>ZwOpenTransactionManager</b> returns STATUS_SUCCESS.

`DesiredAccess`

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that specifies the caller's requested access to the transaction manager object. For information about how to specify this parameter, see the <i>DesiredAccess</i> parameter of <a href="..\wdm\nf-wdm-zwcreatetransactionmanager.md">ZwCreateTransactionManager</a>.

`ObjectAttributes`

A pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use the <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> routine to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. This parameter is optional and can be <b>NULL</b>.

`LogFileName`

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the path and file name of the <a href="https://msdn.microsoft.com/d7ad0e16-d1f2-4c41-b647-95b5445c2708">log file stream</a> that was created when the transaction manager object was created. For more information, see the <i>LogFileName</i> parameter of <b>ZwCreateTransactionManager</b>. This parameter is optional and can be <b>NULL</b>.

`TmIdentity`

A pointer to a GUID that identifies the transaction manager object.  This parameter is optional and can be <b>NULL</b>.

`OpenOptions`

This parameter is not used and must be zero.


## Return Value

<b>ZwOpenTransactionManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The value of an input parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
KTM could not allocate system resources (typically memory).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The object name that the <i>ObjectAttributes </i>parameter specifies is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LOG_CORRUPTION_DETECTED</b></dt>
</dl>
</td>
<td width="60%">
KTM encountered an error while creating or opening the log file.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>DesiredAccess</i> parameter is invalid.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

The caller can identify which transaction manager object to open by using one of the following three techniques:

<ul>
<li>
Use the <i>LogFileName</i> parameter to specify the path and file name of a log file stream that was created when the transaction manager object was created.

</li>
<li>
Use the <i>TmIdentity</i> parameter to specify the GUID that identifies the transaction manager object. 

</li>
<li>
Use the <i>ObjectAttributes</i> parameter to supply an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that contains the object name that the caller previously specified to the <a href="..\wdm\nf-wdm-zwcreatetransactionmanager.md">ZwCreateTransactionManager</a> routine. 

</li>
</ul>
You must specify only one of the above-listed parameters (an object name, a log file name, or a GUID) and set the other two parameters to <b>NULL</b>.

Your TPS component must call <a href="..\wdm\nf-wdm-zwrecovertransactionmanager.md">ZwRecoverTransactionManager</a> after it has called <b>ZwOpenTransactionManager</b>.

A TPS component that calls <b>ZwOpenTransactionManager</b> must eventually call <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> to close the object handle.

For more information about how to use <b>ZwOpenTransactionManager</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564802">Transaction Manager Objects</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a>.

<b>NtOpenTransactionManager</b> and <b>ZwOpenTransactionManager</b> are two versions of the same Windows Native System Services routine. 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later operating system versions.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdm\nf-wdm-zwqueryinformationtransactionmanager.md">ZwQueryInformationTransactionManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="..\wdm\nf-wdm-zwcreatetransactionmanager.md">ZwCreateTransactionManager</a>



<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>



<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



<a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwOpenTransactionManager routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>