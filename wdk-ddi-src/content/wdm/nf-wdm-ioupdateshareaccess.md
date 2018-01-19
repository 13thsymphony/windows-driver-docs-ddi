---
UID : NF:wdm.IoUpdateShareAccess
title : IoUpdateShareAccess function
author : windows-driver-content
description : The IoUpdateShareAccess routine updates the share access for the given file object, usually when the file is being opened.
old-location : kernel\ioupdateshareaccess.htm
old-project : kernel
ms.assetid : b8e14607-a8d4-4e15-8b1d-92096879ea65
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : IoUpdateShareAccess
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IoUpdateShareAccess
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
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


# IoUpdateShareAccess function
The <b>IoUpdateShareAccess</b> routine updates the share access for the given file object, usually when the file is being opened.

## Syntax

````
VOID IoUpdateShareAccess(
  _In_    PFILE_OBJECT  FileObject,
  _Inout_ PSHARE_ACCESS ShareAccess
);
````

## Parameters

`FileObject`

Pointer to a referenced file object representing the file or associated device object for which to update the share access.

`ShareAccess`

Pointer to the common <b>SHARE_ACCESS</b> structure associated with the <i>FileObject</i>. Drivers should treat this structure as opaque.


## Return Value

None

## Remarks

<b>IoUpdateShareAccess</b> is not an atomic operation. Therefore, drivers calling this routine must protect the shared file object passed to <b>IoUpdateShareAccess </b>by means of some kind of lock, such as a mutex or a resource lock, in order to prevent corruption of the shared access counts.

Before calling <b>IoUpdateShareAccess</b>, the caller must successfully call <b>IoCheckShareAccess</b> with <i>Update</i> set to False. Such a call to <b>IoCheckShareAccess</b> determines whether the requested shared access is compatible with the way the file object is currently being accessed by other opens, but it does not update the <b>SHARE_ACCESS</b> structure. <b>IoUpdateShareAccess</b> actually updates the <b>SHARE_ACCESS</b> structure associated with the file object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-iocheckshareaccess.md">IoCheckShareAccess</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioremoveshareaccess.md">IoRemoveShareAccess</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iosetshareaccess.md">IoSetShareAccess</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoUpdateShareAccess routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>