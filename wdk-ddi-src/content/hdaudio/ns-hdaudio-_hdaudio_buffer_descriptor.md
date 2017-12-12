---
UID: NS.HDAUDIO._HDAUDIO_BUFFER_DESCRIPTOR
title: _HDAUDIO_BUFFER_DESCRIPTOR
author: windows-driver-content
description: The HDAUDIO_BUFFER_DESCRIPTOR structure specifies a buffer descriptor, which is an entry in a buffer descriptor list (BDL).
old-location: audio\hdaudio_buffer_descriptor.htm
old-project: audio
ms.assetid: da07d3c2-0bd5-4e61-87b3-6fda8007cf5f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _HDAUDIO_BUFFER_DESCRIPTOR, *PHDAUDIO_BUFFER_DESCRIPTOR, HDAUDIO_BUFFER_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HDAUDIO_BUFFER_DESCRIPTOR
req.alt-loc: hdaudio.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL.
---

# _HDAUDIO_BUFFER_DESCRIPTOR structure



## -description
The HDAUDIO_BUFFER_DESCRIPTOR structure specifies a buffer descriptor, which is an entry in a buffer descriptor list (BDL).



## -syntax

````
typedef struct _HDAUDIO_BUFFER_DESCRIPTOR {
  PHYSICAL_ADDRESS Address;
  ULONG            Length;
  ULONG            InterruptOnCompletion;
} HDAUDIO_BUFFER_DESCRIPTOR, *PHDAUDIO_BUFFER_DESCRIPTOR;
````


## -struct-fields

### -field Address

Specifies the start address of a physically contiguous fragment of the buffer. In the case of a 32-bit address, the address should be right-justified and the 32 most significant bits (MSBs) of the member should be zero.


### -field Length

Specifies the size in bytes of the buffer fragment.


### -field InterruptOnCompletion

Specifies whether the DMA engine should generate an interrupt on completing the transfer of the buffer fragment. A value of 1 enables the interrupt. A value of 0 disables it.


## -remarks
A BDL is an array of HDAUDIO_BUFFER_DESCRIPTOR structures. Each structure specifies a physically contiguous fragment of the buffer. A BDL specifies all the fragments that make up the buffer.

The <b>Address</b> member contains the physical memory address of the start of the buffer fragment. The <b>Length</b> member specifies the number of bytes of physically contiguous memory that the fragment contains.

If the <b>InterruptOnCompletion</b> bit is set during a DMA transfer to or from the buffer fragment, the DMA engine generates an interrupt on completion of the transfer.

This structure is used by the <a href="..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md">AllocateContiguousDmaBuffer</a> and <a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a> routines.

For more information about BDLs, see the Intel High Definition Audio Specification at the <a href="http://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hdaudio.h (include Hdaudio.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md">AllocateContiguousDmaBuffer</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20HDAUDIO_BUFFER_DESCRIPTOR structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

