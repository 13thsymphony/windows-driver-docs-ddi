---
UID: NS.KS._MF_MDL_SHARED_PAYLOAD_KEY
title: _MF_MDL_SHARED_PAYLOAD_KEY
author: windows-driver-content
description: This union is used internally by the operating system.
old-location: stream\mf_mdl_shared_payload_key.htm
old-project: stream
ms.assetid: 3EA093AB-1D23-4744-997E-8C7072934628
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _MF_MDL_SHARED_PAYLOAD_KEY, *PMF_MDL_SHARED_PAYLOAD_KEY, MF_MDL_SHARED_PAYLOAD_KEY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MF_MDL_SHARED_PAYLOAD_KEY
req.alt-loc: ks.h
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

# _MF_MDL_SHARED_PAYLOAD_KEY structure



## -description
This union is used internally by the operating system.


## -syntax

````
typedef union _MF_MDL_SHARED_PAYLOAD_KEY {
  struct {
    ULONG   pHandle;
    ULONG   fHandle;
    ULONG64 uPayload;
  } combined;
  GUID   GMDLHandle;
} MF_MDL_SHARED_PAYLOAD_KEY, PMF_MDL_SHARED_PAYLOAD_KEY;
````


## -struct-fields

### -field combined

This member is used internally by the operating system.

### -field pHandle

This member is used internally by the operating system.

### -field fHandle

This member is used internally by the operating system.

### -field uPayload

This member is used internally by the operating system.
</dd>
</dl>

### -field GMDLHandle

This structure is used internally by the operating system.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>