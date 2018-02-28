---
UID: NS:d3dkmddi._DXGKARG_RECOMMENDFUNCTIONALVIDPN
title: "_DXGKARG_RECOMMENDFUNCTIONALVIDPN"
author: windows-driver-content
description: The DXGKARG_RECOMMENDFUNCTIONALVIDPN structure contains arguments for the DxgkDdiRecommendFunctionalVidPn function.
old-location: display\dxgkarg_recommendfunctionalvidpn.htm
old-project: display
ms.assetid: 58031257-5363-4e4f-b95f-aa3cd603c113
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKARG_RECOMMENDFUNCTIONALVIDPN, DXGKARG_RECOMMENDFUNCTIONALVIDPN structure [Display Devices], DmStructs_15342273-6bfe-4cee-8f8e-1d89c7683e4b.xml, _DXGKARG_RECOMMENDFUNCTIONALVIDPN, d3dkmddi/DXGKARG_RECOMMENDFUNCTIONALVIDPN, display.dxgkarg_recommendfunctionalvidpn
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
-	DXGKARG_RECOMMENDFUNCTIONALVIDPN
product: Windows
targetos: Windows
req.typenames: DXGKARG_RECOMMENDFUNCTIONALVIDPN
---

# _DXGKARG_RECOMMENDFUNCTIONALVIDPN structure
The DXGKARG_RECOMMENDFUNCTIONALVIDPN structure contains arguments for the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a> function. The <i>DxgkDdiRecommendFunctionalVidPn</i> function creates a functional video present network (VidPN) that can be implemented on a specified display adapter.

## Syntax
````
typedef struct _DXGKARG_RECOMMENDFUNCTIONALVIDPN {
  UINT                                 NumberOfVidPnTargets;
  const D3DDDI_VIDEO_PRESENT_TARGET_ID *pVidPnTargetPrioritizationVector;
  D3DKMDT_HVIDPN                       hRecommendedFunctionalVidPn;
  DXGK_RECOMMENDFUNCTIONALVIDPN_REASON RequestReason;
  OPTIONAL VOID                        *pPrivateDriverData;
  UINT                                 PrivateDriverDataSize;
} DXGKARG_RECOMMENDFUNCTIONALVIDPN;
````

## Members


`hRecommendedFunctionalVidPn`

A handle, provided by the caller, to an empty VidPN object. <i>DxgkDdiRecommendFunctionalVidPn</i> must add a path (source-target pair) to the VidPN's topology and must pin modes on the path's source and target. For information about adding paths to a topology and creating mode sets for video present sources and targets, see <a href="https://msdn.microsoft.com/5dedac8c-9a99-4b3a-81be-39819135cd97">VidPN Objects and Interfaces</a>.

`NumberOfVidPnTargets`

Reserved for future use.

`pPrivateDriverData`

A pointer to a buffer that contains private data that is passed from a user-mode application to the display miniport driver.

`PrivateDriverDataSize`

The size, in bytes, of the data block pointed to by <i>pPrivateDriverData</i>.

`pVidPnTargetPrioritizationVector`

Reserved for future use.

`RequestReason`

A <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_recommendfunctionalvidpn_reason.md">DXGK_RECOMMENDFUNCTIONALVIDPN_REASON</a> value that indicates why the caller is requesting a functional VidPN.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_RECOMMENDFUNCTIONALVIDPN structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>