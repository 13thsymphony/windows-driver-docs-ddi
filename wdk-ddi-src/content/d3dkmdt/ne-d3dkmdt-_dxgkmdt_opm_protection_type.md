---
UID: NE:d3dkmdt._DXGKMDT_OPM_PROTECTION_TYPE
title: "_DXGKMDT_OPM_PROTECTION_TYPE"
author: windows-driver-content
description: The DXGKMDT_OPM_PROTECTION_TYPE enumeration indicates the type of protections that a video output supports.
old-location: display\dxgkmdt_opm_protection_type.htm
old-project: display
ms.assetid: 2e82c863-16d8-4b79-b662-fc1c766a2f05
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKMDT_OPM_PROTECTION_TYPE_OTHER, display.dxgkmdt_opm_protection_type, DXGKMDT_OPM_PROTECTION_TYPE_DPCP, DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP, DXGKMDT_OPM_PROTECTION_TYPE_MASK, DXGKMDT_OPM_PROTECTION_TYPE_CGMSA, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_HDCP, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_MASK, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_DPCP, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_OTHER, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE, DmEnums_8213d95c-c1df-4084-b386-cfb9fac440e0.xml, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_ACP, _DXGKMDT_OPM_PROTECTION_TYPE, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_NONE, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_CGMSA, DXGKMDT_OPM_PROTECTION_TYPE, DXGKMDT_OPM_PROTECTION_TYPE_ACP, DXGKMDT_OPM_PROTECTION_TYPE enumeration [Display Devices], DXGKMDT_OPM_PROTECTION_TYPE_NONE, DXGKMDT_OPM_PROTECTION_TYPE_HDCP
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	DXGKMDT_OPM_PROTECTION_TYPE
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_PROTECTION_TYPE
---

# _DXGKMDT_OPM_PROTECTION_TYPE Enumeration
The DXGKMDT_OPM_PROTECTION_TYPE enumeration indicates the type of protections that a video output supports.

## Syntax
````
typedef enum _DXGKMDT_OPM_PROTECTION_TYPE { 
  DXGKMDT_OPM_PROTECTION_TYPE_OTHER                 = 0x80000000,
  DXGKMDT_OPM_PROTECTION_TYPE_NONE                  = 0x00000000,
  DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP  = 0x00000001,
  DXGKMDT_OPM_PROTECTION_TYPE_ACP                   = 0x00000002,
  DXGKMDT_OPM_PROTECTION_TYPE_CGMSA                 = 0x00000004,
  DXGKMDT_OPM_PROTECTION_TYPE_HDCP                  = 0x00000008,
  DXGKMDT_OPM_PROTECTION_TYPE_DPCP                  = 0x00000010,
  DXGKMDT_OPM_PROTECTION_TYPE_MASK                  = 0x8000001F
} DXGKMDT_OPM_PROTECTION_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_TYPE_ACP</td>
                    <td>Indicates that the protected output supports Analog Copy Protection (ACP). ACP protects analog TV signals. Currently, OPM can use ACP to protect signals from composite outputs, S-Video outputs, or component outputs. For more information about ACP, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=71273">Rovi (formerly Macrovision)</a> website. OPM can use this value in a call to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> function to determine whether a protected output supports ACP. OPM can also use this value in a call to the driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> function to change the ACP protection level.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_TYPE_CGMSA</td>
                    <td>Indicates that the protected output supports Content Generation Management System Analog (CGMS-A). CGMS-A protects analog TV signals. Currently, OPM can use CGMS-A to protect signals from composite outputs, S-Video outputs, or component outputs. For more information about CGMS-A, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70568">CGMS-A article</a>. OPM can use this value in a call to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> function to determine whether a protected output supports CGMS-A. OPM can also use this value in a call to the driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> function to change the CGMS-A protection level.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP</td>
                    <td>Indicates that the protected output supports High-bandwidth Digital Content Protection (HDCP) that is compatible with Certified Output Protection Protocol (COPP). For more information about HDCP, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=38728">HDCP Specification Revision 1.1</a>. This protection type can be used only with protected output objects that have COPP semantics. OPM can use this value in a call to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> function to determine whether a protected output supports COPP-compatible HDCP. OPM can also use this value in a call to the driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> function to change the COPP-compatible HDCP protection level.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_TYPE_DPCP</td>
                    <td>Indicates that the protected output supports DisplayPort Copy Protection (DPCP). For more information about DisplayPort, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=71382">DisplayPort article</a>. This protection type can be used only with protected output objects that have OPM semantics. OPM can use this value in a call to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> function to determine whether a protected output supports DPCP. OPM can also use this value in a call to the driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> function to change the DPCP protection level.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_TYPE_HDCP</td>
                    <td>Indicates that the protected output supports HDCP. This protection type can be used only with protected output objects that have OPM semantics. OPM can use this value in a call to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> function to determine whether a protected output supports HDCP. OPM can also use this value in a call to the driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> function to change the HDCP protection level.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_TYPE_MASK</td>
                    <td>A mask value that indicates the valid bitfields in a bitwise OR combination of the values from this enumeration.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_TYPE_NONE</td>
                    <td>Indicates that the video output does not support any protection type.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_TYPE_OTHER</td>
                    <td>Indicates a protection type other than those given in the following constants of this enumeration.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_TYPE_TYPE_ENFORCEMENT_HDCP</td>
                    <td></td>
                </tr>
</table>

    ## Remarks

        DXGKMDT_OPM_PROTECTION_TYPE_HDCP and DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP are used to turn HDCP on or off and to determine if HDCP is on or off. 

If a protected output supports DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP, it supports HDCP repeaters, and an application handles HDCP revocation. If a protected output supports DXGKMDT_OPM_PROTECTION_TYPE_HDCP, it supports HDCP repeaters and handles HDCP revocation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

    ## See Also

        <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_set_protection_level_parameters.md">DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_standard_information.md">DXGKMDT_OPM_STANDARD_INFORMATION</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_PROTECTION_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>