---
UID: NE.d3dkmdt._DXGKDT_OPM_DVI_CHARACTERISTICS
title: _DXGKDT_OPM_DVI_CHARACTERISTICS
author: windows-driver-content
description: The DXGKDT_OPM_DVI_CHARACTERISTICS enumeration indicates the Digital Video Interface (DVI) electrical characteristics of a connector.
old-location: display\dxgkdt_opm_dvi_characteristics.htm
old-project: display
ms.assetid: 4286a059-ef44-4a11-8e8e-ab030583f58d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGKDT_OPM_DVI_CHARACTERISTICS, DXGKDT_OPM_DVI_CHARACTERISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKDT_OPM_DVI_CHARACTERISTICS
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

# _DXGKDT_OPM_DVI_CHARACTERISTICS enumeration



## -description
The DXGKDT_OPM_DVI_CHARACTERISTICS enumeration indicates the Digital Video Interface (DVI) electrical characteristics of a connector. 


## -syntax

````
typedef enum _DXGKDT_OPM_DVI_CHARACTERISTICS { 
  DXGKMDT_OPM_DVI_CHARACTERISTIC_1_0           = 1,
  DXGKMDT_OPM_DVI_CHARACTERISTIC_1_1_OR_ABOVE  = 2,
  DXGKMDT_OPM_DVI_CHARACTERISTICS_FORCE_ULONG  = 0xFFFFFFFF
} DXGKDT_OPM_DVI_CHARACTERISTICS;
````


## -enum-fields

### -field DXGKMDT_OPM_DVI_CHARACTERISTIC_1_0

Indicates that the DVI electrical characteristics are version 1.0. 

### -field DXGKMDT_OPM_DVI_CHARACTERISTIC_1_1_OR_ABOVE

Indicates that the DVI electrical characteristics are version 1.1 or later. 

### -field DXGKMDT_OPM_DVI_CHARACTERISTICS_FORCE_ULONG

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.

## -remarks
The DXGKMDT_OPM_GET_DVI_CHARACTERISTICS GUID is used in a call to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> function to retrieve the DVI electrical characteristics of the output connector. For more information about retrieving information about a protected output, see <a href="https://msdn.microsoft.com/20e268b8-fea0-48dd-a3cd-3cbb4233ef99">Retrieving Information About a Protected Output</a>. 

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows 7 and later versions of the Windows operating systems.
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
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDT_OPM_DVI_CHARACTERISTICS enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
