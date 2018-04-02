---
UID: NS:bthddi._SCO_INDICATION_PARAMETERS
title: "_SCO_INDICATION_PARAMETERS"
author: windows-driver-content
description: The SCO_INDICATION_PARAMETERS structure describes indication parameters about a SCO connect or disconnect notification.
old-location: bltooth\sco_indication_parameters.htm
old-project: bltooth
ms.assetid: 2d3ae219-8a40-476c-b8eb-94f4c0566527
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSCO_INDICATION_PARAMETERS, PSCO_INDICATION_PARAMETERS, PSCO_INDICATION_PARAMETERS structure pointer [Bluetooth Devices], SCO_INDICATION_PARAMETERS, SCO_INDICATION_PARAMETERS structure [Bluetooth Devices], _SCO_INDICATION_PARAMETERS, bltooth.sco_indication_parameters, bth_structs_73ebf679-d092-4b0a-a54f-84539b8c85ae.xml, bthddi/PSCO_INDICATION_PARAMETERS, bthddi/SCO_INDICATION_PARAMETERS"
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
-	SCO_INDICATION_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: SCO_INDICATION_PARAMETERS, *PSCO_INDICATION_PARAMETERS
---

# _SCO_INDICATION_PARAMETERS structure
The SCO_INDICATION_PARAMETERS structure describes indication parameters about a SCO connect or
  disconnect notification.

## Syntax
```
typedef struct _SCO_INDICATION_PARAMETERS {
  SCO_CHANNEL_HANDLE ConnectionHandle;
  BTH_ADDR           BtAddress;
  union {
    struct {
      struct {
        SCO_LINK_TYPE LinkType;
      } Request;
    } Connect;
    struct {
      SCO_DISCONNECT_REASON Reason;
      BOOLEAN               CloseNow;
    } Disconnect;
  } Parameters;
} *PSCO_INDICATION_PARAMETERS, SCO_INDICATION_PARAMETERS;
```

## Members


`ConnectionHandle`

A connection handle to the remote device. This handle is only valid for notifications that arrive
     over an established SCO connection.

`BtAddress`

The Bluetooth address of the remote device.

`Parameters`

####

## Remarks
A profile driver's 
    <a href="https://msdn.microsoft.com/abc9fc88-6852-4bfb-8271-7a73a508c397">SCO Callback Function</a> should process
    a notification differently depending upon the value that the Bluetooth driver stack passes in the 
    <i>Indication</i> parameter of the callback function.

When the Bluetooth driver stack passes 
    <b>ScoIndicationRemoteConnect</b>, the callback function should use the 
    <b>Connect</b> member of the 
    <b>Parameters</b> union.

When the Bluetooth driver stack passes 
    <b>ScoIndicationRemoteDisconnect</b>, the callback function should use the 
    <b>Disconnect</b> member of the 
    <b>Parameters</b> union.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="https://msdn.microsoft.com/abc9fc88-6852-4bfb-8271-7a73a508c397">SCO Callback Function</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536775">SCO_DISCONNECT_REASON</a>