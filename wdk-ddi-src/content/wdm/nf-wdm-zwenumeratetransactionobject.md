---
UID: NF.wdm.ZwEnumerateTransactionObject
title: ZwEnumerateTransactionObject function
author: windows-driver-content
description: The ZwEnumerateTransactionObject routine enumerates the KTM objects on a computer.
old-location: kernel\zwenumeratetransactionobject.htm
old-project: kernel
ms.assetid: 49560022-a690-4259-b725-f8927af31804
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ZwEnumerateTransactionObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwEnumerateTransactionObject,NtEnumerateTransactionObject
req.alt-loc: NtosKrnl.exe
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
req.product: Windows 10 or later.
---

# ZwEnumerateTransactionObject function



## -description
The <b>ZwEnumerateTransactionObject</b> routine enumerates the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554272">KTM objects</a> on a computer.



## -syntax

````
NTSTATUS ZwEnumerateTransactionObject(
  _In_opt_ HANDLE            RootObjectHandle,
  _In_     KTMOBJECT_TYPE    QueryType,
  _Inout_  PKTMOBJECT_CURSOR ObjectCursor,
  _In_     ULONG             ObjectCursorLength,
  _Out_    PULONG            ReturnLength
);
````


## -parameters

### -param RootObjectHandle [in, optional]

A handle to a KTM object. The routine enumerates the child objects of the specified object. This parameter is optional and can be <b>NULL</b>. For more information about valid values for this parameter, see the table in the following Remarks section.


### -param QueryType [in]

A <a href="kernel.ktmobject_type">KTMOBJECT_TYPE</a>-typed value that identifies the object type to enumerate. For more information about valid values for this parameter, see the table in the following Remarks section.


### -param ObjectCursor [in, out]

A pointer to a caller-allocated buffer that begins with a <a href="kernel.ktmobject_cursor">KTMOBJECT_CURSOR</a> structure. <b>ZwEnumerateTransactionObject</b> uses the buffer to store the GUIDs of objects that it finds.


### -param ObjectCursorLength [in]

The length, in bytes, of the buffer that <i>ObjectCursor</i> points to.


### -param ReturnLength [out]

A pointer to a caller-allocated location that receives the number of bytes that <b>ZwEnumerateTransactionObject</b> returns in the <i>ObjectCursor</i> buffer, including the length of the <b>KTMOBJECT_CURSOR</b> structure and the length of all returned GUIDs.


## -returns
<b>ZwEnumerateTransactionObject</b> returns STATUS_SUCCESS if the operation succeeds but the routine has not enumerated all the objects. If there are no more objects to enumerate, the routine returns STATUS_NO_MORE_ENTRIES. Otherwise, this routine might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>QueryType</i> or <i>ObjectCursorLength</i> parameter's value is invalid.
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>The handle that the <i>RootObjectHandle</i> parameter specifies is not a handle to a valid KTM object.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>An object handle is invalid.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller does not have appropriate access to the objects that are being enumerated.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
The following table contains the valid values for the <i>RootObjectHandle</i> and <i>QueryType</i> parameters.

KTMOBJECT_TRANSACTION_MANAGER

<b>NULL</b>

All transaction manager objects

KTMOBJECT_RESOURCE_MANAGER

A handle to a transaction manager object.

The handle must have TRANSACTIONMANAGER_QUERY_INFORMATION access to the object.

All resource manager objects that belong to the specified transaction manager object

KTMOBJECT_ENLISTMENT

A handle to a resource manager object.

The handle must have RESOURCEMANAGER_QUERY_INFORMATION access to the object.

All enlistment objects that belong to the specified resource manager object

KTMOBJECT_TRANSACTION

All transaction objects that belong to the specified transaction manager object

All transaction objects that belong to all transaction manager objects

Most TPS components do not have to call <b>ZwEnumerateTransactionObject</b>, but the routine might be useful if you have to write a debugging utility.

Before your component calls <b>ZwEnumerateTransactionObject</b>, it must allocate and zero the buffer that <i>ObjectCursor</i> points to. The buffer's GUID array can be large enough to receive one or more elements. 

To enumerate all of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554272">KTM objects</a> of the specified type, your component must call <b>ZwEnumerateTransactionObject</b> repeatedly until it returns STATUS_NO_MORE_ENTRIES. 

Every time that the routine is called, it fills the buffer's GUID array with as many object GUIDs that will fit. After each call, your component can use the <a href="kernel.ktmobject_cursor">KTMOBJECT_CURSOR</a> structure's <b>ObjectIdCount</b> member to determine the number of object GUIDs that the routine stored in the array.

<b>NtEnumerateTransactionObject</b> and <b>ZwEnumerateTransactionObject</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

The following code example shows how to enumerate all of the transaction objects on a computer. In this example, the <b>KTMOBJECT_CURSOR</b> structure's GUID array contains only one element, so each call to <b>ZwEnumerateTransactionObject</b> returns one GUID. The routine creates a Unicode string from the GUID and displays the string.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later operating system versions.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.ktmobject_cursor">KTMOBJECT_CURSOR</a>
</dt>
<dt>
<a href="kernel.ktmobject_type">KTMOBJECT_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwEnumerateTransactionObject routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

