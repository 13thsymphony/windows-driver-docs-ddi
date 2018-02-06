---
UID: NS:ntddk._PS_CREATE_NOTIFY_INFO
title: "_PS_CREATE_NOTIFY_INFO"
author: windows-driver-content
description: The PS_CREATE_NOTIFY_INFO structure provides information about a newly created process.
old-location: kernel\ps_create_notify_info.htm
old-project: kernel
ms.assetid: 66fade6b-b1c1-477c-bd44-2809d02271f2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/PPS_CREATE_NOTIFY_INFO, PS_CREATE_NOTIFY_INFO structure [Kernel-Mode Driver Architecture], kstruct_c_489ee208-518d-41f1-af90-a8873f3e7fb0.xml, ntddk/PS_CREATE_NOTIFY_INFO, PPS_CREATE_NOTIFY_INFO structure pointer [Kernel-Mode Driver Architecture], PPS_CREATE_NOTIFY_INFO, _PS_CREATE_NOTIFY_INFO, kernel.ps_create_notify_info, PS_CREATE_NOTIFY_INFO, *PPS_CREATE_NOTIFY_INFO
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddk.h
apiname:
-	PS_CREATE_NOTIFY_INFO
product: Windows
targetos: Windows
req.typenames: "*PPS_CREATE_NOTIFY_INFO, PS_CREATE_NOTIFY_INFO"
---

# _PS_CREATE_NOTIFY_INFO structure
The <b>PS_CREATE_NOTIFY_INFO</b> structure provides information about a newly created process.

## Syntax
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

## Members


`_FILE_OBJECT`



`CommandLine`

A pointer to a <b>UNICODE_STRING</b> string that holds the command that is used to execute the process. If the command is not available, <b>CommandLine</b> is <b>NULL</b>.
<div class="alert"><b>Note</b>  <p class="note">If <b>IsSubsystemProcess</b> is TRUE, this value maybe NULL. 

</div><div> </div>

`CreatingThreadId`

The process ID and thread ID of the process and thread that created the new process. <b>CreatingThreadId</b>-&gt;<b>UniqueProcess</b> contains the process ID, and <b>CreatingThreadId</b>-&gt;<b>UniqueThread</b> contains the thread ID.

`CreationStatus`

The NTSTATUS value to return for the process-creation operation. Drivers can change this value to an error code to prevent the process from being created.

`FileObject`

A pointer to the file object for the process executable file. 
<div class="alert"><b>Note</b>  <p class="note">If <b>IsSubsystemProcess</b> is TRUE, this value may be NULL. 

</div><div> </div>

`ImageFileName`

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> string that holds the file name of the executable. If the <b>FileOpenNameAvailable</b> member is <b>TRUE</b>, the string specifies the exact file name that is used to open the executable file. If <b>FileOpenNameAvailable</b> is <b>FALSE</b>, the operating system might provide only a partial name.
<div class="alert"><b>Note</b>  <p class="note">If <b>IsSubsystemProcess</b> is TRUE, this value maybe NULL. 

</div><div> </div>

`ParentProcessId`

The process ID of the parent process for the new process. Note that the parent process is not necessarily the same process as the process that created the new process. The new process can inherit certain properties of the parent process, such as handles or shared memory. (The process ID of the process creator is given by <b>CreatingThreadId</b>-&gt;<b>UniqueProcess</b>.)

`Size`

The size, in bytes, of this structure. The operating system uses this size to indicate the type of structure that it passes to <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff559951">CreateProcessNotifyEx</a>. Currently, this member is always <b>sizeof</b>(<b>PS_CREATE_NOTIFY_INFO</b>).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating system. Available in Windows Vista and later versions of the Windows operating system. |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\ntddk\nf-ntddk-pssetcreateprocessnotifyroutineex.md">PsSetCreateProcessNotifyRoutineEx</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff559951">CreateProcessNotifyEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PS_CREATE_NOTIFY_INFO structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>