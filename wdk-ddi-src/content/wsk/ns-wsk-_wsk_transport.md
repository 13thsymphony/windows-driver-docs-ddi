---
UID : NS:wsk._WSK_TRANSPORT
title : _WSK_TRANSPORT
author : windows-driver-content
description : The WSK_TRANSPORT structure specifies an available transport that is supported by the WSK subsystem.
old-location : netvista\wsk_transport.htm
old-project : netvista
ms.assetid : aaf7b5ac-0401-4b6a-a478-3d50559817db
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : _WSK_TRANSPORT, wsk/PWSK_TRANSPORT, *PWSK_TRANSPORT, netvista.wsk_transport, WSK_TRANSPORT, WSK_TRANSPORT structure [Network Drivers Starting with Windows Vista], wskref_be7d6a6d-971e-49de-bc64-ebd1f1d04085.xml, wsk/WSK_TRANSPORT, PWSK_TRANSPORT structure pointer [Network Drivers Starting with Windows Vista], PWSK_TRANSPORT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wsk.h
req.include-header : Wsk.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWSK_TRANSPORT, WSK_TRANSPORT"
req.product : Windows 10 or later.
---

# _WSK_TRANSPORT structure
The WSK_TRANSPORT structure specifies an available transport that is supported by the WSK
  subsystem.

## Syntax
````
typedef struct _WSK_TRANSPORT {
  USHORT         Version;
  USHORT         SocketType;
  ULONG          Protocol;
  ADDRESS_FAMILY AddressFamily;
  GUID           ProviderId;
} WSK_TRANSPORT, *PWSK_TRANSPORT;
````

## Members


`AddressFamily`

The address family that is supported by the transport. For more information about supported
     address families, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571151">WSK Address Families</a>.

`Protocol`

The protocol that is supported by the transport. For more information about the protocols that are
     supported for each supported address family, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571151">WSK Address Families</a>.

`ProviderId`

The identifier of the transport provider that implements the transport.

`SocketType`

The type of socket that is supported by the transport. This member can be one of the following:
     



For more information about the socket types that are supported for each supported address family, see
     
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571151">WSK Address Families</a>.

`Version`

The version of the transport. The format of the version number is transport-specific.

## Remarks
A WSK application passes a pointer to an array of WSK_TRANSPORT structures to the 
    <a href="..\wsk\nc-wsk-pfn_wsk_control_client.md">WskControlClient</a> function when specifying
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571195">WSK_TRANSPORT_LIST_QUERY</a> control
    code. The WSK subsystem fills in the array with the list of available transports that can be used for
    socket communication. When a WSK application calls the 
    <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> or 
    <a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a> function to create a new
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
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wsk.h (include Wsk.h) |

## See Also

<a href="..\wsk\nc-wsk-pfn_wsk_control_client.md">WskControlClient</a>

<a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a>

<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_TRANSPORT structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>