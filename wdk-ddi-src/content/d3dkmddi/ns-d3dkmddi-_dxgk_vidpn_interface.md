---
UID: NS:d3dkmddi._DXGK_VIDPN_INTERFACE
title: "_DXGK_VIDPN_INTERFACE"
author: windows-driver-content
description: The DXGK_VIDPN_INTERFACE structure contains pointers to functions that belong to the VidPn interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_vidpn_interface.htm
old-project: display
ms.assetid: 7ddd110c-2521-4df6-a936-e702a0f15312
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_VIDPN_INTERFACE, DXGK_VIDPN_INTERFACE structure [Display Devices], DmStructs_0fb940db-3ede-4eac-938b-89e34a9b337d.xml, _DXGK_VIDPN_INTERFACE, d3dkmddi/DXGK_VIDPN_INTERFACE, display.dxgk_vidpn_interface
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
-	DXGK_VIDPN_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_VIDPN_INTERFACE
---

# _DXGK_VIDPN_INTERFACE structure
The DXGK_VIDPN_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570556">VidPn interface</a>, which is implemented by the video present network (VidPN) manager.

## Syntax
```
typedef struct _DXGK_VIDPN_INTERFACE {
  DXGK_VIDPN_INTERFACE_VERSION               Version;
  DXGKDDI_VIDPN_GETTOPOLOGY                  pfnGetTopology;
  DXGKDDI_VIDPN_ACQUIRESOURCEMODESET         pfnAcquireSourceModeSet;
  DXGKDDI_VIDPN_RELEASESOURCEMODESET         pfnReleaseSourceModeSet;
  DXGKDDI_VIDPN_CREATENEWSOURCEMODESET       pfnCreateNewSourceModeSet;
  DXGKDDI_VIDPN_ASSIGNSOURCEMODESET          pfnAssignSourceModeSet;
  DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET pfnAssignMultisamplingMethodSet;
  DXGKDDI_VIDPN_ACQUIRETARGETMODESET         pfnAcquireTargetModeSet;
  DXGKDDI_VIDPN_RELEASETARGETMODESET         pfnReleaseTargetModeSet;
  DXGKDDI_VIDPN_CREATENEWTARGETMODESET       pfnCreateNewTargetModeSet;
  DXGKDDI_VIDPN_ASSIGNTARGETMODESET          pfnAssignTargetModeSet;
} DXGK_VIDPN_INTERFACE;
```

## Members


`Version`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562860">DXGK_VIDPN_INTERFACE_VERSION</a> enumerator that specifies the version of the interface.

`pfnGetTopology`

A pointer to the <a href="https://msdn.microsoft.com/2bc43cd0-97a2-4120-8e6f-425664d3d28c">pfnGetTopology</a> function.

`pfnAcquireSourceModeSet`

A pointer to the <a href="https://msdn.microsoft.com/cf19f468-86c1-4cc9-8945-e23f73a85c91">pfnAcquireSourceModeSet</a> function.

`pfnReleaseSourceModeSet`

A pointer to the <a href="https://msdn.microsoft.com/f1ee8761-f36e-4a39-a78e-95975442f7d3">pfnReleaseSourceModeSet</a> function.

`pfnCreateNewSourceModeSet`

A pointer to the <a href="https://msdn.microsoft.com/d46ffa49-6e75-4cd4-9d14-aa2c9fa671be">pfnCreateNewSourceModeSet</a> function.

`pfnAssignSourceModeSet`

A pointer to the <a href="https://msdn.microsoft.com/e1a2ca9e-9035-4656-bcb8-4ad956a8501d">pfnAssignSourceModeSet</a> function.

`pfnAssignMultisamplingMethodSet`

A pointer to the <a href="https://msdn.microsoft.com/607e3294-7399-446c-b07c-f0d5416b997e">pfnAssignMultisamplingMethodSet</a> function.

`pfnAcquireTargetModeSet`

A pointer to the <a href="https://msdn.microsoft.com/1b91c472-21eb-4aa8-91e3-c9eb70556d9f">pfnAcquireTargetModeSet</a> function.

`pfnReleaseTargetModeSet`

A pointer to the <a href="https://msdn.microsoft.com/bd369651-57d4-406f-ba51-9632362de15d">pfnReleaseTargetModeSet</a> function.

`pfnCreateNewTargetModeSet`

A pointer to the <a href="https://msdn.microsoft.com/c52935b4-306f-4200-80d9-0cfab6998450">pfnCreateNewTargetModeSet</a> function.

`pfnAssignTargetModeSet`

A pointer to the <a href="https://msdn.microsoft.com/846c6dd5-d4f8-4835-83a2-994725deaf36">pfnAssignTargetModeSet</a> function.

## Remarks
The display miniport driver calls <a href="https://msdn.microsoft.com/649ce7fc-6852-43f3-b944-b2b64fcba874">DxgkCbQueryVidPnInterface</a> to obtain a pointer to a DXGK_VIDPN_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter a VidPN object.

For more information about the VidPN interface, see <a href="https://msdn.microsoft.com/5dedac8c-9a99-4b3a-81be-39819135cd97">VidPN Objects and Interfaces</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |