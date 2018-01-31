---
UID : NE:icm.COLORPROFILETYPE
title : COLORPROFILETYPE
author : windows-driver-content
description : The COLORPROFILETYPE enumeration is used to specify the type of color profile.
old-location : print\colorprofiletype.htm
old-project : print
ms.assetid : 756ba822-ace2-4893-a989-9d355434e57c
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : colorfnc_409d0d83-91ea-408a-8970-4de6e9cf94eb.xml, icm/COLORPROFILETYPE, icm/CPT_DMP, *PCOLORPROFILETYPE, COLORPROFILETYPE, icm/CPT_CAMP, CPT_ICC, CPT_DMP, print.colorprofiletype, CPT_CAMP, CPT_GMMP, icm/CPT_GMMP, icm/CPT_ICC, COLORPROFILETYPE enumeration [Print Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : icm.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Included in Windows Vista and later.
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
req.typenames : COLORPROFILETYPE
---

# COLORPROFILETYPE Enumeration
The COLORPROFILETYPE enumeration is used to specify the type of color profile.

## Syntax
````
typedef enum  { 
  CPT_ICC   = 0,
  CPT_DMP   = 1,
  CPT_CAMP  = 2,
  CPT_GMMP  = 3
} COLORPROFILETYPE;
````

## Constants

<table>

<tr>
<td>CPT_CAMP</td>
<td>Specifies a WCS color appearance model profile (CAMP). If this value is specified, only the CPST_NONE value of <a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a> is valid.</td>
</tr>

<tr>
<td>CPT_DMP</td>
<td>Specifies a WCS device model profile (DMP). If this value is specified, only the CPST_RGB_WORKING_SPACE and CPST_CUSTOM_WORKING_SPACE values of <a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a> are valid.</td>
</tr>

<tr>
<td>CPT_GMMP</td>
<td>Specifies a WCS gamut map model profile (GMMP). If this value is specified, only the CPST_PERCEPTUAL, CPST_SATURATION, CPST_RELATIVE_COLORIMETRIC, and CPST_ABSOLUTE_COLORIMETRIC values of <a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a> are valid. Any one of these values may optionally be combined (in a bitwise OR operation) with CPST_DEFAULT.</td>
</tr>

<tr>
<td>CPT_ICC</td>
<td>Specifies an ICC profile. If this value is specified, only the CPST_RGB_WORKING_SPACE and CPST_CUSTOM_WORKING_SPACE values of <a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a> are valid.</td>
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
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | icm.h |

## See Also

<a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20COLORPROFILETYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>