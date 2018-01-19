---
UID : NF:wdm.IoCheckShareAccessEx
title : IoCheckShareAccessEx function
author : windows-driver-content
description : The IoCheckShareAccessEx routine is called by file system drivers (FSDs) or other highest-level drivers to check whether shared access to a file object is permitted.
old-location : kernel\iocheckshareaccessex.htm
old-project : kernel
ms.assetid : E6CDE415-FCC2-4039-B6DD-168113D9A490
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : IoCheckShareAccessEx
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : 
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 7 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IoCheckShareAccessEx
req.alt-loc : ntoskrnl.lib,ntoskrnl.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ntoskrnl.lib
req.dll : 
req.irql : 
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# IoCheckShareAccessEx function
The <b>IoCheckShareAccessEx</b> routine is called by file system drivers (FSDs) or other highest-level drivers to check whether shared access to a file object is permitted.

## Syntax

````
NTSTATUS IoCheckShareAccessEx(
  _In_    ACCESS_MASK   DesiredAccess,
  _In_    ULONG         DesiredShareAccess,
  _Inout_ PFILE_OBJECT  FileObject,
  _Inout_ PSHARE_ACCESS ShareAccess,
  _In_    BOOLEAN       Update,
  _In_    PBOOLEAN      WritePermission
);
````

## Parameters

`DesiredAccess`

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that indicates the desired type of access to the given file object.

`DesiredShareAccess`

Specifies the desired type of shared access to the file object for the current open request. The value of this parameter is usually the same as the <i>ShareAccess</i> parameter that is passed to the file system or highest-level driver by the I/O manager when the open request was made. This value can be zero, or any combination of the following:

<dl>
<dd>
FILE_SHARE_READ

</dd>
<dd>
FILE_SHARE_WRITE

</dd>
<dd>
FILE_SHARE_DELETE

</dd>
</dl>

`FileObject`

A pointer to the file object for which to check access for the current open request.

`ShareAccess`

A pointer to the common share-access data structure that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.

`Update`

Specifies whether to update the share-access status for <i>FileObject</i>. A Boolean value of <b>TRUE</b> means this routine will update the share access information for the file object if the open request is permitted.

`WritePermission`

Specifies whether the share access has write permission. This value is TRUE if the share has write permission; otherwise, FALSE. If  the value is FALSE and the share access has write permission and the caller attempts to take exclusive read access, the write permission is downgraded to FILE_SHARE_READ. This value is NULL if  a write permission check is not done on the share access.


## Return Value

The <b>IoCheckShareAccessEx</b> routine returns STATUS_SUCCESS if the requester's access to the file object is compatible with the way in which it is currently open. If the request is denied because of a sharing violation, then STATUS_SHARING_VIOLATION is returned.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549503">I/O Manager Routines</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCheckShareAccessEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>