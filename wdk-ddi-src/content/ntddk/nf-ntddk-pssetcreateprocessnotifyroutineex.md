---
UID: NF:ntddk.PsSetCreateProcessNotifyRoutineEx
title: PsSetCreateProcessNotifyRoutineEx function
author: windows-driver-content
description: The PsSetCreateProcessNotifyRoutineEx routine registers or removes a callback routine that notifies the caller when a process is created or exits.
old-location: kernel\pssetcreateprocessnotifyroutineex.htm
old-project: kernel
ms.assetid: e982200c-f30c-423e-bd85-03365850c996
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PsSetCreateProcessNotifyRoutineEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista with SP1 and Windows Server 2008.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PsSetCreateProcessNotifyRoutineEx
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
req.typenames: *PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT
---

# PsSetCreateProcessNotifyRoutineEx function



## -description
The <b>PsSetCreateProcessNotifyRoutineEx</b> routine registers or removes a callback routine that notifies the caller when a process is created or exits.



## -syntax

````
NTSTATUS PsSetCreateProcessNotifyRoutineEx(
  _In_ PCREATE_PROCESS_NOTIFY_ROUTINE_EX NotifyRoutine,
  _In_ BOOLEAN                           Remove
);
````


## -parameters

### -param NotifyRoutine [in]

A pointer to the <a href="..\ntddk\nc-ntddk-pcreate_process_notify_routine_ex.md">PCREATE_PROCESS_NOTIFY_ROUTINE_EX</a> routine to register or remove. The operating system calls this routine whenever a new process is created.


### -param Remove [in]

A Boolean value that specifies whether <b>PsSetCreateProcessNotifyRoutineEx</b> will add or remove a specified routine from the list of callback routines. If this parameter is <b>TRUE</b>, the specified routine is removed from the list of callback routines. If this parameter is <b>FALSE</b>, the specified routine is added to the list of callback routines. If <i>Remove</i> is <b>TRUE</b>, the system also waits for all in-flight callback routines to complete before returning.


## -returns
<b>PsSetCreateProcessNotifyRoutineEx</b> returns one of the following NTSTATUS values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The specified routine is now registered with the operating system. The operating system calls this routine whenever a new process is created.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The specified routine was already registered, or the operating system has reached its limit for registering process-creation callback routines.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The image that contains the callback routine pointer did not have IMAGE_DLLCHARACTERISTICS_FORCE_INTEGRITY set in its image header.

 


## -remarks
Highest-level drivers can call <b>PsSetCreateProcessNotifyRoutineEx</b> to register a <a href="..\ntddk\nc-ntddk-pcreate_process_notify_routine_ex.md">PCREATE_PROCESS_NOTIFY_ROUTINE_EX</a> routine. An installable file system (IFS) or highest-level system-profiling driver might register a process-creation callback routine to track which processes are created and deleted against the driver's internal state across the system. 

A driver must remove any callback routines that it registers before it unloads. You can remove the callback routine by calling <b>PsSetCreateProcessNotifyRoutineEx</b> with <i>Remove</i> set to <b>TRUE</b>.

The operating system calls the driver's process-notify routine at PASSIVE_LEVEL inside a critical region with <a href="https://msdn.microsoft.com/74ed953c-1b2a-40b9-9df3-16869b198b38">normal kernel APCs</a> disabled. When a process is created, the process-notify routine runs in the context of the thread that created the new process. When a process is deleted, the process-notify routine runs in the context of the last thread to exit from the process.


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
Available starting with Windows Vista with SP1 and Windows Server 2008.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975204">PowerIrpDDis</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nc-ntddk-pcreate_process_notify_routine_ex.md">PCREATE_PROCESS_NOTIFY_ROUTINE_EX</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_ps_create_notify_info.md">PS_CREATE_NOTIFY_INFO</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-pssetcreateprocessnotifyroutine.md">PsSetCreateProcessNotifyRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsSetCreateProcessNotifyRoutineEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

