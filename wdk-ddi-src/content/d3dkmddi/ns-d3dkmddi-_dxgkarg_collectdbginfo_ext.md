---
UID: NS:d3dkmddi._DXGKARG_COLLECTDBGINFO_EXT
title: "_DXGKARG_COLLECTDBGINFO_EXT"
author: windows-driver-content
description: The DXGKARG_COLLECTDBGINFO_EXT structure describes extension information for a debug report.
old-location: display\dxgkarg_collectdbginfo_ext.htm
old-project: display
ms.assetid: cbde31fe-06c1-44af-8940-b66e8044a5cd
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKARG_COLLECTDBGINFO_EXT, DXGKARG_COLLECTDBGINFO_EXT structure [Display Devices], DmStructs_3c280734-d3c8-4970-a6d8-8ad2b3dce913.xml, _DXGKARG_COLLECTDBGINFO_EXT, d3dkmddi/DXGKARG_COLLECTDBGINFO_EXT, display.dxgkarg_collectdbginfo_ext
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_COLLECTDBGINFO_EXT
product: Windows
targetos: Windows
req.typenames: DXGKARG_COLLECTDBGINFO_EXT
---

# _DXGKARG_COLLECTDBGINFO_EXT structure
The DXGKARG_COLLECTDBGINFO_EXT structure describes extension information for a debug report.

## Syntax
````
typedef struct _DXGKARG_COLLECTDBGINFO_EXT {
  UINT BucketingKey;
  UINT CurrentDmaBufferOffset;
  UINT Reserved2;
  UINT Reserved3;
  UINT Reserved4;
  UINT Reserved5;
  UINT Reserved6;
  UINT Reserved7;
} DXGKARG_COLLECTDBGINFO_EXT;
````

## Members


`BucketingKey`

[out] The optional integer key for Microsoft Online Crash Analysis (OCA) bucketing (that is, the categorizing of minidumps).

`CurrentDmaBufferOffset`

[out] The optional execution offset into the current DMA buffer. The operating system uses the offset to optimize DMA data collection.

`Reserved2`

Reserved for future use.

`Reserved3`

Reserved for future use.

`Reserved4`

Reserved for future use.

`Reserved5`

Reserved for future use.

`Reserved6`

Reserved for future use.

`Reserved7`

Reserved for future use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_collectdbginfo.md">DXGKARG_COLLECTDBGINFO</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_collectdbginfo.md">DxgkDdiCollectDbgInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_COLLECTDBGINFO_EXT structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>