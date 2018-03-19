---
UID: NS:ks._KSSTREAM_POINTER_OFFSET
title: "_KSSTREAM_POINTER_OFFSET"
author: windows-driver-content
description: The KSSTREAM_POINTER_OFFSET structure indexes bytes or mappings within a frame.
old-location: stream\ksstream_pointer_offset.htm
old-project: stream
ms.assetid: ccbe77ee-2377-45d9-b8bf-714680c1920a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSSTREAM_POINTER_OFFSET, KSSTREAM_POINTER_OFFSET, KSSTREAM_POINTER_OFFSET structure [Streaming Media Devices], PKSSTREAM_POINTER_OFFSET, PKSSTREAM_POINTER_OFFSET structure pointer [Streaming Media Devices], _KSSTREAM_POINTER_OFFSET, avstruct_e210364b-520e-4d21-98ea-e22f5468e911.xml, ks/KSSTREAM_POINTER_OFFSET, ks/PKSSTREAM_POINTER_OFFSET, stream.ksstream_pointer_offset"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSSTREAM_POINTER_OFFSET
product: Windows
targetos: Windows
req.typenames: KSSTREAM_POINTER_OFFSET, *PKSSTREAM_POINTER_OFFSET
---

# _KSSTREAM_POINTER_OFFSET structure
The KSSTREAM_POINTER_OFFSET structure indexes bytes or mappings within a frame.

## Syntax
````
typedef struct _KSSTREAM_POINTER_OFFSET {
  union {
    PUCHAR     Data;
    PKSMAPPING Mappings;
  };
  ULONG Count;
  ULONG Remaining;
} KSSTREAM_POINTER_OFFSET, *PKSSTREAM_POINTER_OFFSET;
````

## Members


`Data`

A pointer to a buffer containing input data or a buffer to which data is to be output. Specify <b>Data</b> if the minidriver does not set the KSPIN_FLAG_GENERATE_MAPPINGS flag in the <b>Flags</b> member of <a href="..\ks\ns-ks-_kspin_descriptor_ex.md">KSPIN_DESCRIPTOR_EX</a>.

`Alignment`



`Count`

If <b>Data</b> is specified above, <b>Count</b> contains the total number of bytes of data available in the <b>Data</b> buffer. If <b>Mappings</b> is specified above, <b>Count</b> contains the total number of mappings in the <b>Mappings</b> table. <b>Count</b> does not change unless the stream pointer moves to a different <i>Frame</i>.

`Remaining`

This member specifies a value of type ULONG that indicates the number of bytes or mappings remaining at and ahead of the given stream pointer. This value is equal to <b>Count</b> minus the number of bytes or mappings that have been processed. <b>Remaining</b> starts equal to <b>Count</b> and decreases as the stream pointer moves forward.

## Remarks
See also <a href="https://msdn.microsoft.com/ba1c525b-26b0-4778-b58b-f4169cfb972e">AVStream DMA Services</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions. Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions. |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-_ksmapping.md">KSMAPPING</a>



<a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a>