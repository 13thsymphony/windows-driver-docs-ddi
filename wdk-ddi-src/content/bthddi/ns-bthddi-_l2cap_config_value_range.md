---
UID: NS:bthddi._L2CAP_CONFIG_VALUE_RANGE
title: "_L2CAP_CONFIG_VALUE_RANGE"
author: windows-driver-content
description: The L2CAP_CONFIG_VALUE_RANGE structure is used to specify values for the Mtu and FlushTO members of the _BRB_L2CA_OPEN_CHANNEL structure.
old-location: bltooth\l2cap_config_value_range.htm
old-project: bltooth
ms.assetid: 12d9b0c1-6dce-4dc6-a8df-706408e1fbe1
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PL2CAP_CONFIG_VALUE_RANGE, L2CAP_CONFIG_VALUE_RANGE, L2CAP_CONFIG_VALUE_RANGE structure [Bluetooth Devices], PL2CAP_CONFIG_VALUE_RANGE, PL2CAP_CONFIG_VALUE_RANGE structure pointer [Bluetooth Devices], _L2CAP_CONFIG_VALUE_RANGE, bltooth.l2cap_config_value_range, bth_structs_3af526a5-d36e-432f-9d2e-fa31bee0effe.xml, bthddi/L2CAP_CONFIG_VALUE_RANGE, bthddi/PL2CAP_CONFIG_VALUE_RANGE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
-	L2CAP_CONFIG_VALUE_RANGE
product: Windows
targetos: Windows
req.typenames: L2CAP_CONFIG_VALUE_RANGE, *PL2CAP_CONFIG_VALUE_RANGE
---

# _L2CAP_CONFIG_VALUE_RANGE structure
The L2CAP_CONFIG_VALUE_RANGE structure is used to specify values for the 
  <b>Mtu</b> and 
  <b>FlushTO</b> members of the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff536860">_BRB_L2CA_OPEN_CHANNEL</a> structure.

## Syntax
```
typedef struct _L2CAP_CONFIG_VALUE_RANGE {
  USHORT Min;
  USHORT Preferred;
  USHORT Max;
} *PL2CAP_CONFIG_VALUE_RANGE, L2CAP_CONFIG_VALUE_RANGE;
```

## Members


`Min`

The minimum value that the local system will accept.

`Preferred`

The ideal value that the local system requests that the remote device accept.

`Max`

The maximum value that the local system will accept.

## Remarks
For 
    <b>FlushTO</b> member settings, the L2CAP_CONFIG_VALUE_RANGE structure contains the profile driver's ideal
    flush timeout value in the 
    <b>Preferred</b> member, along with a range of acceptable values as specified by the 
    <b>Min</b> and 
    <b>Max</b> members.

The profile driver uses a <b>BRB_L2CA_OPEN_CHANNEL</b> request to send these settings to a remote device with
    which it is attempting to create a L2CAP connection. If the 
    <b>Preferred</b> value that is sent by the profile driver falls in the range specified by the remote
    device, the 
    <b>FlushTO</b> settings are accepted. If the remote device rejects the setting as being too long, the
    remote device responds with the maximum setting it will accept. If the remote device's maximum flush
    timeout falls within the range defined by the 
    <b>Min</b> and 
    <b>Max</b> members, the 
    <b>FlushTO</b> value is accepted. Otherwise, the remote device rejects the 
    <b>FlushTO</b> value and the connection attempt fails.

If the remote device rejects the profile driver's 
    <b>Preferred</b> member value as being too short, the remote device responds with the minimum settings it
    will accept. If the remote device's minimum flush timeout falls within the range defined by the 
    <b>Min</b> and 
    <b>Max</b> members, the 
    <b>FlushTO</b> value is accepted. Otherwise, the remote device rejects the 
    <b>FlushTO</b> value and the connection attempt fails.

The profile driver negotiates these values separately from the flush timeout settings that it sends to
    the Bluetooth driver stack when a remote device attempts to create an inbound L2CAP channel to the
    profile driver. For more information about L2CAP configuration ranges, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536760">L2CAP_CONFIG_RANGE</a>.

For 
    <b>Mtu</b> members settings, this structure provides 
    <b>Preferred</b>, 
    <b>Min</b>, and 
    <b>Max</b> settings for both inbound and outbound connections.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536860">_BRB_L2CA_OPEN_CHANNEL</a>