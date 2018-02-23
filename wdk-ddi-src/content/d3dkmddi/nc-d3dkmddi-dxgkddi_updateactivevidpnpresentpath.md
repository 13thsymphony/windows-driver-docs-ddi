---
UID: NC:d3dkmddi.DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH
title: DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH
author: windows-driver-content
description: The DxgkDdiUpdateActiveVidPnPresentPath function updates one of the video present paths that is currently active on the display adapter.
old-location: display\dxgkddiupdateactivevidpnpresentpath.htm
old-project: display
ms.assetid: 3bf5ebf7-8113-4ab2-beb1-1a52df25ac37
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgkddiupdateactivevidpnpresentpath, DxgkDdiUpdateActiveVidPnPresentPath callback function [Display Devices], DxgkDdiUpdateActiveVidPnPresentPath, DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH, DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH, d3dkmddi/DxgkDdiUpdateActiveVidPnPresentPath, DmFunctions_837597a1-a23e-4aa9-b219-b1f69eb58ed1.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DxgkDdiUpdateActiveVidPnPresentPath
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH function
The <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function updates one of the video present paths that is currently active on the display adapter.

## Syntax

```
DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH DxgkddiUpdateactivevidpnpresentpath;

NTSTATUS DxgkddiUpdateactivevidpnpresentpath(
  IN_CONST_HANDLE hAdapter,
  IN_CONST_PDXGKARG_UPDATEACTIVEVIDPNPRESENTPATH_CONST pUpdateActiveVidPnPresentPath
)
{...}
```

## Parameters

`hAdapter`

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

`pUpdateActiveVidPnPresentPath`




## Return Value

<i>DxgkDdiUpdateActiveVidPnPresentPath</i>returns one of the following values:

## Remarks

The operating system calls the <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function to control the settings of video present paths, such as path rotation, a presented content's geometry transformations, gamma ramps that are used to adjust the presented content's brightness, and so on.

<div class="alert"><b>Note</b>    The display miniport driver's <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function must support gamma ramps.</div>
<div> </div>
Beginning with Windows 8, if the display miniport driver sets the <b>SupportSmoothRotation</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure, it must support updating the path rotation on the adapter using the <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function. The driver must always be able to set the path rotation during a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a> function.

The <i>DxgkDdiUpdateActiveVidPnPresentPath</i> function should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>






<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_updateactivevidpnpresentpath.md">DXGKARG_UPDATEACTIVEVIDPNPRESENTPATH</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>