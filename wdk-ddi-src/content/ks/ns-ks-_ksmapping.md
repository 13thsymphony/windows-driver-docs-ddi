---
UID: NS:ks._KSMAPPING
title: "_KSMAPPING"
author: windows-driver-content
description: The KSMAPPING structure is used to describe a single contiguous chunk of physical memory for use in scatter/gather DMA operations.
old-location: stream\ksmapping.htm
old-project: stream
ms.assetid: 9a5149dc-5506-4100-80fc-7cd17585d2af
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSMAPPING, KSMAPPING, KSMAPPING structure [Streaming Media Devices], PKSMAPPING, PKSMAPPING structure pointer [Streaming Media Devices], _KSMAPPING, avstruct_65f80fd5-14a6-431b-a1b6-e6c3d18302d3.xml, ks/KSMAPPING, ks/PKSMAPPING, stream.ksmapping"
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
-	KSMAPPING
product: Windows
targetos: Windows
req.typenames: KSMAPPING, *PKSMAPPING
---

# _KSMAPPING structure
The KSMAPPING structure is used to describe a single contiguous chunk of physical memory for use in scatter/gather DMA operations.

## Syntax
```
typedef struct _KSMAPPING {
  PHYSICAL_ADDRESS PhysicalAddress;
  ULONG            ByteCount;
  ULONG            Alignment;
} KSMAPPING, *PKSMAPPING;
```

## Members


`PhysicalAddress`

This member contains the physical address of this piece of the data frame.

`ByteCount`

This member contains the number of bytes of contiguous physical memory in this individual mapping.

`Alignment`

This member specifies the memory alignment in bytes for this buffer.

## Remarks
In order for minidrivers to use this structure within the stream pointer offsets, the pin for which this is referring must specify scatter/gather DMA mapping generation through KSPIN_FLAG_GENERATE_MAPPINGS and the client must register its DMA adapter object with AVStream using <b>KsDeviceRegisterAdapterObject</b>. See <a href="https://msdn.microsoft.com/ba1c525b-26b0-4778-b58b-f4169cfb972e">AVStream DMA Services</a>. The KSPIN_FLAG_GENERATE_MAPPINGS flag is defined on the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563534">KSPIN_DESCRIPTOR_EX</a> reference page.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions. Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions. |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567140">KSSTREAM_POINTER_OFFSET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561687">KsDeviceRegisterAdapterObject</a>