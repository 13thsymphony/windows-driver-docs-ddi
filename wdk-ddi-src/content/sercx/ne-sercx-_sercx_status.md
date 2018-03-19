---
UID: NE:sercx._SERCX_STATUS
title: "_SERCX_STATUS"
author: windows-driver-content
description: The SERCX_STATUS enumeration indicates the status of a serial receive or transmit operation.
old-location: serports\sercx_status.htm
old-project: serports
ms.assetid: 7EF129C7-25C3-49D2-8FC5-FFA1C4E77935
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSERCX_STATUS, 1/SERCX_STATUS, 1/SerCxStatusCancelled, 1/SerCxStatusSuccess, 1/SerCxStatusTimeout, SERCX_STATUS, SERCX_STATUS enumeration [Serial Ports], SerCxStatusCancelled, SerCxStatusSuccess, SerCxStatusTimeout, _SERCX_STATUS, serports.sercx_status"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: Called at IRQL <= DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	1.0\Sercx.h
api_name:
-	SERCX_STATUS
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# _SERCX_STATUS Enumeration
The <b>SERCX_STATUS</b> enumeration indicates the status of a serial receive or transmit operation.

## Syntax
````
typedef enum _SERCX_STATUS { 
  SerCxStatusSuccess    = STATUS_SUCCESS,
  SerCxStatusCancelled  = STATUS_CANCELLED,
  SerCxStatusTimeout    = STATUS_TIMEOUT
} SERCX_STATUS;
````

## Constants

<table>
            
                <tr>
                    <td>SerCxStatusSuccess</td>
                    <td>The operation is proceeding successfully.</td>
                </tr>
            
                <tr>
                    <td>SerCxStatusCancelled</td>
                    <td>The operation was canceled.</td>
                </tr>
            
                <tr>
                    <td>SerCxStatusTimeout</td>
                    <td>The operation timed out. This enumeration value applies only to read interval time-outs for receive operations. For more information, see the description of the <b>ReadIntervalTimeout</b> member in <a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>.</td>
                </tr>
</table>

## Remarks

The <a href="..\sercx\nf-sercx-sercxprogressreceive.md">SerCxProgressReceive</a> and <a href="..\sercx\nf-sercx-sercxprogresstransmit.md">SerCxProgressTransmit</a> methods have parameters that are <b>SERCX_STATUS</b> enumeration values.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Header** | sercx.h |

## See Also

<a href="..\sercx\nf-sercx-sercxprogressreceive.md">SerCxProgressReceive</a>



<a href="..\sercx\nf-sercx-sercxprogresstransmit.md">SerCxProgressTransmit</a>



<a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>