---
UID: NS.UCXROOTHUB._ROOTHUB_30PORTS_INFO
title: _ROOTHUB_30PORTS_INFO
author: windows-driver-content
description: Provides information about USB 3.0 root hub ports. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_30PORT_INFO callback function.
old-location: buses\_roothub_30ports_info.htm
old-project: UsbRef
ms.assetid: 2E727D84-193C-45AA-AEC4-75B72BB23FC9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _ROOTHUB_30PORTS_INFO, *PROOTHUB_30PORTS_INFO, ROOTHUB_30PORTS_INFO, PROOTHUB_30PORTS_INFO
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
req.alt-api: ROOTHUB_30PORTS_INFO
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

# _ROOTHUB_30PORTS_INFO structure



## -description
Provides information about USB 3.0 root hub ports. This structure is passed by UCX in the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_get_30port_info.md">EVT_UCX_ROOTHUB_GET_30PORT_INFO</a> callback function.



## -syntax

````
typedef struct _ROOTHUB_30PORTS_INFO {
  ULONG                 Size;
  USHORT                NumberOfPorts;
  USHORT                PortInfoSize;
   PROOTHUB_30PORT_INFO *PortInfoArray;
} ROOTHUB_30PORTS_INFO, *P_ROOTHUB_30PORTS_INFO;
````


## -struct-fields

### -field Size

The size in bytes of this structure.


### -field NumberOfPorts

Number of USB 3.0 root hub ports.


### -field PortInfoSize

The size of the <a href="buses._roothub_30port_info">ROOTHUB_30PORT_INFO</a> array.


### -field PortInfoArray

A pointer to an array of  <a href="buses._roothub_30port_info">ROOTHUB_30PORT_INFO</a> structures.


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

## -see-also
<dl>
<dt>
<a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_get_30port_info.md">EVT_UCX_ROOTHUB_GET_30PORT_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20ROOTHUB_30PORTS_INFO structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

