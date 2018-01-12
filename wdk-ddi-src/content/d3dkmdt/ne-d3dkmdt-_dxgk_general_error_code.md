---
UID: NE:d3dkmdt._DXGK_GENERAL_ERROR_CODE
title: _DXGK_GENERAL_ERROR_CODE
author: windows-driver-content
description: The DXGK_GENERAL_ERROR_CODE enumeration specifies a set of predefined graphics processing unit (GPU) errors reported via a page fault interrupt.
old-location: display\dxgk_general_error_code.htm
old-project: display
ms.assetid: 678998C5-DC3B-471D-ADBF-876EFB53D227
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_GENERAL_ERROR_CODE, DXGK_GENERAL_ERROR_CODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_GENERAL_ERROR_CODE
req.alt-loc: D3dkmdt.h
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
req.typenames: DXGK_GENERAL_ERROR_CODE
---

# _DXGK_GENERAL_ERROR_CODE enumeration



## -description
The <b>DXGK_GENERAL_ERROR_CODE</b> enumeration specifies a set of predefined graphics processing unit (GPU) errors reported via a page fault interrupt.



## -syntax

````
typedef enum _DXGK_GENERAL_ERROR_CODE { 
  DXGK_GENERAL_ERROR_PAGE_FAULT           = 0,
  DXGK_GENERAL_ERROR_INVALID_INSTRUCTION  = 1
} DXGK_GENERAL_ERROR_CODE;
````


## -enum-fields

### -field DXGK_GENERAL_ERROR_PAGE_FAULT

Indicates that the GPU encountered a page fault. The <b>FaultedVirtualAddress</b> and <b>PageTableLevel</b> members of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure should be used to provide further information about the GPU virtual address operation that caused the fault.


### -field DXGK_GENERAL_ERROR_INVALID_INSTRUCTION

Indicates that the GPU encountered an invalid instruction in the DMA command buffer.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmdt.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_GENERAL_ERROR_CODE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

