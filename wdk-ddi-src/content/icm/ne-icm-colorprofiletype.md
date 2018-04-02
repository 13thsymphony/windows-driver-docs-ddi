---
UID: NE:icm.COLORPROFILETYPE
title: COLORPROFILETYPE
author: windows-driver-content
description: The COLORPROFILETYPE enumeration is used to specify the type of color profile.
old-location: print\colorprofiletype.htm
old-project: print
ms.assetid: 756ba822-ace2-4893-a989-9d355434e57c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCOLORPROFILETYPE, COLORPROFILETYPE, COLORPROFILETYPE enumeration [Print Devices], CPT_CAMP, CPT_DMP, CPT_GMMP, CPT_ICC, colorfnc_409d0d83-91ea-408a-8970-4de6e9cf94eb.xml, icm/COLORPROFILETYPE, icm/CPT_CAMP, icm/CPT_DMP, icm/CPT_GMMP, icm/CPT_ICC, print.colorprofiletype"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: icm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Included in Windows Vista and later.
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
-	icm.h
api_name:
-	COLORPROFILETYPE
product: Windows
targetos: Windows
req.typenames: COLORPROFILETYPE
---

# COLORPROFILETYPE Enumeration
The COLORPROFILETYPE enumeration is used to specify the type of color profile.

## Syntax
```
typedef enum COLORPROFILETYPE {
  CPT_ICC   ,
  CPT_DMP   ,
  CPT_CAMP  ,
  CPT_GMMP
} ;
```

## Constants

<table>
            
                <tr>
                    <td>CPT_ICC</td>
                    <td>Specifies an ICC profile. If this value is specified, only the CPST_RGB_WORKING_SPACE and CPST_CUSTOM_WORKING_SPACE values of <a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a> are valid.</td>
                </tr>
            
                <tr>
                    <td>CPT_DMP</td>
                    <td>Specifies a WCS device model profile (DMP). If this value is specified, only the CPST_RGB_WORKING_SPACE and CPST_CUSTOM_WORKING_SPACE values of <a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a> are valid.</td>
                </tr>
            
                <tr>
                    <td>CPT_CAMP</td>
                    <td>Specifies a WCS color appearance model profile (CAMP). If this value is specified, only the CPST_NONE value of <a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a> is valid.</td>
                </tr>
            
                <tr>
                    <td>CPT_GMMP</td>
                    <td>Specifies a WCS gamut map model profile (GMMP). If this value is specified, only the CPST_PERCEPTUAL, CPST_SATURATION, CPST_RELATIVE_COLORIMETRIC, and CPST_ABSOLUTE_COLORIMETRIC values of <a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a> are valid. Any one of these values may optionally be combined (in a bitwise OR operation) with CPST_DEFAULT.</td>
                </tr>
</table>

## Remarks

The PCOLORPROFILETYPE and LPCOLORPROFILETYPE data types are defined as pointers to this enumeration:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef COLORPROFILETYPE *PCOLORPROFILETYPE, *LPCOLORPROFILETYPE;</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Included in Windows Vista and later. Included in Windows Vista and later. |
| **Header** | icm.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546012">COLORPROFILESUBTYPE</a>