---
UID: NE:d3dkmdt._DXGKMDT_OPM_CGMSA
title: "_DXGKMDT_OPM_CGMSA"
author: windows-driver-content
description: The DXGKMDT_OPM_CGMSA enumeration indicates the protection levels for a protected output that supports Content Generation Management System Analog (CGMS-A).
old-location: display\dxgkmdt_opm_cgmsa.htm
old-project: display
ms.assetid: 1318d00e-aac3-4ff2-89a2-bcabcdff6331
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKMDT_OPM_CGMSA, DXGKMDT_OPM_CGMSA enumeration [Display Devices], DXGKMDT_OPM_CGMSA_COPY_FREELY, DXGKMDT_OPM_CGMSA_COPY_NEVER, DXGKMDT_OPM_CGMSA_COPY_NO_MORE, DXGKMDT_OPM_CGMSA_COPY_ONE_GENERATION, DXGKMDT_OPM_CGMSA_OFF, DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED, DmEnums_94737355-e3ff-4e00-9dbe-9d954e462f54.xml, _DXGKMDT_OPM_CGMSA, d3dkmdt/DXGKMDT_OPM_CGMSA, d3dkmdt/DXGKMDT_OPM_CGMSA_COPY_FREELY, d3dkmdt/DXGKMDT_OPM_CGMSA_COPY_NEVER, d3dkmdt/DXGKMDT_OPM_CGMSA_COPY_NO_MORE, d3dkmdt/DXGKMDT_OPM_CGMSA_COPY_ONE_GENERATION, d3dkmdt/DXGKMDT_OPM_CGMSA_OFF, d3dkmdt/DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED, display.dxgkmdt_opm_cgmsa
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	DXGKMDT_OPM_CGMSA
product:
- Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_CGMSA
---

# _DXGKMDT_OPM_CGMSA Enumeration
The DXGKMDT_OPM_CGMSA enumeration indicates the protection levels for a protected output that supports Content Generation Management System Analog (CGMS-A).

## Syntax
```
typedef enum _DXGKMDT_OPM_CGMSA {
  DXGKMDT_OPM_CGMSA_OFF                        ,
  DXGKMDT_OPM_CGMSA_COPY_FREELY                ,
  DXGKMDT_OPM_CGMSA_COPY_NO_MORE               ,
  DXGKMDT_OPM_CGMSA_COPY_ONE_GENERATION        ,
  DXGKMDT_OPM_CGMSA_COPY_NEVER                 ,
  DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED
} DXGKMDT_OPM_CGMSA;
```

## Constants

<table>
            
                <tr>
                    <td>DXGKMDT_OPM_CGMSA_OFF</td>
                    <td>Indicates that a video output's signal is not protected with the CGMS-A output protection scheme.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_CGMSA_COPY_FREELY</td>
                    <td>Indicates that the signal from a physical video output can be copied an infinite number of times.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_CGMSA_COPY_NO_MORE</td>
                    <td>Indicates that the signal from a physical video output cannot be copied because the signal was already copied once.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_CGMSA_COPY_ONE_GENERATION</td>
                    <td>Indicates that the signal from a physical video output can be copied once. However, the copy can never be copied.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_CGMSA_COPY_NEVER</td>
                    <td>Indicates that the signal from a physical video output can never be copied.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED</td>
                    <td>Indicates that the technological control of consumer redistribution is enabled. 

The five preceding protection levels can be bitwise OR combined  with the DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED to turn on redistribution control. 

DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED corresponds to the CEA-805-A standard's Redistribution Control Information (RCI) bit. For more information about the RCI bit, see the definition of the RCI bit in section 4.4.3.8 in the CEA-805-A standard. For more information about this standard, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=71276">Consumer Electronics Association</a> website. 

DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED can be used only if a protected output has COPP semantics. A protected output must enable redistribution control if the DirectX graphics kernel subsystem passes DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED to the <a href="https://msdn.microsoft.com/a7829587-c1e7-43ec-a0bb-92bca94b7c3d">DxgkDdiOPMConfigureProtectedOutput</a> function. <i>DxgkDdiOPMConfigureProtectedOutput</i> must fail if DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED is passed to it and the display miniport driver cannot enable redistribution control for any reason.</td>
                </tr>
</table>

## Remarks

CGMS-A protects analog TV signals. Currently, OPM can use CGMS-A to protect signals from composite outputs, S-Video outputs, or component outputs. For more information about CGMS-A, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70568">CGMS-A article</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560921">DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560925">DXGKMDT_OPM_STANDARD_INFORMATION</a>



<a href="https://msdn.microsoft.com/a7829587-c1e7-43ec-a0bb-92bca94b7c3d">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="https://msdn.microsoft.com/9f15df1e-bdf5-4634-97f1-78515664b594">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a>