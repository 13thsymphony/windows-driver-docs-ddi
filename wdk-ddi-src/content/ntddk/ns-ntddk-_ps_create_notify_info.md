---
UID: NS.NTDDK._PS_CREATE_NOTIFY_INFO
title: _PS_CREATE_NOTIFY_INFO
author: windows-driver-content
description: The PS_CREATE_NOTIFY_INFO structure provides information about a newly created process.
old-location: kernel\ps_create_notify_info.htm
old-project: kernel
ms.assetid: 66fade6b-b1c1-477c-bd44-2809d02271f2
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PS_CREATE_NOTIFY_INFO, PS_CREATE_NOTIFY_INFO, *PPS_CREATE_NOTIFY_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PS_CREATE_NOTIFY_INFO
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
---

# _PS_CREATE_NOTIFY_INFO structure



## -description
The <b>PS_CREATE_NOTIFY_INFO</b> structure provides information about a newly created process.


## -syntax

````
typedef struct _PS_CREATE_NOTIFY_INFO {
  SIZE_T              Size;
  union {
    ULONG  Flags;
    struct {
      ULONG FileOpenNameAvailable  :1;
      ULONG IsSubsystemProcess   :1;
      ULONG Reserved  :30;
    };
  };
  HANDLE              ParentProcessId;
  CLIENT_ID           CreatingThreadId;
  struct _FILE_OBJECT  *FileObject;
  PCUNICODE_STRING    ImageFileName;
  PCUNICODE_STRING    CommandLine;
  NTSTATUS            CreationStatus;
} PS_CREATE_NOTIFY_INFO, *PPS_CREATE_NOTIFY_INFO;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure. The operating system uses this size to indicate the type of structure that it passes to <a href="kernel.createprocessnotifyex">CreateProcessNotifyEx</a>. Currently, this member is always <b>sizeof</b>(<b>PS_CREATE_NOTIFY_INFO</b>).

### -field Flags

Reserved. Use the <b>FileOpenNameAvailable</b> member instead. 

### -field FileOpenNameAvailable

A Boolean value that specifies whether the <b>ImageFileName</b> member contains the exact file name that is used to open the process executable file.

### -field IsSubsystemProcess 

A Boolean value that indicates the type of process subsystem is a subsystem other than Win32. 
<div class="alert"><b>Note</b>  <p class="note"><b>IsSubsystemProcess</b> is only populated for subsystem processes other than Win32 when a driver has registered through <a href="kernel.pssetcreateprocessnotifyroutineex2">PsSetCreateProcessNotifyRoutineEx2</a> with a type that allows for notifications from subsystem processes.  When <b>IsSubsystemProcess</b> is set, the <b>FileObject</b>, <b>ImageFileName</b>, and <b>CommandLine</b> may be NULL.  Drivers should use <b>ProcessSubsystemInformation</b> to query the subsystem type if needed. 
For more information, see <a href="base.ntqueryinformationprocess">NtQueryInformationProcess</a>.
</div>
<div> </div>

### -field Reserved

Reserved for system use.

### -field ParentProcessId

The process ID of the parent process for the new process. Note that the parent process is not necessarily the same process as the process that created the new process. The new process can inherit certain properties of the parent process, such as handles or shared memory. (The process ID of the process creator is given by <b>CreatingThreadId</b>-&gt;<b>UniqueProcess</b>.)

### -field CreatingThreadId

The process ID and thread ID of the process and thread that created the new process. <b>CreatingThreadId</b>-&gt;<b>UniqueProcess</b> contains the process ID, and <b>CreatingThreadId</b>-&gt;<b>UniqueThread</b> contains the thread ID.

### -field FileObject

A pointer to the file object for the process executable file. 
<div class="alert"><b>Note</b>  <p class="note">If <b>IsSubsystemProcess</b> is TRUE, this value may be NULL. 
</div>
<div> </div>

### -field ImageFileName

A pointer to a <a href="kernel.unicode_string">UNICODE_STRING</a> string that holds the file name of the executable. If the <b>FileOpenNameAvailable</b> member is <b>TRUE</b>, the string specifies the exact file name that is used to open the executable file. If <b>FileOpenNameAvailable</b> is <b>FALSE</b>, the operating system might provide only a partial name.
<div class="alert"><b>Note</b>  <p class="note">If <b>IsSubsystemProcess</b> is TRUE, this value maybe NULL. 
</div>
<div> </div>

### -field CommandLine

A pointer to a <b>UNICODE_STRING</b> string that holds the command that is used to execute the process. If the command is not available, <b>CommandLine</b> is <b>NULL</b>.
<div class="alert"><b>Note</b>  <p class="note">If <b>IsSubsystemProcess</b> is TRUE, this value maybe NULL. 
</div>
<div> </div>

### -field CreationStatus

The NTSTATUS value to return for the process-creation operation. Drivers can change this value to an error code to prevent the process from being created.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating system.
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
</table>

## -see-also
<dl>
<dt>
<a href="kernel.createprocessnotifyex">CreateProcessNotifyEx</a>
</dt>
<dt>
<a href="kernel.pssetcreateprocessnotifyroutineex">PsSetCreateProcessNotifyRoutineEx</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PS_CREATE_NOTIFY_INFO structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
