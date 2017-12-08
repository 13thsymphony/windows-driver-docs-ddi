---
UID: NE.wdfmemory._WDF_MEMORY_DESCRIPTOR_TYPE
title: _WDF_MEMORY_DESCRIPTOR_TYPE
author: windows-driver-content
description: The WDF_MEMORY_DESCRIPTOR_TYPE enumeration identifies the types of memory descriptions that a WDF_MEMORY_DESCRIPTOR structure can specify.
old-location: wdf\wdf_memory_descriptor_type.htm
old-project: wdf
ms.assetid: ab364ad8-1b04-4ad0-a036-9b1c41e16604
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WDF_MEMORY_DESCRIPTOR_TYPE, WDF_MEMORY_DESCRIPTOR_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_MEMORY_DESCRIPTOR_TYPE
req.alt-loc: wdfmemory.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.product: Windows 10 or later.
---

# _WDF_MEMORY_DESCRIPTOR_TYPE enumeration



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WDF_MEMORY_DESCRIPTOR_TYPE</b> enumeration identifies the types of memory descriptions that a <a href="wdf.wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure can specify.


## -syntax

````
typedef enum _WDF_MEMORY_DESCRIPTOR_TYPE { 
  WdfMemoryDescriptorTypeInvalid  = 0,
  WdfMemoryDescriptorTypeBuffer   = 1,
  WdfMemoryDescriptorTypeMdl      = 2,
  WdfMemoryDescriptorTypeHandle   = 3
} WDF_MEMORY_DESCRIPTOR_TYPE;
````


## -enum-fields

### -field WdfMemoryDescriptorTypeInvalid

Reserved for internal use only.

### -field WdfMemoryDescriptorTypeBuffer

The <a href="wdf.wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure contains a buffer description.

### -field WdfMemoryDescriptorTypeMdl

The <a href="wdf.wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure contains a memory descriptor list (MDL).

### -field WdfMemoryDescriptorTypeHandle

The <a href="wdf.wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure contains a handle to a memory object.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfmemory.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_MEMORY_DESCRIPTOR_TYPE enumeration%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
