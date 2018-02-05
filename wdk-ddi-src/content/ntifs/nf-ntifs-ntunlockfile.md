---
UID : NF:ntifs.NtUnlockFile
title : NtUnlockFile function
author : windows-driver-content
description : The ZwUnlockFile routine unlocks a byte-range lock in a file.
old-location : kernel\zwunlockfile.htm
old-project : kernel
ms.assetid : dca3023b-99d5-471a-a5a2-8453c367ce9b
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ZwUnlockFile routine [Kernel-Mode Driver Architecture], ntifs/NtUnlockFile, k111_a77fe0ba-5252-4441-aaad-67d2bbae01cb.xml, ZwUnlockFile, ntifs/ZwUnlockFile, kernel.zwunlockfile, NtUnlockFile
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h, FltKernel.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 7.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL (see Remarks section)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# NtUnlockFile function
The <b>ZwUnlockFile</b> routine unlocks a byte-range lock in a file.

## Syntax

````
NTSTATUS ZwUnlockFile(
  _In_  HANDLE           FileHandle,
  _Out_ PIO_STATUS_BLOCK IoStatusBlock,
  _In_  PLARGE_INTEGER   ByteOffset,
  _In_  PLARGE_INTEGER   Length,
  _In_  ULONG            Key
);
````

## Parameters

`FileHandle`

A handle for the file object that represents the file whose byte range is to be unlocked.

`IoStatusBlock`

A pointer to an <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure that contains the final status.

`ByteOffset`

A pointer to a variable that specifies the starting byte offset for the byte range to be unlocked.

`Length`

A pointer to a variable that specifies the length, in bytes, of the byte range to unlock.

`Key`

The caller-assigned value used to describe groups of related locks. This value should be set to zero.


## Return Value

The <b>ZwUnlockFile</b> routine returns STATUS_SUCCESS on success or an appropriate NTSTATUS value. Possible NTSTATUS values include:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RANGE_NOT_LOCKED</b></dt>
</dl>
</td>
<td width="60%">
The byte range specified is not locked.

</td>
</tr>
</table>

## Remarks

The <b>ZwUnlockFile</b> routine takes a range of bytes as specified by the <i>ByteOffset</i> and <i>Length</i> arguments. This range must be identical to a range of bytes in the file that was previously locked with a single call to the <b>ZwUnlockFile</b> routine. It is not possible to unlock two previously locked adjacent ranges with a single call to <b>ZwUnlockFile</b>. It is also not possible to unlock part of a range that was previously locked with a single call to the <b>ZwUnlockFile</b> routine.

Callers of <b>ZwUnlockFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.
<div class="alert"><b>Note</b>  If the call to the <b>ZwUnlockFile</b> function occurs in user mode, you should use the name "<a href="https://msdn.microsoft.com/library/windows/hardware/ff557707">NtUnlockFile</a>" instead of "<b>ZwUnlockFile</b>".</div><div> </div>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 7. Available starting with Windows 7. |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h, FltKernel.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL (see Remarks section) |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>

<a href="..\ntifs\nf-ntifs-zwlockfile.md">ZwLockFile</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwUnlockFile routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>