---
UID: NE.d3dkmdt._DXGKMDT_OPM_PROTECTION_STANDARD
title: _DXGKMDT_OPM_PROTECTION_STANDARD
author: windows-driver-content
description: The DXGKMDT_OPM_PROTECTION_STANDARD enumeration indicates the type of television signal for which a video output supports protection.
old-location: display\dxgkmdt_opm_protection_standard.htm
old-project: display
ms.assetid: 9f079edf-312a-4218-8b73-0325ccca5a05
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGKMDT_OPM_PROTECTION_STANDARD, DXGKMDT_OPM_PROTECTION_STANDARD
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
req.alt-api: DXGKMDT_OPM_PROTECTION_STANDARD
req.alt-loc: d3dkmdt.h
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
---

# _DXGKMDT_OPM_PROTECTION_STANDARD enumeration



## -description
The DXGKMDT_OPM_PROTECTION_STANDARD enumeration indicates the type of television signal for which a video output supports protection.


## -syntax

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


## -enum-fields

### -field DXGKMDT_OPM_PROTECTION_STANDARD_OTHER

Indicates a protected television signal type other than those given in the following constants of this enumeration. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_NONE

Indicates that the video output does not support protection for any television signals. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_IEC61880_525I

Indicates that the video output supports the IEC61880_525I standard. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_IEC61880_2_525I

Indicates that the video output supports the IEC61880_2_525I standard. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_IEC62375_625P

Indicates that the video output supports the IEC62375_625P standard. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_EIA608B_525

Indicates that the video output supports the EIA608B_525 standard. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_EN300294_625I

Indicates that the video output supports the EN300294_625I standard. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_525P

Indicates that the video output supports the CEA805A_TYPEA_525P standard. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_750P

Indicates that the video output supports the CEA805A_TYPEA_750P standard. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEA_1125I

Indicates that the video output supports the CEA805A_TYPEA_1125I standard. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_525P

Indicates that the video output supports the CEA805A_TYPEB_525P standard. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_750P

Indicates that the video output supports the CEA805A_TYPEB_750P standard. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_CEA805A_TYPEB_1125I

Indicates that the video output supports the CEA805A_TYPEB_1125I standard. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_525I

Indicates that the video output supports the ARIBTRB15_525I standard. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_525P

Indicates that the video output supports the ARIBTRB15_525P standard. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_750P

Indicates that the video output supports the ARIBTRB15_750P standard. 

### -field DXGKMDT_OPM_PROTECTION_STANDARD_ARIBTRB15_1125I

Indicates that the video output supports the ARIBTRB15_1125I standard. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>
</dt>
<dt>
<a href="display.dxgkmdt_opm_acp_and_cgmsa_signaling">DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING</a>
</dt>
<dt>
<a href="display.dxgkmdt_opm_set_acp_and_cgmsa_signaling_parameters">DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_PROTECTION_STANDARD enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
