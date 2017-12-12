---
UID: NS.WINBIO_TYPES._WINBIO_REGISTERED_FORMAT
title: _WINBIO_REGISTERED_FORMAT
author: windows-driver-content
description: The WINBIO_REGISTERED_FORMAT structure specifies a biometric data format.
old-location: biometric\winbio_registered_format.htm
old-project: biometric
ms.assetid: 70591143-f429-4a6e-8f2a-cc1082f40f6e
ms.author: windowsdriverdev
ms.date: 11/13/2017
ms.keywords: _WINBIO_REGISTERED_FORMAT, *PWINBIO_REGISTERED_FORMAT, WINBIO_REGISTERED_FORMAT
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
req.alt-api: WINBIO_REGISTERED_FORMAT
req.alt-loc: winbio_types.h
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
req.product: Windows 10 or later.
---

# _WINBIO_REGISTERED_FORMAT structure



## -description
The WINBIO_REGISTERED_FORMAT structure specifies a biometric data format.



## -syntax

````
typedef struct _WINBIO_REGISTERED_FORMAT {
  USHORT Owner;
  USHORT Type;
} WINBIO_REGISTERED_FORMAT, *PWINBIO_REGISTERED_FORMAT;
````


## -struct-fields

### -field Owner

Specifies format owner.


### -field Type

Specifies format type.


## -remarks
For Windows, the format owner is defined as follows:

The Type for the standard Windows fingerprint format is:

WBDI drivers for fingerprint sensors must support the Owner and Type for the Windows fingerprint data format. The Windows Biometric Service (WBS) verifies that a sensor minimally supports the Windows fingerprint raw data format.  Windows defines this standard raw data format to allow ISVs to write engine adapters that can take input from any sensor.  Each engine should have a capability to support at least this format, but it can specify a different format as a preferred raw format.

No format owner or type are defined as follows:


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Winbio_types.h</dt>
</dl>
</td>
</tr>
</table>