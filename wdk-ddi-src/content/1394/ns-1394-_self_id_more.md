---
UID: NS:1394._SELF_ID_MORE
title: "_SELF_ID_MORE"
author: windows-driver-content
description: The SELF_ID_MORE structure contains a raw packet one, two, or three self-ID packet. See the IEEE 1394 specification for details.
old-location: ieee\self_id_more.htm
old-project: IEEE
ms.assetid: d3c164a6-4830-4f1f-9fa5-5cd61e796e31
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SELF_ID_MORE structure [Buses], PSELF_ID_MORE, 1394/SELF_ID_MORE, IEEE.self_id_more, _SELF_ID_MORE, *PSELF_ID_MORE, 1394/PSELF_ID_MORE, SELF_ID_MORE, PSELF_ID_MORE structure pointer [Buses], 1394stct_cbfa017d-065b-45ce-ae08-6a6589c6b477.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	SELF_ID_MORE
product: Windows
targetos: Windows
req.typenames: SELF_ID_MORE, *PSELF_ID_MORE
---

# _SELF_ID_MORE structure
The SELF_ID_MORE structure contains a raw packet one, two, or three self-ID packet. See the IEEE 1394 specification for details.

## Syntax
````
typedef struct _SELF_ID_MORE {
  ULONG SID_Phys_ID  :6;
  ULONG SID_Packet_ID  :2;
  ULONG SID_PortA  :2;
  ULONG SID_Reserved2  :2;
  ULONG SID_Sequence  :3;
  ULONG SID_One  :1;
  ULONG SID_PortE  :2;
  ULONG SID_PortD  :2;
  ULONG SID_PortC  :2;
  ULONG SID_PortB  :2;
  ULONG SID_More_Packets  :1;
  ULONG SID_Reserved3  :1;
  ULONG SID_PortH  :2;
  ULONG SID_PortG  :2;
  ULONG SID_PortF  :2;
} SELF_ID_MORE, *PSELF_ID_MORE;
````

## Members


`SID_More_Packets`

One if this packet will be followed by more SELF_ID_MORE packets, zero otherwise. This member contains bit 0 of byte 3 of the self ID packet.

`SID_One`

Always a 1. This member contains bit 6 of byte 1 of the self ID packet.

`SID_Packet_ID`

Must be PHY_PACKET_ID_SELF_ID. This member specifies bits 0-10 of the node address. This member contains bits 6-7 of byte 0 of the self ID packet.

`SID_Phys_ID`

Specifies the device node number. This member specifies bits 0-10 of the node address. This member contains bits 0-5 of byte 0 of the self ID packet.

`SID_PortA`

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member contains bits 0-1 of byte 1 of the self ID packet.

`SID_PortB`

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member contains bits 6-7 of byte 2 of the self ID packet.

`SID_PortC`

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member contains bits 4-5 of byte 2 of the self ID packet.

`SID_PortD`

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member specifies bits 2-3 of byte 2 of the self ID packet.

`SID_PortE`

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member specifies bits 0-1 of byte 2 of the self ID packet.

`SID_PortF`

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member contains bits 6-7 of byte 3 of the self ID packet.

`SID_PortG`

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member contains bits 4-5 of byte 3 of the self ID packet.

`SID_PortH`

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member contains bits 2-3 of byte 3 of the self ID packet.

`SID_Reserved2`

Reserved. This member contains bits 2-3 of byte 1 of the self ID packet.

`SID_Reserved3`

Reserved. This member contains bit 1 of byte 3 of the self ID packet.

`SID_Sequence`

Specifies the packet number in sequence (the first SELF_ID_MORE packet is packet zero). This member contains bits 4-5 of byte 1 of the self ID packet.

## Remarks
This structure corresponds to self ID packet 1, as described in the <i>P1394a</i> specification. Note that type 2 self ID packets are identical to type 1 packets, except that the last five fields are replaced by a reserved area. The SELF_ID_MORE structure can be used to access all of the significant information in both type 1 and type 2 self ID packets.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 1394.h (include 1394.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538877">TOPOLOGY_MAP</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20SELF_ID_MORE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>