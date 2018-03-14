---
UID: NE:wdm._IO_PAGING_PRIORITY
title: "_IO_PAGING_PRIORITY"
author: windows-driver-content
description: The IO_PAGING_PRIORITY enumeration describes the priority value for a paging I/O IRP.
old-location: kernel\io_paging_priority.htm
old-project: kernel
ms.assetid: c96d1c81-429f-46de-b56c-6424734ccd7a
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IO_PAGING_PRIORITY, IO_PAGING_PRIORITY enumeration [Kernel-Mode Driver Architecture], IoPagingPriorityHigh, IoPagingPriorityInvalid, IoPagingPriorityNormal, IoPagingPriorityReserved1, IoPagingPriorityReserved2, _IO_PAGING_PRIORITY, kernel.io_paging_priority, sysenum_8e021ebd-f26a-4749-8e76-c540af5dfae1.xml, wdm/IO_PAGING_PRIORITY, wdm/IoPagingPriorityHigh, wdm/IoPagingPriorityInvalid, wdm/IoPagingPriorityNormal, wdm/IoPagingPriorityReserved1, wdm/IoPagingPriorityReserved2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	IO_PAGING_PRIORITY
product: Windows
targetos: Windows
req.typenames: IO_PAGING_PRIORITY
req.product: Windows 10 or later.
---

# _IO_PAGING_PRIORITY Enumeration
The <b>IO_PAGING_PRIORITY</b> enumeration describes the priority value for a paging I/O IRP.

## Syntax
````
typedef enum _IO_PAGING_PRIORITY { 
  IoPagingPriorityInvalid    = 0,
  IoPagingPriorityNormal     = 1,
  IoPagingPriorityHigh       = 2,
  IoPagingPriorityReserved1  = 3,
  IoPagingPriorityReserved2  = 4
} IO_PAGING_PRIORITY;
````

## Constants

<table>
            
                <tr>
                    <td>IoPagingPriorityHigh</td>
                    <td>The associated IRP has a high priority level for paging I/O.</td>
                </tr>
            
                <tr>
                    <td>IoPagingPriorityInvalid</td>
                    <td>The IRP is not a paging I/O IRP.</td>
                </tr>
            
                <tr>
                    <td>IoPagingPriorityNormal</td>
                    <td>The associated IRP has a normal priority level for paging I/O.</td>
                </tr>
            
                <tr>
                    <td>IoPagingPriorityReserved1</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>IoPagingPriorityReserved2</td>
                    <td>Reserved for system use.</td>
                </tr>
</table>

## Remarks

The <a href="..\ntddk\nf-ntddk-iogetpagingiopriority.md">IoGetPagingIoPriority</a> routine returns an <b>IO_PAGING_PRIORITY</b> value to indicate the priority value of a paging I/O IRP.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\ntddk\nf-ntddk-iogetpagingiopriority.md">IoGetPagingIoPriority</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_PAGING_PRIORITY enumeration%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>