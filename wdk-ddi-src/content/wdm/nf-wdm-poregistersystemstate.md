---
UID: NF.wdm.PoRegisterSystemState
title: PoRegisterSystemState function
author: windows-driver-content
description: The PoRegisterSystemState routine registers the system as busy due to certain activity.
old-location: kernel\poregistersystemstate.htm
old-project: kernel
ms.assetid: 851c694f-6c47-498c-8035-132a63c0fa62
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: PoRegisterSystemState
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
req.alt-api: PoRegisterSystemState
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
req.irql: <=APC_LEVEL
req.product: Windows 10 or later.
---

# PoRegisterSystemState function



## -description
The <b>PoRegisterSystemState</b> routine registers the system as busy due to certain activity.



## -syntax

````
PVOID PoRegisterSystemState(
  _Inout_ PVOID           StateHandle,
  _In_    EXECUTION_STATE Flags
);
````


## -parameters

### -param StateHandle [in, out]

A pointer to a caller-supplied buffer for a registration state handle. The size, in bytes, of the buffer is <b>sizeof</b>(ULONG). If <b>NULL</b>, this is a new registration. If non-<b>NULL</b>, this parameter points to a handle that was returned by a previous call to <b>PoRegisterSystemState</b>.


### -param Flags [in]

Indicates the type of activity, as specified by a bitwise OR of one or more of the following values:




### -param ES_SYSTEM_REQUIRED

The system is not idle, regardless of apparent load.


### -param ES_DISPLAY_REQUIRED

Use of the display is required.


### -param ES_USER_PRESENT

A user is present.


### -param ES_CONTINUOUS

The settings are continuous and should remain in effect until explicitly changed.

</dd>
</dl>

## -returns
<b>PoRegisterSystemState</b> returns a handle to be used later to change or unregister the system busy state. It returns <b>NULL</b> if the handle could not be allocated.


## -remarks
<b>PoRegisterSystemState</b> registers the system busy state as indicated by the flags. The registration persists until the caller explicitly changes it with another call to <b>PoRegisterSystemState</b> or cancels it with a call to <a href="kernel.pounregistersystemstate">PoUnregisterSystemState</a>.

The <i>Flags</i> parameter specifies the type of activity in progress. Drivers can specify any combination of the flags.

Setting ES_CONTINUOUS makes the busy state persist until a driver explicitly changes or cancels it by calling <b>PoRegisterSystemState</b> or <b>PoUnregisterSystemState</b>.

A driver can set the system busy state to request that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a> avoid system power state transitions out of the system working state (S0) while driver activity is occurring. Note, however, that under some circumstances (such as a critically low battery) the power manager may override this request and put the system to sleep anyway.

To set the system power state, call <a href="kernel.posetsystemstate">PoSetSystemState</a>.


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
Available starting with Windows 2000.

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
&lt;=APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.posetsystemstate">PoSetSystemState</a>
</dt>
<dt>
<a href="kernel.pounregistersystemstate">PoUnregisterSystemState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoRegisterSystemState routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

