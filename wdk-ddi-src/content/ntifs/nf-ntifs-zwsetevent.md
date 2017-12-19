---
UID: NF.ntifs.ZwSetEvent
title: ZwSetEvent function
author: windows-driver-content
description: The ZwSetEvent routine sets an event object to a Signaled state and attempts to satisfy as many waits as possible.
old-location: kernel\zwsetevent.htm
old-project: kernel
ms.assetid: f561fc3e-2233-4237-a88d-bd5a887a1e7a
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ZwSetEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwSetEvent,NtSetEvent
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
---

# ZwSetEvent function



## -description
The <b>ZwSetEvent</b> routine sets an event object to a Signaled state and attempts to satisfy as many waits as possible.



## -syntax

````
NTSTATUS ZwSetEvent(
  _In_      HANDLE EventHandle,
  _Out_opt_ PLONG  PreviousState
);
````


## -parameters

### -param EventHandle [in]

A handle to an event object.


### -param PreviousState [out, optional]

An optional pointer to a variable where the previous state of the event object is stored on output. 


## -returns
<b>ZwSetEvent</b> returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following: 
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller did not have the required privileges to modify the event specified by the <i>EventHandle</i> parameter. 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Resources required by this function could not be allocated. 
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>The supplied <i>EventHandle</i> parameter was invalid. 

 


## -remarks
<b>ZwSetEvent</b> sets an event object to a Signaled state and attempts to satisfy as many waits as possible.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


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
Available in Windows XP and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="kernel.iocreatenotificationevent">IoCreateNotificationEvent</a>
</dt>
<dt>
<a href="kernel.iocreatesynchronizationevent">IoCreateSynchronizationEvent</a>
</dt>
<dt>
<a href="kernel.keclearevent">KeClearEvent</a>
</dt>
<dt>
<a href="kernel.keresetevent">KeResetEvent</a>
</dt>
<dt>
<a href="kernel.kesetevent">KeSetEvent</a>
</dt>
<dt>
<a href="kernel.kewaitforsingleobject">KeWaitForSingleObject</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="kernel.zwclose">ZwClose</a>
</dt>
<dt>
<a href="kernel.zwcreateevent">ZwCreateEvent</a>
</dt>
<dt>
<a href="kernel.zwwaitforsingleobject">ZwWaitForSingleObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwSetEvent routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

