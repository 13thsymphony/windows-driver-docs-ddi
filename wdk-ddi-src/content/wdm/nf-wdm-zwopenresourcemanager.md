---
UID: NF:wdm.ZwOpenResourceManager
title: ZwOpenResourceManager function
author: windows-driver-content
description: The ZwOpenResourceManager routine returns a handle to an existing resource manager object.
old-location: kernel\zwopenresourcemanager.htm
old-project: kernel
ms.assetid: baa12e3c-dc17-4fef-bce4-29c50328314c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: NtOpenResourceManager, ZwOpenResourceManager, ZwOpenResourceManager routine [Kernel-Mode Driver Architecture], kernel.zwopenresourcemanager, ktm_ref_f873ba66-20d0-4498-a8b6-d62bf8593d05.xml, wdm/NtOpenResourceManager, wdm/ZwOpenResourceManager
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
-	ZwOpenResourceManager
-	NtOpenResourceManager
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ZwOpenResourceManager function
The <b>ZwOpenResourceManager</b> routine returns a handle to an existing <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a>.

## Syntax

````
NTSTATUS ZwOpenResourceManager(
  _Out_    PHANDLE            ResourceManagerHandle,
  _In_     ACCESS_MASK        DesiredAccess,
  _In_     HANDLE             TmHandle,
  _In_     LPGUID             ResourceManagerGuid,
  _In_opt_ POBJECT_ATTRIBUTES ObjectAttributes
);
````

## Parameters

`ResourceManagerHandle`

A pointer to a caller-allocated variable that receives the resource manager handle if the call to <b>ZwOpenResourceManager</b> succeeds.

`DesiredAccess`

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that specifies the caller's requested access to the resource manager object. For more information about how to specify this parameter, see the <i>DesiredAccess</i> parameter of <a href="..\wdm\nf-wdm-zwcreateresourcemanager.md">ZwCreateResourceManager</a>. This parameter cannot be zero.

`TmHandle`

A handle to a transaction manager object that was obtained by a previous call to <a href="..\wdm\nf-wdm-zwcreatetransactionmanager.md">ZwCreateTransactionManager</a> or <a href="..\wdm\nf-wdm-zwopentransactionmanager.md">ZwOpenTransactionManager</a>.

`ResourceManagerGuid`

A pointer to the GUID that identifies the resource manager to open.

`ObjectAttributes`

A pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies the object's attributes. Use the <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> routine to initialize this structure, but specify only that routine's <i>InitializedAttributes</i> and <i>Attributes</i> parameters. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE flag in the <i>Attributes</i> parameter. This parameter is optional and can be <b>NULL</b>.


## Return Value

<b>ZwOpenResourceManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The handle that <i>TmHandle</i> specifies is not a handle to a transaction object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The handle that <i>TmHandle</i> specifies is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have appropriate access to the specified transaction manager object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>DesiredAccess</i> parameter is zero or the <i>ResourceManagerGuid</i> parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RESOURCEMANAGER_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The specified resource manager could not be found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTIONMANAGER_NOT_ONLINE</b></dt>
</dl>
</td>
<td width="60%">
The specified transaction manager is not online.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

Typically, a TPS component calls <b>ZwOpenResourceManager</b> after it receives an enlistment GUID from another TPS component that had previously called <a href="..\wdm\nf-wdm-zwcreateresourcemanager.md">ZwCreateResourceManager</a>. Most TPS designs do not require calling <b>ZwOpenResourceManager</b>.

A resource manager that calls <b>ZwOpenResourceManager</b> must eventually call <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> to close the object handle.

For more information about <b>ZwOpenResourceManager</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554272">KTM Objects</a>.

<b>NtOpenResourceManager</b> and <b>ZwOpenResourceManager</b> are two versions of the same Windows Native System Services routine.

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

<a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a>



<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="..\wdm\nf-wdm-zwopentransactionmanager.md">ZwOpenTransactionManager</a>



<a href="..\wdm\nf-wdm-zwcreatetransactionmanager.md">ZwCreateTransactionManager</a>



<a href="..\wdm\nf-wdm-zwcreateresourcemanager.md">ZwCreateResourceManager</a>



<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwOpenResourceManager routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>