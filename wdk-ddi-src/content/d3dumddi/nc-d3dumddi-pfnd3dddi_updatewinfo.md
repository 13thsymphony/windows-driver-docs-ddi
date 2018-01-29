---
UID : NC:d3dumddi.PFND3DDDI_UPDATEWINFO
title : PFND3DDDI_UPDATEWINFO
author : windows-driver-content
description : The UpdateWInfo function updates the w range for w buffering.
old-location : display\updatewinfo.htm
old-project : display
ms.assetid : e9cd87b9-3958-4b10-895d-480e03ebea76
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.updatewinfo, UpdateWInfo callback function [Display Devices], UpdateWInfo, PFND3DDDI_UPDATEWINFO, PFND3DDDI_UPDATEWINFO, d3dumddi/UpdateWInfo, UserModeDisplayDriver_Functions_c829f8ef-b1fd-49ef-a9f0-cf92232bdb4f.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DXGK_PTE
---


# PFND3DDDI_UPDATEWINFO callback function
The <i>UpdateWInfo</i> function updates the w range for w buffering.

## Syntax

```
PFND3DDDI_UPDATEWINFO Pfnd3dddiUpdatewinfo;

HRESULT Pfnd3dddiUpdatewinfo(
  HANDLE hDevice,
  CONST D3DDDIARG_WINFO *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>UpdateWInfo</i> returns S_OK or an appropriate error result if the w range is not successfully updated.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_winfo.md">D3DDDIARG_WINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_UPDATEWINFO callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>