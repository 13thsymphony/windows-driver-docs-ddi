---
UID: NS:wsk._WSK_TRANSPORT
title: "_WSK_TRANSPORT"
author: windows-driver-content
description: The WSK_TRANSPORT structure specifies an available transport that is supported by the WSK subsystem.
old-location: netvista\wsk_transport.htm
old-project: netvista
ms.assetid: aaf7b5ac-0401-4b6a-a478-3d50559817db
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWSK_TRANSPORT, PWSK_TRANSPORT, PWSK_TRANSPORT structure pointer [Network Drivers Starting with Windows Vista], WSK_TRANSPORT, WSK_TRANSPORT structure [Network Drivers Starting with Windows Vista], _WSK_TRANSPORT, netvista.wsk_transport, wsk/PWSK_TRANSPORT, wsk/WSK_TRANSPORT, wskref_be7d6a6d-971e-49de-bc64-ebd1f1d04085.xml"
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
-	WSK_TRANSPORT
product:
- Windows
targetos: Windows
req.typenames: WSK_TRANSPORT, *PWSK_TRANSPORT
req.product: Windows 10 or later.
---

# _WSK_TRANSPORT structure
The WSK_TRANSPORT structure specifies an available transport that is supported by the WSK
  subsystem.

## Syntax
```
typedef struct _WSK_TRANSPORT {
  USHORT         Version;
  USHORT         SocketType;
  ULONG          Protocol;
  ADDRESS_FAMILY AddressFamily;
  GUID           ProviderId;
} WSK_TRANSPORT, *PWSK_TRANSPORT;
```

## Members


`Version`

The version of the transport. The format of the version number is transport-specific.

`SocketType`

The type of socket that is supported by the transport. This member can be one of the following:
     





#### SOCK_STREAM

Supports reliable connection-oriented byte stream communication.



#### SOCK_DGRAM

Supports unreliable connectionless datagram communication.



#### SOCK_RAW

Supports raw access to the transport protocol.

For more information about the socket types that are supported for each supported address family, see
     
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571151">WSK Address Families</a>.

`Protocol`

The protocol that is supported by the transport. For more information about the protocols that are
     supported for each supported address family, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571151">WSK Address Families</a>.

`AddressFamily`

The address family that is supported by the transport. For more information about supported
     address families, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571151">WSK Address Families</a>.

`ProviderId`

The identifier of the transport provider that implements the transport.

## Remarks
A WSK application passes a pointer to an array of WSK_TRANSPORT structures to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571126">WskControlClient</a> function when specifying
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571195">WSK_TRANSPORT_LIST_QUERY</a> control
    code. The WSK subsystem fills in the array with the list of available transports that can be used for
    socket communication. When a WSK application calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a> or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571150">WskSocketConnect</a> function to create a new
    socket, it can pass the values contained in the 
    <b>AddressFamily</b>, 
    <b>SocketType</b>, and 
    <b>Protocol</b> members of a returned WSK_TRANSPORT structure for the 
    <i>AddressFamily</i>, 
    <i>SocketType</i>, and 
    <i>Protocol</i> parameters.

A single transport provider can support multiple combinations of values for the 
    <b>AddressFamily</b>, 
    <b>SocketType</b>, and 
    <b>Protocol</b> members.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | wsk.h (include Wsk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff571126">WskControlClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571150">WskSocketConnect</a>