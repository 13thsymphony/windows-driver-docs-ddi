---
UID: NS:d3dkmddi._DXGK_VIDPNTARGETMODESET_INTERFACE
title: "_DXGK_VIDPNTARGETMODESET_INTERFACE"
author: windows-driver-content
description: The DXGK_VIDPNTARGETMODESET_INTERFACE structure contains pointers to functions that belong to the VidPn Target Mode Set interface, which is implemented by the VidPN manager.
old-location: display\dxgk_vidpntargetmodeset_interface.htm
old-project: display
ms.assetid: 556d3134-942b-475c-adac-3087a512f481
ms.author: windowsdriverdev
ms.date: 3/29/2018
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
product:
- Windows
targetos: Windows
req.typenames: DXGK_VIDPNTARGETMODESET_INTERFACE
---

# _DXGK_VIDPNTARGETMODESET_INTERFACE structure
The DXGK_VIDPNTARGETMODESET_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570559">VidPn Target Mode Set interface</a>, which is implemented by the VidPN manager.

## Syntax
```
typedef struct _DXGK_VIDPNTARGETMODESET_INTERFACE {
  DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES           pfnGetNumModes;
  DXGKDDI_VIDPNTARGETMODESET_ACQUIREFIRSTMODEINFO  pfnAcquireFirstModeInfo;
  DXGKDDI_VIDPNTARGETMODESET_ACQUIRENEXTMODEINFO   pfnAcquireNextModeInfo;
  DXGKDDI_VIDPNTARGETMODESET_ACQUIREPINNEDMODEINFO pfnAcquirePinnedModeInfo;
  DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO       pfnReleaseModeInfo;
  DXGKDDI_VIDPNTARGETMODESET_CREATENEWMODEINFO     pfnCreateNewModeInfo;
  DXGKDDI_VIDPNTARGETMODESET_ADDMODE               pfnAddMode;
  DXGKDDI_VIDPNTARGETMODESET_PINMODE               pfnPinMode;
} DXGK_VIDPNTARGETMODESET_INTERFACE;
```

## Members


`pfnGetNumModes`

A pointer to the <a href="https://msdn.microsoft.com/1197989a-c76e-4dee-a1c7-677b6558677c">pfnGetNumModes</a> function.

`pfnAcquireFirstModeInfo`

A pointer to the <a href="https://msdn.microsoft.com/64a1a8f4-afbc-4337-b809-9346c1171e0b">pfnAcquireFirstModeInfo</a> function.

`pfnAcquireNextModeInfo`

A pointer to the <a href="https://msdn.microsoft.com/894d0d15-d12a-4138-9a92-8f930c12dd52">pfnAcquireNextModeInfo</a> function.

`pfnAcquirePinnedModeInfo`

A pointer to the <a href="https://msdn.microsoft.com/0a321ee2-f246-498d-b658-a01e275644be">pfnAcquirePinnedModeInfo</a> function.

`pfnReleaseModeInfo`

A pointer to the <a href="https://msdn.microsoft.com/0b1d0331-f0fa-40fc-a1d6-15fe3568f3cc">pfnReleaseModeInfo</a> function.

`pfnCreateNewModeInfo`

A pointer to the <a href="https://msdn.microsoft.com/ebb37681-fa03-49f5-968b-87c9ff4ebae9">pfnCreateNewModeInfo</a> function.

`pfnAddMode`

A pointer to the <a href="https://msdn.microsoft.com/96c14056-aa93-4164-8adf-31fa1b3d33d3">pfnAddMode</a> function.

`pfnPinMode`

A pointer to the <a href="https://msdn.microsoft.com/91ea3105-2fdf-4533-a2d4-d27f1e660056">pfnPinMode</a> function.

## Remarks
The display miniport driver calls the <a href="https://msdn.microsoft.com/1b91c472-21eb-4aa8-91e3-c9eb70556d9f">pfnAcquireTargetModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570556">VidPn interface</a> to obtain a handle to a VidPN target mode set object and a pointer to a DXGK_VIDPNTARGETMODESET_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the VidPN target mode set object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561921">DXGK_MONITORSOURCEMODESET_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562073">DXGK_VIDPNSOURCEMODESET_INTERFACE</a>



<a href="https://msdn.microsoft.com/1b91c472-21eb-4aa8-91e3-c9eb70556d9f">pfnAcquireTargetModeSet</a>