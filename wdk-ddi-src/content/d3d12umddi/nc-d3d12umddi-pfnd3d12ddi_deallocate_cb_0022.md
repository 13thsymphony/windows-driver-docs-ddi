---
UID: NC:d3d12umddi.PFND3D12DDI_DEALLOCATE_CB_0022
title: PFND3D12DDI_DEALLOCATE_CB_0022
author: windows-driver-content
description: The pfnDeallocateCb callback function controls heap deallocation by using a D3D12DDICB_DEALLOCATE_0022 structure.
old-location: display\pfnd3d12ddi_deallocate_cb_0022.htm
old-project: display
ms.assetid: 85304F27-A522-44B7-86EC-31F670828354
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnd3d12ddi_deallocate_cb_0022, pfnDeallocateCb callback function [Display Devices], pfnDeallocateCb, PFND3D12DDI_DEALLOCATE_CB_0022, PFND3D12DDI_DEALLOCATE_CB_0022, d3d12umddi/pfnDeallocateCb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d12umddi.h
apiname:
-	pfnDeallocateCb
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---


# PFND3D12DDI_DEALLOCATE_CB_0022 callback function
The <i>pfnDeallocateCb</i> callback function controls heap deallocation by using a <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddicb_deallocate_0022.md">D3D12DDICB_DEALLOCATE_0022</a> structure.

## Syntax

```
PFND3D12DDI_DEALLOCATE_CB_0022 Pfnd3d12ddiDeallocateCb0022;

HRESULT Pfnd3d12ddiDeallocateCb0022(
   D3D12DDI_HRTDEVICE,
  CONST D3D12DDICB_DEALLOCATE_0022 *
)
{...}
```

## Parameters

`D3D12DDI_HRTDEVICE`



`*`




## Return Value

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

Access this callback function by using the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_corelayer_devicecallbacks_0022.md">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a> structure.

The driver must check the return value of the function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_allocate_cb_0022.md">pfnAllocateCb</a>



<a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_allocate_cb_0022.md">pfnAllocateCb</a>



<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddicb_deallocate_0022.md">D3D12DDICB_DEALLOCATE_0022</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D12DDI_DEALLOCATE_CB_0022 callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>