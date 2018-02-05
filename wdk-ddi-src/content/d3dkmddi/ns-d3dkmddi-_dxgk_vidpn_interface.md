---
UID : NS:d3dkmddi._DXGK_VIDPN_INTERFACE
title : "_DXGK_VIDPN_INTERFACE"
author : windows-driver-content
description : The DXGK_VIDPN_INTERFACE structure contains pointers to functions that belong to the VidPn interface, which is implemented by the video present network (VidPN) manager.
old-location : display\dxgk_vidpn_interface.htm
old-project : display
ms.assetid : 7ddd110c-2521-4df6-a936-e702a0f15312
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : "_DXGK_VIDPN_INTERFACE, DmStructs_0fb940db-3ede-4eac-938b-89e34a9b337d.xml, DXGK_VIDPN_INTERFACE, d3dkmddi/DXGK_VIDPN_INTERFACE, DXGK_VIDPN_INTERFACE structure [Display Devices], display.dxgk_vidpn_interface"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmddi.h
req.include-header : D3dkmddi.h
req.target-type : Windows
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DXGK_VIDPN_INTERFACE
---

# _DXGK_VIDPN_INTERFACE structure
The DXGK_VIDPN_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570556">VidPn interface</a>, which is implemented by the video present network (VidPN) manager.

## Syntax
````
typedef struct _DXGK_VIDPN_INTERFACE {
  DXGK_VIDPN_INTERFACE_VERSION               Version;
  DXGKDDI_VIDPN_GETTOPOLOGY                  pfnGetTopology;
  DXGKDDI_VIDPN_ACQUIRESOURCEMODESET         pfnAcquireSourceModeSet;
  DXGKDDI_VIDPN_RELEASESOURCEMODESET         pfnReleaseSourceModeSet;
  DXGKDDI_VIDPN_CREATENEWSOURCEMODESET       pfnCreateNewSourceModeSet;
  DXGKDDI_VIDPN_ASSIGNSOURCEMODESET          pfnAssignSourceModeSet;
  DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET pfnAssignMultisamplingMethodSet;
  DXGKDDI_VIDPN_ACQUIRETARGETMODESET         pfnAcquireTargetModeSet;
  DXGKDDI_VIDPN_RELEASETARGETMODESET         pfnReleaseTargetModeSet;
  DXGKDDI_VIDPN_CREATENEWTARGETMODESET       pfnCreateNewTargetModeSet;
  DXGKDDI_VIDPN_ASSIGNTARGETMODESET          pfnAssignTargetModeSet;
} DXGK_VIDPN_INTERFACE;
````

## Members


`pfnAcquireSourceModeSet`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset.md">pfnAcquireSourceModeSet</a> function.

`pfnAcquireTargetModeSet`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset.md">pfnAcquireTargetModeSet</a> function.

`pfnAssignMultisamplingMethodSet`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_assignmultisamplingmethodset.md">pfnAssignMultisamplingMethodSet</a> function.

`pfnAssignSourceModeSet`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_assignsourcemodeset.md">pfnAssignSourceModeSet</a> function.

`pfnAssignTargetModeSet`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_assigntargetmodeset.md">pfnAssignTargetModeSet</a> function.

`pfnCreateNewSourceModeSet`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_createnewsourcemodeset.md">pfnCreateNewSourceModeSet</a> function.

`pfnCreateNewTargetModeSet`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_createnewtargetmodeset.md">pfnCreateNewTargetModeSet</a> function.

`pfnGetTopology`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function.

`pfnReleaseSourceModeSet`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_releasesourcemodeset.md">pfnReleaseSourceModeSet</a> function.

`pfnReleaseTargetModeSet`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_releasetargetmodeset.md">pfnReleaseTargetModeSet</a> function.

`Version`

A <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_vidpn_interface_version.md">DXGK_VIDPN_INTERFACE_VERSION</a> enumerator that specifies the version of the interface.

## Remarks
The display miniport driver calls <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_queryvidpninterface.md">DxgkCbQueryVidPnInterface</a> to obtain a pointer to a DXGK_VIDPN_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter a VidPN object.

For more information about the VidPN interface, see <a href="https://msdn.microsoft.com/5dedac8c-9a99-4b3a-81be-39819135cd97">VidPN Objects and Interfaces</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |