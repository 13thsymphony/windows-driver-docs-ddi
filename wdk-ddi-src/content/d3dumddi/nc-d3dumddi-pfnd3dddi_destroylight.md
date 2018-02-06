---
UID: NC:d3dumddi.PFND3DDDI_DESTROYLIGHT
title: PFND3DDDI_DESTROYLIGHT
author: windows-driver-content
description: The DestroyLight function deactivates a light source.
old-location: display\destroylight.htm
old-project: display
ms.assetid: dbc86e4d-a002-4270-a3c4-02d16972c921
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.destroylight, DestroyLight callback function [Display Devices], DestroyLight, PFND3DDDI_DESTROYLIGHT, PFND3DDDI_DESTROYLIGHT, d3dumddi/DestroyLight, UserModeDisplayDriver_Functions_fce83d93-bfe6-44f9-a1c4-ea92921bfb69.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	DestroyLight
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DESTROYLIGHT callback function
The <b>DestroyLight</b> function deactivates a light source.

## Syntax

```
PFND3DDDI_DESTROYLIGHT Pfnd3dddiDestroylight;

HRESULT Pfnd3dddiDestroylight(
  HANDLE hDevice,
  CONST D3DDDIARG_DESTROYLIGHT *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<b>DestroyLight</b> returns S_OK or an appropriate error result if the light source is not successfully deactivated.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_destroylight.md">D3DDDIARG_DESTROYLIGHT</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYLIGHT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>