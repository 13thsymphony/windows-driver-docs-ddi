---
UID: NS:sercx._SERCX_ACTIVITY
title: "_SERCX_ACTIVITY"
author: windows-driver-content
description: The SERCX_ACTIVITY structure contains a summary of work items that are ready for the serial controller driver to process.
old-location: serports\sercx_activity.htm
old-project: serports
ms.assetid: 743AA179-3FD1-4528-9A78-5ECC53642D55
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSERCX_ACTIVITY, 1/PSERCX_ACTIVITY, 1/SERCX_ACTIVITY, PSERCX_ACTIVITY, PSERCX_ACTIVITY structure pointer [Serial Ports], SERCX_ACTIVITY, SERCX_ACTIVITY structure [Serial Ports], _SERCX_ACTIVITY, serports.sercx_activity"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: sercx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.irql: Any IRQL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	1.0\Sercx.h
api_name:
-	SERCX_ACTIVITY
product: Windows
targetos: Windows
req.typenames: SERCX_ACTIVITY, *PSERCX_ACTIVITY
req.product: Windows 10 or later.
---

# _SERCX_ACTIVITY structure
The <b>SERCX_ACTIVITY</b> structure contains a summary of work items that are ready for the serial controller driver to process.

## Syntax
```
typedef struct _SERCX_ACTIVITY {
  ULONG   Size;
  BOOLEAN Transmitting;
  BOOLEAN Receiving;
} *PSERCX_ACTIVITY, SERCX_ACTIVITY;
```

## Members


`Size`

The size, in bytes, of this structure. The <a href="https://msdn.microsoft.com/library/windows/hardware/hh406695">SerCxGetActivity</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.

`Transmitting`

Whether a transmit (write) operation is in progress. This member is TRUE if a transmit operation is in progress. Otherwise, it is FALSE.

`Receiving`

Whether a receive (read) operation is in progress. This member is TRUE if a receive operation is in progress. Otherwise, it is FALSE.

## Remarks
This structure must be initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439532">SERCX_ACTIVITY_INIT</a> function before its initial use. Thereafter, calls to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406695">SerCxGetActivity</a> method update the contents of this structure to indicate the work that is currently pending.

The <b>SERCX_ACTIVITY</b> structure summarizes the pending work that the serial framework extension (SerCx) assigns to the serial controller driver. This work is driven by I/O requests from clients, but an I/O request does not necessarily spawn a work item. For example, if SerCx has a sufficient amount of received data in its memory buffer to complete a pending read request, this request does not cause the <b>Receiving</b> member of the <b>SERCX_ACTIVITY</b> structure to be set to TRUE.

Typically, <b>SerCxGetActivity</b> is called from the main loop of the transmit/receive DPC function in the serial controller driver. This function calls <b>SerCxGetActivity</b>, processes a complete transmit or receive operation, and then calls <b>SerCxGetActivity</b> again to determine whether an operation of another type requires work.  If more work is available, the DPC function might perform this work before it returns.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Header** | sercx.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439532">SERCX_ACTIVITY_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406677">SerCxCompleteWait</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406695">SerCxGetActivity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406713">SerCxProgressReceive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406715">SerCxProgressTransmit</a>