---
UID: NC:ntddk.PCREATE_PROCESS_NOTIFY_ROUTINE
title: PCREATE_PROCESS_NOTIFY_ROUTINE
author: windows-driver-content
description: Process-creation callback implemented by a driver to track the system-wide creation and deletion of processes against the driver's internal state.
old-location: kernel\pcreate_process_notify_routine.htm
old-project: kernel
ms.assetid: 2C5B3C90-04A9-48CF-9162-0E069A483C5F
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _FILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SetCreateProcessNotifyRoutine
req.alt-loc: Ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA
---

# PCREATE_PROCESS_NOTIFY_ROUTINE callback



## -description
Process-creation callback implemented by a driver  to track the system-wide creation and deletion of processes against the driver's internal state.



## -prototype

````
PCREATE_PROCESS_NOTIFY_ROUTINE SetCreateProcessNotifyRoutine;

void SetCreateProcessNotifyRoutine(
  _In_ HANDLE  ParentId,
  _In_ HANDLE  ProcessId,
  _In_ BOOLEAN Create
)
{ ... }
````


## -parameters

### -param ParentId [in]

The process ID of the parent process.


### -param ProcessId [in]

The process ID of the process.


### -param Create [in]

Indicates whether the process was created (<b>TRUE</b>) or deleted (<b>FALSE</b>).


## -returns
This callback function does not return a value.


## -remarks
Highest-level drivers call <b>PsSetCreateProcessNotifyRoutine</b> to register their process-creation notify routines.

A driver's process-notify routine is also called with <i>Create</i> set to <b>FALSE</b>, typically when the last thread within a process has terminated and the process address space is about to be deleted.

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
Available starting with Windows 2000.

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
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt><b>PsSetCreateProcessNotifyRoutine</b></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCREATE_PROCESS_NOTIFY_ROUTINE callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

