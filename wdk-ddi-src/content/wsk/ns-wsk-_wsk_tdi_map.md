---
UID: NS:wsk._WSK_TDI_MAP
title: "_WSK_TDI_MAP"
author: windows-driver-content
description: The WSK_TDI_MAP structure specifies a mapping between a particular address family, socket type, and protocol to the device name of a TDI transport.
old-location: netvista\wsk_tdi_map.htm
old-project: netvista
ms.assetid: 4c1407e9-2e4d-41cc-8d50-017c8c2bf20f
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWSK_TDI_MAP, PWSK_TDI_MAP, PWSK_TDI_MAP structure pointer [Network Drivers Starting with Windows Vista], WSK_TDI_MAP, WSK_TDI_MAP structure [Network Drivers Starting with Windows Vista], _WSK_TDI_MAP, netvista.wsk_tdi_map, wsk/PWSK_TDI_MAP, wsk/WSK_TDI_MAP, wskref_7be2eb13-c9b8-4fc8-bc00-b3d168353ed0.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wsk.h
api_name:
-	WSK_TDI_MAP
product: Windows
targetos: Windows
req.typenames: WSK_TDI_MAP, *PWSK_TDI_MAP
req.product: Windows 10 or later.
---

# _WSK_TDI_MAP structure
The WSK_TDI_MAP structure specifies a mapping between a particular address family, socket type, and
  protocol to the device name of a 
  <a href="https://msdn.microsoft.com/3878053c-388a-4bbc-a30e-feb16eda2f99">TDI</a> transport.

## Syntax
```
typedef struct _WSK_TDI_MAP {
  USHORT         SocketType;
  ADDRESS_FAMILY AddressFamily;
  ULONG          Protocol;
  PCWSTR         TdiDeviceName;
} WSK_TDI_MAP, *PWSK_TDI_MAP;
```

## Members


`SocketType`

The socket type. This member can contain any of the SOCK_<i>XXX</i> values that are defined in the 
     Ws2def.h header file.

`AddressFamily`

The address family. This member can contain any of the AF_<i>XXX</i> values that are defined in the 
     Ws2def.h header file.

`Protocol`

The transport protocol.

`TdiDeviceName`

A pointer to a null-terminated wide character string that contains the device name for the 
     <a href="https://msdn.microsoft.com/7c432f72-4de6-40a8-884c-26e13926e550">TDI</a> transport that supports the combination of
     address family, socket type, and protocol specified by the 
     <b>AddressFamily</b>, 
     <b>SocketType</b>, and 
     <b>Protocol</b> members.

## Remarks
The 
    <b>Map</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571192">WSK_TDI_MAP_INFO</a> structure points to an
    array of WSK_TDI_MAP structures, each of which contains a mapping between a particular address family,
    socket type, and protocol to the device name of a 
    <a href="https://msdn.microsoft.com/3878053c-388a-4bbc-a30e-feb16eda2f99">TDI</a> transport.

For more information about using TDI transports, see 
    <a href="https://msdn.microsoft.com/58fb5e62-e15d-4f15-8eb3-3e302ea08c4f">Using TDI Transports</a>.

<div class="alert"><b>Note</b>  TDI will not be supported in Microsoft Windows versions after Windows Vista. Use 
    <a href="https://msdn.microsoft.com/b9d88e59-3c4b-4804-8dd9-02c275927a1e">Windows Filtering
    Platform</a> or 
    <a href="https://msdn.microsoft.com/90264a3d-f002-4205-8e15-9060644117a3">Winsock Kernel</a> instead.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | wsk.h (include Wsk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff571192">WSK_TDI_MAP_INFO</a>