---
UID: NE:d3dkmdt._DXGKMDT_OPM_PROTECTION_STANDARD
title: "_DXGKMDT_OPM_PROTECTION_STANDARD"
author: windows-driver-content
description: The DXGKMDT_OPM_PROTECTION_STANDARD enumeration indicates the type of television signal for which a video output supports protection.
old-location: display\dxgkmdt_opm_protection_standard.htm
old-project: display
ms.assetid: 9f079edf-312a-4218-8b73-0325ccca5a05
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_1125I, DXGKMDT_OPM_PROTECTION_STANDARD_EN300294_625I, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_750P, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_750P, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_IEC61880_525I, DXGKMDT_OPM_PROTECTION_STANDARD_OTHER, DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_525P, DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_750P, DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_525P, DXGKMDT_OPM_PROTECTION_STANDARD_IEC62375_625P, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_IEC62375_625P, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_EN300294_625I, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_525P, DXGKMDT_OPM_PROTECTION_STANDARD_EIA608B_525, DXGKMDT_OPM_PROTECTION_STANDARD_IEC61880_525I, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_IEC61880_2_525I, DXGKMDT_OPM_PROTECTION_STANDARD_NONE, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_1125I, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_525P, DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_1125I, DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_1125I, DXGKMDT_OPM_PROTECTION_STANDARD, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_750P, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_525I, DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_750P, DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_1125I, DXGKMDT_OPM_PROTECTION_STANDARD_IEC61880_2_525I, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_525P, DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_750P, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_OTHER, display.dxgkmdt_opm_protection_standard, DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_525P, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_1125I, _DXGKMDT_OPM_PROTECTION_STANDARD, DXGKMDT_OPM_PROTECTION_STANDARD enumeration [Display Devices], d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_NONE, DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_525I, DmEnums_ce6cf9d1-ec7d-43bd-9204-2428751bdabf.xml, d3dkmdt/DXGKMDT_OPM_PROTECTION_STANDARD_EIA608B_525
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
-	DXGKMDT_OPM_PROTECTION_STANDARD
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_PROTECTION_STANDARD
---

# _DXGKMDT_OPM_PROTECTION_STANDARD Enumeration
The DXGKMDT_OPM_PROTECTION_STANDARD enumeration indicates the type of television signal for which a video output supports protection.

## Syntax
````
typedef enum _DXGKMDT_OPM_PROTECTION_STANDARD { 
  DXGKMDT_OPM_PROTECTION_STANDARD_OTHER                = 0x80000000,
  DXGKMDT_OPM_PROTECTION_STANDARD_NONE                 = 0x00000000,
  DXGKMDT_OPM_PROTECTION_STANDARD_IEC61880_525I        = 0x00000001,
  DXGKMDT_OPM_PROTECTION_STANDARD_IEC61880_2_525I      = 0x00000002,
  DXGKMDT_OPM_PROTECTION_STANDARD_IEC62375_625P        = 0x00000004,
  DXGKMDT_OPM_PROTECTION_STANDARD_EIA608B_525          = 0x00000008,
  DXGKMDT_OPM_PROTECTION_STANDARD_EN300294_625I        = 0x00000010,
  DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_525P   = 0x00000020,
  DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_750P   = 0x00000040,
  DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_1125I  = 0x00000080,
  DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_525P   = 0x00000100,
  DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_750P   = 0x00000200,
  DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_1125I  = 0x00000400,
  DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_525I       = 0x00000800,
  DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_525P       = 0x00001000,
  DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_750P       = 0x00002000,
  DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_1125I      = 0x00004000
} DXGKMDT_OPM_PROTECTION_STANDARD;
````

## Constants

<table>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_1125I</td>
                    <td>Indicates that the video output supports the ARIBTRB15_1125I standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_525I</td>
                    <td>Indicates that the video output supports the ARIBTRB15_525I standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_525P</td>
                    <td>Indicates that the video output supports the ARIBTRB15_525P standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_750P</td>
                    <td>Indicates that the video output supports the ARIBTRB15_750P standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_1125I</td>
                    <td>Indicates that the video output supports the CEA805A_TYPEA_1125I standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_525P</td>
                    <td>Indicates that the video output supports the CEA805A_TYPEA_525P standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_750P</td>
                    <td>Indicates that the video output supports the CEA805A_TYPEA_750P standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_1125I</td>
                    <td>Indicates that the video output supports the CEA805A_TYPEB_1125I standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_525P</td>
                    <td>Indicates that the video output supports the CEA805A_TYPEB_525P standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_750P</td>
                    <td>Indicates that the video output supports the CEA805A_TYPEB_750P standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_EIA608B_525</td>
                    <td>Indicates that the video output supports the EIA608B_525 standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_EN300294_625I</td>
                    <td>Indicates that the video output supports the EN300294_625I standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_IEC61880_2_525I</td>
                    <td>Indicates that the video output supports the IEC61880_2_525I standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_IEC61880_525I</td>
                    <td>Indicates that the video output supports the IEC61880_525I standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_IEC62375_625P</td>
                    <td>Indicates that the video output supports the IEC62375_625P standard.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_NONE</td>
                    <td>Indicates that the video output does not support protection for any television signals.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_PROTECTION_STANDARD_OTHER</td>
                    <td>Indicates a protected television signal type other than those given in the following constants of this enumeration.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

    ## See Also

        <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_acp_and_cgmsa_signaling.md">DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_set_acp_and_cgmsa_signaling_parameters.md">DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_PROTECTION_STANDARD enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>