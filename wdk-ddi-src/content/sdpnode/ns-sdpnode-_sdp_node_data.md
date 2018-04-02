---
UID: NS:sdpnode._SDP_NODE_DATA
title: "_SDP_NODE_DATA"
author: windows-driver-content
description: The SDP_NODE_DATA union holds the data of an element in a tree-based representation of an SDP record.
old-location: bltooth\sdp_node_data.htm
old-project: bltooth
ms.assetid: ce1f9f1b-2215-4b39-b5e6-a5076f02af64
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSDP_NODE_DATA, PSDP_NODE_DATA, PSDP_NODE_DATA union pointer [Bluetooth Devices], SDP_NODE_DATA, SDP_NODE_DATA union [Bluetooth Devices], _SDP_NODE_DATA, bltooth.sdp_node_data, bth_structs_c97da04d-31d0-4e0b-b909-9a1fae7d53dd.xml, sdpnode/PSDP_NODE_DATA, sdpnode/SDP_NODE_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: sdpnode.h
req.include-header: Sdpnode.h
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	sdpnode.h
api_name:
-	SDP_NODE_DATA
product: Windows
targetos: Windows
req.typenames: SDP_NODE_DATA, *PSDP_NODE_DATA
req.product: Windows 10 or later.
---

# _SDP_NODE_DATA structure
The SDP_NODE_DATA union holds the data of an element in a tree-based representation of an SDP
  record.

## Syntax
```
typedef struct _SDP_NODE_DATA {
  SDP_LARGE_INTEGER_16  int128;
  SDP_ULARGE_INTEGER_16 uint128;
  GUID                  uuid128;
  ULONG                 uuid32;
  USHORT                uuid16;
  LONGLONG              int64;
  ULONGLONG             uint64;
  LONG                  int32;
  ULONG                 uint32;
  SHORT                 int16;
  USHORT                uint16;
  CHAR                  int8;
  UCHAR                 uint8;
  SDP_BOOLEAN           boolean;
  PCHAR                 string;
  PCHAR                 url;
  SDP_NODE_HEADER       sequence;
  SDP_NODE_HEADER       alternative;
  ISdpNodeContainer     *container;
  struct {
    PUCHAR stream;
    ULONG  streamLength;
  };
} *PSDP_NODE_DATA, SDP_NODE_DATA;
```

## Members


`int128`

The union member for a 128-bit integer.

`uint128`

The union member for an unsigned 128-bit integer.

`uuid128`

The union member for a 128-bit universally unique identifier (UUID).

`uuid32`

The union member for a 32-bit UUID.

`uuid16`

The union member for a 16-bit UUID.

`int64`

The union member for a 64-bit integer.

`uint64`

The union member for an unsigned 64-bit integer.

`int32`

The union member for a 32-bit integer.

`uint32`

The union member for an unsigned 32-bit integer.

`int16`

The union member for a 16-bit integer.

`uint16`

The union member for an unsigned 16-bit integer.

`int8`

The union reserved for an 8-bit integer.

`uint8`

The union member for an unsigned 8-bit integer.

`boolean`

The union member for a Boolean value.

`string`

The union member for a string value.

`url`

The union member for a URL value.

`sequence`

An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536850">SDP_NODE_HEADER</a> structure that references
     the elements of a sequence.

`alternative`

An SDP_NODE_HEADER structure that references the elements of an alternate list sequence.

`container`

A list of pointers to user-mode specific interfaces.

## Remarks
Each 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a> structure in the tree representation of an
    SDP record contains a SDP_NODE_HEADER structure and an SDP_NODE_DATA union.

The header specifies the type of data. Driver developers can access links to peer 
    <b>SDP_NODE</b> structures by calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure of the header. By evaluating 
    <code>Node.hdr.Link.Flink</code>and 
    <code>Node.hdr.Link.Blink</code>, drivers can obtain the addresses of peer
    nodes in the tree. Keep in mind that 
    <b>LIST_ENTRY</b> pointers contain the addresses of other LIST_ENTRY structures, and that the profile
    driver must use the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a> memory manager macro to
    extract the address of the containing node record.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | sdpnode.h (include Sdpnode.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536850">SDP_NODE_HEADER</a>