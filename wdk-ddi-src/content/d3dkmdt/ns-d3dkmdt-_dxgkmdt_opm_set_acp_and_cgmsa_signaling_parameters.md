---
UID: NS:d3dkmdt._DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS
title: "_DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS"
author: windows-driver-content
description: The DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure contains parameters to set Analog Content Protection (ACP) and Content Generation Management System Analog (CGMS-A) signaling for a protected output.
old-location: display\dxgkmdt_opm_set_acp_and_cgmsa_signaling_parameters.htm
old-project: display
ms.assetid: e4151e72-e0a6-4873-a2e8-c3321941cfd4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS, DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure [Display Devices], DmStructs_64a3857d-3c66-4653-980b-72df307eba0f.xml, _DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS, d3dkmdt/DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS, display.dxgkmdt_opm_set_acp_and_cgmsa_signaling_parameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS
---

# _DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure
The DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure contains parameters to set Analog Content Protection (ACP) and Content Generation Management System Analog (CGMS-A) signaling for a protected output.

## Syntax
````
typedef struct _DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS {
  ULONG ulNewTVProtectionStandard;
  ULONG ulAspectRatioChangeMask1;
  ULONG ulAspectRatioData1;
  ULONG ulAspectRatioChangeMask2;
  ULONG ulAspectRatioData2;
  ULONG ulAspectRatioChangeMask3;
  ULONG ulAspectRatioData3;
  ULONG ulReserved[4];
  ULONG ulReserved2[4];
  ULONG ulReserved3;
} DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS;
````

## Members


`ulNewTVProtectionStandard`

A <a href="..\d3dkmdt\ne-d3dkmdt-_dxgkmdt_opm_protection_standard.md">DXGKMDT_OPM_PROTECTION_STANDARD</a>-typed value that indicates the type of television signal to set ACP and CGMS-A signaling for on the protected output.

`ulAspectRatioChangeMask1`

A mask value that indicates the valid bits to change in the following <b>ulAspectRatioData1</b> member.

`ulAspectRatioData1`

32-bit data that indicates the aspect ratio value to set for the active protection standard.

`ulAspectRatioChangeMask2`

A mask value that indicates the valid bits to change in the following <b>ulAspectRatioData2</b> member.

`ulAspectRatioData2`

32-bit data for additional aspect ratio-related data for specific protection standards. This data can be used to express End and Q0 values for EIA-608-B, or active format description for CEA-805-A Type B packets.

`ulAspectRatioChangeMask3`

A mask value that indicates the valid bits to change in the following <b>ulAspectRatioData3</b> member.

`ulAspectRatioData3`

32-bit data for additional aspect ratio-related data for specific protection standards. This data can be used to express End and Q0 values for EIA-608-B, or active format description for CEA-805-A Type B packets.

`ulReserved`

Reserved. Must be set to zero.

`ulReserved2`

Reserved. Must be set to zero.

`ulReserved3`

Reserved. Must be set to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<a href="..\d3dkmdt\ne-d3dkmdt-_dxgkmdt_opm_protection_standard.md">DXGKMDT_OPM_PROTECTION_STANDARD</a>