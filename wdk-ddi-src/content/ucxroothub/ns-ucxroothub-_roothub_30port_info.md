---
UID: NS.UCXROOTHUB._ROOTHUB_30PORT_INFO
title: _ROOTHUB_30PORT_INFO
author: windows-driver-content
description: Provides information about a USB 3.0 root hub port. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_30PORT_INFO callback function.
old-location: buses\_roothub_30port_info.htm
old-project: UsbRef
ms.assetid: 5C39C0EB-AC7F-44E5-95EB-9F067DBE0801
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _ROOTHUB_30PORT_INFO, PROOTHUB_30PORT_INFO, *PROOTHUB_30PORT_INFO, ROOTHUB_30PORT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxroothub.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ROOTHUB_30PORT_INFO
req.alt-loc: ucxroothub.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# _ROOTHUB_30PORT_INFO structure



## -description
Provides information about a USB 3.0 root hub port. This structure is passed by UCX in the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_get_30port_info.md">EVT_UCX_ROOTHUB_GET_30PORT_INFO</a> callback function.



## -syntax

````
typedef struct _ROOTHUB_30PORT_INFO {
  USHORT   PortNumber;
  UCHAR    MinorRevision;
  UCHAR    HubDepth;
  TRISTATE Removable;
  TRISTATE DebugCapable;
} ROOTHUB_30PORT_INFO, *P_ROOTHUB_30PORT_INFO;
````


## -struct-fields

### -field PortNumber

The USB 3.0 port number connected to the root hub.


### -field MinorRevision

Revision number.


### -field HubDepth

The hub depth limit.


### -field Removable

A <a href="buses.tristate">TRISTATE</a> value that indicates if the port is removable. 


### -field DebugCapable

A <a href="buses.tristate">TRISTATE</a> value that indicates if the port is debug capable. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ucxroothub.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
</table>