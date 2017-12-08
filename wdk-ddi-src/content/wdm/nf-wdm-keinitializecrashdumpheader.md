---
UID: NF.wdm.KeInitializeCrashDumpHeader
title: KeInitializeCrashDumpHeader function
author: windows-driver-content
description: The KeInitializeCrashDumpHeader routine supplies the header information the system requires for a crash dump file.
old-location: kernel\keinitializecrashdumpheader.htm
old-project: kernel
ms.assetid: 6fa0cf86-35f4-4e5d-bced-ebd2ec499b64
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KeInitializeCrashDumpHeader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Server 2003 with SP1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeInitializeCrashDumpHeader
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
req.irql: Any level
req.product: Windows 10 or later.
---

# KeInitializeCrashDumpHeader function



## -description
The <b>KeInitializeCrashDumpHeader</b> routine supplies the header information the system requires for a crash dump file.


## -syntax

````
NTSTATUS KeInitializeCrashDumpHeader(
  _In_      ULONG  DumpType,
  _In_      ULONG  Flags,
  _Out_     PVOID  Buffer,
  _In_      ULONG  BufferSize,
  _Out_opt_ PULONG BufferNeeded
);
````


## -parameters

### -param DumpType [in]

Specifies the type of dump file. The only valid value is DUMP_TYPE_FULL.

### -param Flags [in]

Specifies flags for the dump file. The only valid value is 0.

### -param Buffer [out]

Pointer to the buffer that receives the header information.

### -param BufferSize [in]

Specifies the size in bytes of the buffer pointed to by <i>Buffer</i>.

### -param BufferNeeded [out, optional]

Optionally, a pointer to a variable that receives the size necessary to hold the complete header information.

## -returns
<b>KeInitializeCrashDumpHeader</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.   

## -remarks
Drivers can use this routine to manually create a crash dump file. The file can be created at any time, and used by a debugger to examine the state of the system.

To create a crash-dump file, call <b>KeInitializeCrashDumpHeader</b> to create the header, then append the contents of memory to the header. Note that the driver is not required to record the contents of memory immediately after calling the routine: the header can normally be created at any time before the crash-dump file is written.

Because the routine is designed to be called well before the memory contents are recorded, it has the following limitations:

The routine does not record any information about active exception records.

If the size of system RAM changes, the header must be recreated.

The routine does not record any secondary dump data.

Starting with Windows 8, <b>KeInitializeCrashDumpHeader</b> always writes the base address of the system process page directory to the crash-dump header, regardless of the process context from which <b>KeInitializeCrashDumpHeader</b> is called. The debugger can use this directory to access the crash-dump file in the context of the system process.

In earlier versions of Windows, <b>KeInitializeCrashDumpHeader</b> writes the base address of the page directory of the caller's current process context to the crash-dump header. Thus, <b>KeInitializeCrashDumpHeader</b> must be called from the system process. Otherwise, the debugger will be unable to access the crash-dump file in the process context in which the file was saved.

Starting with Windows 8, <b>KeInitializeCrashDumpHeader</b> is declared in the Wdm.h header file in the Windows Driver Kit (WDK). To use this routine with earlier versions of the WDK, include the following function declaration in your driver code:

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
Available starting with Windows Server 2003 with SP1.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
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
Any level
</td>
</tr>
</table>