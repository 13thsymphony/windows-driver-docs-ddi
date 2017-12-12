---
UID: NE.umdprovider._UMDETW_ALLOCATION_SEMANTIC
title: _UMDETW_ALLOCATION_SEMANTIC
author: windows-driver-content
description: Indicates what a memory allocation is used for if the allocation is internal to the user-mode driver.
old-location: display\umdetw_allocation_semantic.htm
old-project: display
ms.assetid: 4c0fa5c1-7d73-4380-a673-f09bbf0ea281
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _UMDETW_ALLOCATION_SEMANTIC, UMDETW_ALLOCATION_SEMANTIC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: umdprovider.h
req.include-header: Umdprovider.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UMDETW_ALLOCATION_SEMANTIC
req.alt-loc: umdprovider.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# _UMDETW_ALLOCATION_SEMANTIC enumeration



## -description
Indicates what a memory allocation is used for if the allocation is internal to the user-mode driver.



## -syntax

````
typedef enum _UMDETW_ALLOCATION_SEMANTIC { 
  UMDETW_ALLOCATION_SEMANTIC_NONE              = 0,
  UMDETW_ALLOCATION_SEMANTIC_DMA_BUFFER        = 1,
  UMDETW_ALLOCATION_SEMANTIC_UPLOAD_STAGING    = 2,
  UMDETW_ALLOCATION_SEMANTIC_DOWNLOAD_STAGING  = 3,
  UMDETW_ALLOCATION_SEMANTIC_CONTEXT_SAVE      = 4,
  UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MIN  = 5,
  UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MAX  = 0xFFFF
} UMDETW_ALLOCATION_SEMANTIC;
````


## -enum-fields

### -field UMDETW_ALLOCATION_SEMANTIC_NONE

The allocation is created for a Direct3D resource.


### -field UMDETW_ALLOCATION_SEMANTIC_DMA_BUFFER

The allocation is used as a DMA buffer.


### -field UMDETW_ALLOCATION_SEMANTIC_UPLOAD_STAGING

The allocation is used as a staging allocation to upload and download data to and from video memory.


### -field UMDETW_ALLOCATION_SEMANTIC_DOWNLOAD_STAGING

The allocation is used exclusively as a staging allocation to download data from video memory.


### -field UMDETW_ALLOCATION_SEMANTIC_CONTEXT_SAVE

The allocation is used as a GPU context save area.


### -field UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MIN

The driver can use this semantic value for its own internal purposes.


### -field UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MAX

The driver can use this semantic value for its own internal purposes.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Umdprovider.h (include Umdprovider.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.umdetwlogmapallocation">UMDEtwLogMapAllocation</a>
</dt>
<dt>
<a href="display.umdetwlogunmapallocation">UMDEtwLogUnmapAllocation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20UMDETW_ALLOCATION_SEMANTIC enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

