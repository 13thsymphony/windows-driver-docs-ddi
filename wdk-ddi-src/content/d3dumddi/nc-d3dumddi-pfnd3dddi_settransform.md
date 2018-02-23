---
UID: NC:d3dumddi.PFND3DDDI_SETTRANSFORM
title: PFND3DDDI_SETTRANSFORM
author: windows-driver-content
description: The SetTransform function sets up a transform.
old-location: display\settransform.htm
old-project: display
ms.assetid: 0e989ea4-3693-4c0b-86a5-96b865a0193f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.settransform, SetTransform callback function [Display Devices], SetTransform, PFND3DDDI_SETTRANSFORM, PFND3DDDI_SETTRANSFORM, d3dumddi/SetTransform, UserModeDisplayDriver_Functions_721be745-bcea-4eeb-9bd4-ddda1f1912a5.xml
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
-	SetTransform
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_SETTRANSFORM callback function
The <i>SetTransform</i> function sets up a transform.

## Syntax

```
PFND3DDDI_SETTRANSFORM Pfnd3dddiSettransform;

HRESULT Pfnd3dddiSettransform(
  HANDLE hDevice,
  CONST D3DDDIARG_SETTRANSFORM *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>SetTransform</i> returns S_OK or an appropriate error result if the transform is not successfully set up.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_settransform.md">D3DDDIARG_SETTRANSFORM</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETTRANSFORM callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>