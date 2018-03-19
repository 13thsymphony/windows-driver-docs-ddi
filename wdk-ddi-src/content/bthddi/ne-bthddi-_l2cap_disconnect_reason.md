---
UID: NE:bthddi._L2CAP_DISCONNECT_REASON
title: "_L2CAP_DISCONNECT_REASON"
author: windows-driver-content
description: The L2CAP_DISCONNECT_REASON enumeration type gives the reason an L2CAP channel has been disconnected.
old-location: bltooth\l2cap_disconnect_reason.htm
old-project: bltooth
ms.assetid: 34a37d29-c517-45dc-b94d-abffaa91cb31
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: HardwareRemoval, HciDisconnect, L2CAP_DISCONNECT_REASON, L2CAP_DISCONNECT_REASON enumeration [Bluetooth Devices], L2capDisconnectRequest, RadioPoweredDown, _L2CAP_DISCONNECT_REASON, bltooth.l2cap_disconnect_reason, bth_enums_b465d42e-515c-49b9-8d6c-0d576853a41b.xml, bthddi/HardwareRemoval, bthddi/HciDisconnect, bthddi/L2CAP_DISCONNECT_REASON, bthddi/L2capDisconnectRequest, bthddi/RadioPoweredDown
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista and later versions of Windows.
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	L2CAP_DISCONNECT_REASON
product: Windows
targetos: Windows
req.typenames: L2CAP_DISCONNECT_REASON
---

# _L2CAP_DISCONNECT_REASON Enumeration
The L2CAP_DISCONNECT_REASON enumeration type gives the reason an L2CAP channel has been
  disconnected.

## Syntax
````
typedef enum _L2CAP_DISCONNECT_REASON { 
  HciDisconnect           = 0,
  L2capDisconnectRequest  = 1,
  RadioPoweredDown        = 2,
  HardwareRemoval         = 3
} L2CAP_DISCONNECT_REASON;
````

## Constants

<table>
            
                <tr>
                    <td>HciDisconnect</td>
                    <td>The value specifies for the profile driver that the Bluetooth driver stack has received a
     disconnect notification from the host controller interface (HCI) layer.</td>
                </tr>
            
                <tr>
                    <td>L2capDisconnectRequest</td>
                    <td>This value specifies for the profile driver that a disconnect request has been received from a
     remote device.</td>
                </tr>
            
                <tr>
                    <td>RadioPoweredDown</td>
                    <td>This value specifies for the profile driver that the local radio has been turned off.</td>
                </tr>
            
                <tr>
                    <td>HardwareRemoval</td>
                    <td>This value specifies for the profile driver that the local radio has been physically
     removed.</td>
                </tr>
</table>

## Remarks

A value from this enumeration is used as the 
    <b>Reason</b> member of the 
    <a href="..\bthddi\ns-bthddi-_indication_parameters.md">INDICATION_PARAMETERS</a> structure.

Hardware limitations may prevent the Bluetooth driver stack from distinguishing between 
    <b>RadioPoweredDown</b> and 
    <b>HardwareRemoval</b> events.

Currently, 
    <i>HciDisconnect</i> and 
    <i>L2capDisconnectRequest</i> are the only values the Bluetooth driver stack passes to the 
    <a href="..\bthddi\nc-bthddi-pfnbthport_indication_callback.md">L2CAP Callback Function</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista and later versions of Windows. Versions:\_Supported in Windows Vista and later versions of Windows. |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="..\bthddi\ns-bthddi-_indication_parameters.md">INDICATION_PARAMETERS</a>