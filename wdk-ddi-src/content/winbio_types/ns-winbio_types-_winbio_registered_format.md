---
UID: NS:winbio_types._WINBIO_REGISTERED_FORMAT
title: "_WINBIO_REGISTERED_FORMAT"
author: windows-driver-content
description: The WINBIO_REGISTERED_FORMAT structure specifies a biometric data format.
old-location: biometric\winbio_registered_format.htm
old-project: biometric
ms.assetid: 70591143-f429-4a6e-8f2a-cc1082f40f6e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: winbio_types/PWINBIO_REGISTERED_FORMAT, biometric.winbio_registered_format, biometric_ref_824bd2c9-98a7-4967-8416-82aadd8ec6ed.xml, _WINBIO_REGISTERED_FORMAT, *PWINBIO_REGISTERED_FORMAT, PWINBIO_REGISTERED_FORMAT structure pointer [Biometric Devices], PWINBIO_REGISTERED_FORMAT, WINBIO_REGISTERED_FORMAT structure [Biometric Devices], winbio_types/WINBIO_REGISTERED_FORMAT, WINBIO_REGISTERED_FORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winbio_types.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winbio_types.h
apiname:
-	WINBIO_REGISTERED_FORMAT
product: Windows
targetos: Windows
req.typenames: "*PWINBIO_REGISTERED_FORMAT, WINBIO_REGISTERED_FORMAT"
req.product: Windows 10 or later.
---

# _WINBIO_REGISTERED_FORMAT structure
The WINBIO_REGISTERED_FORMAT structure specifies a biometric data format.

## Syntax
````
typedef struct _WINBIO_REGISTERED_FORMAT {
  USHORT Owner;
  USHORT Type;
} WINBIO_REGISTERED_FORMAT, *PWINBIO_REGISTERED_FORMAT;
````

## Members


`Owner`

Specifies format owner.

`Type`

Specifies format type.

## Remarks
For Windows, the format owner is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define WINBIO_ANSI_381_FORMAT_OWNER    ((USHORT)0x001B)    // INCITS Technical Committee M1</pre>
</td>
</tr>
</table></span></div>
The Type for the standard Windows fingerprint format is:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define WINBIO_ANSI_381_FORMAT_TYPE     ((USHORT)0x0401)    // ANSI-381</pre>
</td>
</tr>
</table></span></div>
WBDI drivers for fingerprint sensors must support the Owner and Type for the Windows fingerprint data format. The Windows Biometric Service (WBS) verifies that a sensor minimally supports the Windows fingerprint raw data format.  Windows defines this standard raw data format to allow ISVs to write engine adapters that can take input from any sensor.  Each engine should have a capability to support at least this format, but it can specify a different format as a preferred raw format.

No format owner or type are defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define WINBIO_NO_FORMAT_OWNER_AVAILABLE    ((USHORT)0)
#define WINBIO_NO_FORMAT_TYPE_AVAILABLE     ((USHORT)0)
</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | winbio_types.h |