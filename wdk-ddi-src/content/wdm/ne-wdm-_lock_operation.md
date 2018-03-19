---
UID: NE:wdm._LOCK_OPERATION
title: "_LOCK_OPERATION"
author: windows-driver-content
description: The LOCK_OPERATION enumeration specifies the type of access that is appropriate for a type of I/O operation.
old-location: ifsk\lock_operation.htm
old-project: ifsk
ms.assetid: 25b2dd6a-2e20-4221-bef4-0001bbaae1d5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoModifyAccess, IoReadAccess, IoWriteAccess, LOCK_OPERATION, LOCK_OPERATION enumeration [Installable File System Drivers], _LOCK_OPERATION, ifsk.lock_operation, wdm/IoModifyAccess, wdm/IoReadAccess, wdm/IoWriteAccess, wdm/LOCK_OPERATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating system.
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
-	LOCK_OPERATION
product: Windows
targetos: Windows
req.typenames: LOCK_OPERATION
req.product: Windows 10 or later.
---

# _LOCK_OPERATION Enumeration
The <b>LOCK_OPERATION</b> enumeration specifies the type of access that is appropriate for a type of I/O operation.

## Syntax
````
typedef enum  { 
  IoReadAccess,
  IoWriteAccess,
  IoModifyAccess
} LOCK_OPERATION;
````

## Constants

<table>
            
                <tr>
                    <td>IoReadAccess</td>
                    <td>This value indicates that a driver  can examine the contents of a buffer but cannot change the contents.</td>
                </tr>
            
                <tr>
                    <td>IoWriteAccess</td>
                    <td>This value indicates that a driver can examine and change the contents of a buffer.</td>
                </tr>
            
                <tr>
                    <td>IoModifyAccess</td>
                    <td>This value indicates that a driver can examine and change the contents of a buffer.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating system. Available in Windows 2000 and later versions of the Windows operating system. |
| **Header** | wdm.h (include Wdm.h) |

## See Also

<a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>



<a href="..\fltkernel\nf-fltkernel-fltdecodeparameters.md">FltDecodeParameters</a>