---
UID : NF:wdm.NtRecoverResourceManager
title : NtRecoverResourceManager function
author : windows-driver-content
description : The ZwRecoverResourceManager routine tries to recover the transaction that is associated with each enlistment of a specified resource manager object.
old-location : kernel\zwrecoverresourcemanager.htm
old-project : kernel
ms.assetid : 976ea17c-db43-487d-a378-3d65d12ddc98
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : NtRecoverResourceManager
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later operating system versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : ZwRecoverResourceManager,NtRecoverResourceManager
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
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


# NtRecoverResourceManager function
The <b>ZwRecoverResourceManager</b> routine tries to recover the transaction that is associated with each enlistment of a specified <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a>.

## Syntax

````
NTSTATUS ZwRecoverResourceManager(
  _In_ HANDLE ResourceManagerHandle
);
````

## Parameters

`ResourceManagerHandle`

A handle to a resource manager object that was obtained by a previous call to <a href="..\wdm\nf-wdm-zwcreateresourcemanager.md">ZwCreateResourceManager</a> or <a href="..\wdm\nf-wdm-zwopenresourcemanager.md">ZwOpenResourceManager</a>. The handle must have RESOURCEMANAGER_RECOVER access to the object.


## Return Value

<b>ZwRecoverResourceManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>The specified handle is not a handle to a resource manager object.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>An object handle is invalid.
<dl>
<dt><b>STATUS_TRANSACTIONMANAGER_NOT_ONLINE</b></dt>
</dl>The transaction manager that is associated with the specified resource manager is not available.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller does not have appropriate access to the resource manager object.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

When a resource manager calls <b>ZwRecoverResourceManager</b>, KTM sends a TRANSACTION_NOTIFY_RECOVER notification to the resource manager for each of the resource manager's enlistments. (If the enlistment is a superior enlistment, KTM sends TRANSACTION_NOTIFY_RECOVER_QUERY instead of TRANSACTION_NOTIFY_RECOVER.)

The final notification that KTM sends to the resource manager is TRANSACTION_NOTIFY_LAST_RECOVER.

For more information about <b>ZwRecoverResourceManager</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546922">Handling Recovery Operations</a>.

<b>NtRecoverResourceManager</b> and <b>ZwRecoverResourceManager</b> are two versions of the same Windows Native System Services routine. 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-tmrecoverresourcemanager.md">TmRecoverResourceManager</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreateresourcemanager.md">ZwCreateResourceManager</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenresourcemanager.md">ZwOpenResourceManager</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwqueryinformationresourcemanager.md">ZwQueryInformationResourceManager</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwsetinformationresourcemanager.md">ZwSetInformationResourceManager</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwRecoverResourceManager routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>