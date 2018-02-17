---
UID: NS:d3dkmddi._DXGKARGCB_GETCAPTUREADDRESS
title: "_DXGKARGCB_GETCAPTUREADDRESS"
author: windows-driver-content
description: The DXGKARGCB_GETCAPTUREADDRESS structure describes parameters for retrieving information about a capture buffer that is associated with an allocation.
old-location: display\dxgkargcb_getcaptureaddress.htm
old-project: display
ms.assetid: 95f1bbf4-06d8-48b7-a983-bf0b65ec2da3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKARGCB_GETCAPTUREADDRESS structure [Display Devices], DmStructs_24ed27a0-7ad3-44d1-aa93-c22733ebfb34.xml, _DXGKARGCB_GETCAPTUREADDRESS, *INOUT_PDXGKARGCB_GETCAPTUREADDRESS, display.dxgkargcb_getcaptureaddress, d3dkmddi/DXGKARGCB_GETCAPTUREADDRESS, DXGKARGCB_GETCAPTUREADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARGCB_GETCAPTUREADDRESS
product: Windows
targetos: Windows
req.typenames: DXGKARGCB_GETCAPTUREADDRESS
---

# _DXGKARGCB_GETCAPTUREADDRESS structure
The DXGKARGCB_GETCAPTUREADDRESS structure describes parameters for retrieving information about a capture buffer that is associated with an allocation.

## Syntax
````
typedef struct _DXGKARGCB_GETCAPTUREADDRESS {
  D3DKMT_HANDLE    hAllocation;
  UINT             SegmentId;
  PHYSICAL_ADDRESS PhysicalAddress;
} DXGKARGCB_GETCAPTUREADDRESS;
````

## Members


`hAllocation`

[in] A handle to the allocation that is associated with the capture buffer to retrieve information on.

`PhysicalAddress`

[out] The physical address of the capture buffer.

`SegmentId`

[out] The identifier of the segment for the capture buffer. The allocation that is associated with the capture buffer is currently paged in this segment.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_getcaptureaddress.md">DxgkCbGetCaptureAddress</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARGCB_GETCAPTUREADDRESS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>