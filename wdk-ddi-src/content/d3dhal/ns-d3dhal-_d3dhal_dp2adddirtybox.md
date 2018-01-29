---
UID : NS:d3dhal._D3DHAL_DP2ADDDIRTYBOX
title : _D3DHAL_DP2ADDDIRTYBOX
author : windows-driver-content
description : DirectX 8.1 and later versions only. D3DHAL_DP2ADDDIRTYBOX is used to specify that a portion of a 3D resource--a volume texture--was dirtied in system memory. Therefore, this volume must be reloaded into video memory before being used.
old-location : display\d3dhal_dp2adddirtybox.htm
old-project : display
ms.assetid : 9cb74a6f-64ae-449a-a1de-6b05419e3387
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3dhal/LPD3DHAL_DP2ADDDIRTYBOX, _D3DHAL_DP2ADDDIRTYBOX, LPD3DHAL_DP2ADDDIRTYBOX, d3dstrct_ae7da3ce-63e0-4854-ad22-12b2669baba2.xml, d3dhal/D3DHAL_DP2ADDDIRTYBOX, LPD3DHAL_DP2ADDDIRTYBOX structure pointer [Display Devices], display.d3dhal_dp2adddirtybox, *LPD3DHAL_DP2ADDDIRTYBOX, D3DHAL_DP2ADDDIRTYBOX, D3DHAL_DP2ADDDIRTYBOX structure [Display Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dhal.h
req.include-header : D3dhal.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.typenames : D3DHAL_DP2ADDDIRTYBOX
---

# _D3DHAL_DP2ADDDIRTYBOX structure
DirectX 8.1 and later versions only.
   

D3DHAL_DP2ADDDIRTYBOX is used to specify that a portion of a 3D resource--a volume texture--was dirtied in system memory. Therefore, this volume must be reloaded into video memory before being used.

## Syntax
````
typedef struct _D3DHAL_DP2ADDDIRTYBOX {
  DWORD  dwSurface;
  D3DBOX DirtyBox;
} D3DHAL_DP2ADDDIRTYBOX, *LPD3DHAL_DP2ADDDIRTYBOX;
````

## Members


`DirtyBox`

Specifies the volume texture that was marked as dirtied. This is a D3DBOX structure, which is described in the Microsoft Windows SDK documentation.

`dwSurface`

Specifies the handle to the managed 3D resource that contains a dirtied volume texture.

## Remarks
D3DHAL_DP2ADDDIRTYBOX, along with the DP2OP_ADDDIRTYBOX token, is used only for driver managed resources. D3DHAL_DP2ADDDIRTYBOX is never sent unless the driver indicates that it manages resources. To indicate that it manages resources, the driver must set the DDCAPS2_CANMANAGERESOURCE bit, in addition to the DDCAPS2_CANMANAGETEXTURE bit, in the <b>dwCaps2</b> member of a DDCORECAPS structure. The driver specifies this <a href="https://msdn.microsoft.com/library/windows/hardware/ff549248">DDCORECAPS</a> structure in the <b>ddCaps</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551627">DD_HALINFO</a> structure when the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556229">DrvGetDirectDrawInfo</a> function is called to initialize the DirectDraw component of the driver.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dhal.h (include D3dhal.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556229">DrvGetDirectDrawInfo</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549248">DDCORECAPS</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551627">DD_HALINFO</a>

<a href="..\d3dhal\ne-d3dhal-_d3dhal_dp2operation.md">D3DHAL_DP2OPERATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2ADDDIRTYBOX structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>