---
UID: NS:d3dkmddi._DXGK_VIDPNTARGETMODESET_INTERFACE
title: "_DXGK_VIDPNTARGETMODESET_INTERFACE"
author: windows-driver-content
description: The DXGK_VIDPNTARGETMODESET_INTERFACE structure contains pointers to functions that belong to the VidPn Target Mode Set interface, which is implemented by the VidPN manager.
old-location: display\dxgk_vidpntargetmodeset_interface.htm
old-project: display
ms.assetid: 556d3134-942b-475c-adac-3087a512f481
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_VIDPNTARGETMODESET_INTERFACE, DXGK_VIDPNTARGETMODESET_INTERFACE structure [Display Devices], DmStructs_f73ff16c-04e3-491b-9f0a-de50563abea4.xml, _DXGK_VIDPNTARGETMODESET_INTERFACE, d3dkmddi/DXGK_VIDPNTARGETMODESET_INTERFACE, display.dxgk_vidpntargetmodeset_interface
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
-	DXGK_VIDPNTARGETMODESET_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_VIDPNTARGETMODESET_INTERFACE
---

# _DXGK_VIDPNTARGETMODESET_INTERFACE structure
The DXGK_VIDPNTARGETMODESET_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570559">VidPn Target Mode Set interface</a>, which is implemented by the VidPN manager.

## Syntax
````
typedef struct _DXGK_VIDPNTARGETMODESET_INTERFACE {
  DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES           pfnGetNumModes;
  DXGKDDI_VIDPNTARGETMODESET_ACQUIREFIRSTMODEINFO  pfnAcquireFirstModeInfo;
  DXGKDDI_VIDPNTARGETMODESET_ACQUIRENEXTMODEINFO   pfnAcquireNextModeInfo;
  DXGKDDI_VIDPNTARGETMODESET_ACQUIREPINNEDMODEINFO pfnAcquirePinnedModeInfo;
  DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO       pfnReleaseModeInfo;
  DXGKDDI_VIDPNTARGETMODESET_CREATENEWMODEINFO     pfnCreateNewModeInfo;
  DXGKDDI_VIDPNTARGETMODESET_ADDMODE               pfnAddMode;
  DXGKDDI_VIDPNTARGETMODESET_PINMODE               pfnPinMode;
} DXGK_VIDPNTARGETMODESET_INTERFACE;
````

## Members


`pfnGetNumModes`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_getnummodes.md">pfnGetNumModes</a> function.

`pfnAcquireFirstModeInfo`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirefirstmodeinfo.md">pfnAcquireFirstModeInfo</a> function.

`pfnAcquireNextModeInfo`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirenextmodeinfo.md">pfnAcquireNextModeInfo</a> function.

`pfnAcquirePinnedModeInfo`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirepinnedmodeinfo.md">pfnAcquirePinnedModeInfo</a> function.

`pfnReleaseModeInfo`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_releasemodeinfo.md">pfnReleaseModeInfo</a> function.

`pfnCreateNewModeInfo`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a> function.

`pfnAddMode`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_addmode.md">pfnAddMode</a> function.

`pfnPinMode`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_pinmode.md">pfnPinMode</a> function.

## Remarks
The display miniport driver calls the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset.md">pfnAcquireTargetModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570556">VidPn interface</a> to obtain a handle to a VidPN target mode set object and a pointer to a DXGK_VIDPNTARGETMODESET_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the VidPN target mode set object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitorsourcemodeset_interface.md">DXGK_MONITORSOURCEMODESET_INTERFACE</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset.md">pfnAcquireTargetModeSet</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpnsourcemodeset_interface.md">DXGK_VIDPNSOURCEMODESET_INTERFACE</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_target_mode.md">D3DKMDT_VIDPN_TARGET_MODE</a>