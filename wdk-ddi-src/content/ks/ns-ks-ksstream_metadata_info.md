---
UID: NS.KS.KSSTREAM_METADATA_INFO
title: KSSTREAM_METADATA_INFO
author: windows-driver-content
description: This structure contains the metadata information that is passed down to the driver.
old-location: stream\ksstream_metadata_info.htm
old-project: stream
ms.assetid: 40C09BCD-407F-4F2D-8780-4DEC1C9246E8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KSSTREAM_METADATA_INFO, KSSTREAM_METADATA_INFO, *PKSSTREAM_METADATA_INFO, PKSSTREAM_METADATA_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSSTREAM_METADATA_INFO
req.alt-loc: Ks.h
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
---

# KSSTREAM_METADATA_INFO structure



## -description
This structure contains the metadata information that is passed down to the driver.



## -syntax

````
typedef struct {
  ULONG                               BufferSize;
  ULONG                               UsedSize;
  Field_size_bytes_(BufferSize) PVOID Data;
  Field_size_bytes_(BufferSize) PVOID SystemVa;
  ULONG                               Flags;
  ULONG                               Reserved;
} KSSTREAM_METADATA_INFO, *PKSSTREAM_METADATA_INFO;
````


## -struct-fields

### -field BufferSize

This value is set by the user mode component and is equal to the MaxMetadataBufferSize supplied by the driver.


### -field UsedSize

The size of the metadata written by the driver in the SystemVa buffer.


### -field Data

The metadata buffer that is passed down by the user mode component. This is mapped to <i>SystemVa</i>.


### -field SystemVa

The buffer that is used by the driver to fill with metadata.


### -field Flags

Set to KSCAMERA_EXTENDEDPROP_METADATA_SYSTEMMEMORY if the metadata buffer is allocated from the system memory.


### -field Reserved

Reserved for system use.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h</dt>
</dl>
</td>
</tr>
</table>