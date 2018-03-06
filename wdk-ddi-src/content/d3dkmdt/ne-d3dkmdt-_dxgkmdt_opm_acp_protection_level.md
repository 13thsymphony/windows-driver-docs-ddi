---
UID: NE:d3dkmdt._DXGKMDT_OPM_ACP_PROTECTION_LEVEL
title: "_DXGKMDT_OPM_ACP_PROTECTION_LEVEL"
author: windows-driver-content
description: The DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports Analog Copy Protection (ACP).
old-location: display\dxgkmdt_opm_acp_protection_level.htm
old-project: display
ms.assetid: 9a7bceab-2bf7-4148-b62a-7d03f61aa9fa
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKMDT_OPM_ACP_FORCE_ULONG, DXGKMDT_OPM_ACP_LEVEL_ONE, DXGKMDT_OPM_ACP_LEVEL_THREE, DXGKMDT_OPM_ACP_LEVEL_TWO, DXGKMDT_OPM_ACP_OFF, DXGKMDT_OPM_ACP_PROTECTION_LEVEL, DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration [Display Devices], DmEnums_8ddb5546-7305-4b58-85e9-8e38a9bdf8af.xml, _DXGKMDT_OPM_ACP_PROTECTION_LEVEL, d3dkmdt/DXGKMDT_OPM_ACP_FORCE_ULONG, d3dkmdt/DXGKMDT_OPM_ACP_LEVEL_ONE, d3dkmdt/DXGKMDT_OPM_ACP_LEVEL_THREE, d3dkmdt/DXGKMDT_OPM_ACP_LEVEL_TWO, d3dkmdt/DXGKMDT_OPM_ACP_OFF, d3dkmdt/DXGKMDT_OPM_ACP_PROTECTION_LEVEL, display.dxgkmdt_opm_acp_protection_level
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
-	DXGKMDT_OPM_ACP_PROTECTION_LEVEL
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_ACP_PROTECTION_LEVEL
---

# _DXGKMDT_OPM_ACP_PROTECTION_LEVEL Enumeration
The DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports Analog Copy Protection (ACP).

## Syntax
````
typedef enum _DXGKMDT_OPM_ACP_PROTECTION_LEVEL { 
  DXGKMDT_OPM_ACP_OFF          = 0,
  DXGKMDT_OPM_ACP_LEVEL_ONE    = 1,
  DXGKMDT_OPM_ACP_LEVEL_TWO    = 2,
  DXGKMDT_OPM_ACP_LEVEL_THREE  = 3,
  DXGKMDT_OPM_ACP_FORCE_ULONG  = 0x7fffffff
} DXGKMDT_OPM_ACP_PROTECTION_LEVEL;
````

## Constants

<table>
            
                <tr>
                    <td>DXGKMDT_OPM_ACP_FORCE_ULONG</td>
                    <td>Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_ACP_LEVEL_ONE</td>
                    <td>Indicates that the signal from a video output is protected by the ACP level one protection scheme.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_ACP_LEVEL_THREE</td>
                    <td>Indicates that the signal from a video output is protected by the ACP level three protection scheme.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_ACP_LEVEL_TWO</td>
                    <td>Indicates that the signal from a video output is protected by the ACP level two protection scheme.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_ACP_OFF</td>
                    <td>Indicates that the signal from a video output is not protected by any form of ACP.</td>
                </tr>
</table>

## Remarks

ACP protects analog TV signals. For example, a DVD player can use ACP to prevent a VCR from recording a copy of a DVD movie. Currently, OPM can use ACP to protect signals from composite outputs, S-Video outputs, or component outputs. For more information about ACP, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=71273">Rovi (formerly Macrovision)</a> website.

Display miniport drivers use the values in DXGKMDT_OPM_ACP_PROTECTION_LEVEL to report the virtual protection level of the protected output or the actual protection level of a physical connector through calls to the driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> and <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> functions. The values in DXGKMDT_OPM_ACP_PROTECTION_LEVEL are also used to configure the protected output's new virtual protection level in a call to the driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_set_protection_level_parameters.md">DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_standard_information.md">DXGKMDT_OPM_STANDARD_INFORMATION</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>