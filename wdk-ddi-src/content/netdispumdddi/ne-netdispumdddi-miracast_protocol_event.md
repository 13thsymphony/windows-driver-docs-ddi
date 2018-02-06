---
UID: NE:netdispumdddi.MIRACAST_PROTOCOL_EVENT
title: MIRACAST_PROTOCOL_EVENT
author: windows-driver-content
description: Specifies the types of wireless display (Miracast) protocol event that the user-mode display driver should report.
old-location: display\miracast_protocol_event.htm
old-project: display
ms.assetid: 7a47acf7-93a9-4bb2-a120-17c32c852ea9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: netdispumdddi/MIRACAST_PROTOCOL_EVENT, display.miracast_protocol_event, MIRACAST_PROTOCOL_EVENT_MONITOR_DEPART, MIRACAST_PROTOCOL_EVENT enumeration [Display Devices], MIRACAST_PROTOCOL_EVENT_SINK_FAILED_PREFERRED_MODE_CHANGE, netdispumdddi/MIRACAST_PROTOCOL_EVENT_IFRAME_RQ, MIRACAST_PROTOCOL_EVENT_MONITOR_ARRIVE, MIRACAST_PROTOCOL_EVENT, netdispumdddi/MIRACAST_PROTOCOL_EVENT_SINK_FAILED_PREFERRED_MODE_CHANGE, netdispumdddi/MIRACAST_PROTOCOL_EVENT_MONITOR_DEPART, netdispumdddi/MIRACAST_PROTOCOL_EVENT_FORCE_UINT32, MIRACAST_PROTOCOL_EVENT_IFRAME_RQ, MIRACAST_PROTOCOL_EVENT_FORCE_UINT32, netdispumdddi/MIRACAST_PROTOCOL_EVENT_MONITOR_ARRIVE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Netdispumdddi.h
apiname:
-	MIRACAST_PROTOCOL_EVENT
product: Windows
targetos: Windows
req.typenames: MIRACAST_PROTOCOL_EVENT
---

# MIRACAST_PROTOCOL_EVENT Enumeration
Specifies the types of wireless display (Miracast) protocol event that the user-mode display driver should report.

## Syntax
````
typedef enum  { 
  MIRACAST_PROTOCOL_EVENT_IFRAME_RQ                          = 0,
  MIRACAST_PROTOCOL_EVENT_MONITOR_ARRIVE                     = 1,
  MIRACAST_PROTOCOL_EVENT_MONITOR_DEPART                     = 2,
  MIRACAST_PROTOCOL_EVENT_SINK_FAILED_PREFERRED_MODE_CHANGE  = 3,
  MIRACAST_PROTOCOL_EVENT_FORCE_UINT32                       = 0xffffffff
} MIRACAST_PROTOCOL_EVENT;
````

## Constants

<table>
            
                <tr>
                    <td>MIRACAST_PROTOCOL_EVENT_FORCE_UINT32</td>
                    <td>Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.</td>
                </tr>
            
                <tr>
                    <td>MIRACAST_PROTOCOL_EVENT_IFRAME_RQ</td>
                    <td>The driver received a request for a new IDR type of I-frame from the Miracast sink.</td>
                </tr>
            
                <tr>
                    <td>MIRACAST_PROTOCOL_EVENT_MONITOR_ARRIVE</td>
                    <td>The driver received a monitor connection event from the Miracast sink.</td>
                </tr>
            
                <tr>
                    <td>MIRACAST_PROTOCOL_EVENT_MONITOR_DEPART</td>
                    <td>The driver received a monitor disconnection event from the Miracast sink.</td>
                </tr>
            
                <tr>
                    <td>MIRACAST_PROTOCOL_EVENT_SINK_FAILED_PREFERRED_MODE_CHANGE</td>
                    <td>Reserved for system use. Do not use in your driver.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | netdispumdddi.h (include Netdispumdddi.h) |