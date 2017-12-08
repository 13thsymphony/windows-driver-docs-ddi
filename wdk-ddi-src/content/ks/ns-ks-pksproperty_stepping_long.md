---
UID: NS.KS.PKSPROPERTY_STEPPING_LONG
title: PKSPROPERTY_STEPPING_LONG
author: windows-driver-content
description: The KSPROPERTY_STEPPING_LONG structure defines the valid range of values for a 32-bit property.
old-location: stream\ksproperty_stepping_long.htm
old-project: stream
ms.assetid: bf0c16f5-ecfa-42bc-bd60-805d5b28ddc3
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSPROPERTY_STEPPING_LONG, KSPROPERTY_STEPPING_LONG, *PKSPROPERTY_STEPPING_LONG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_STEPPING_LONG
req.alt-loc: ks.h
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
---

# PKSPROPERTY_STEPPING_LONG structure



## -description
The KSPROPERTY_STEPPING_LONG structure defines the valid range of values for a 32-bit property.


## -syntax

````
typedef struct {
  ULONG                  SteppingDelta;
  ULONG                  Reserved;
  KSPROPERTY_BOUNDS_LONG Bounds;
} KSPROPERTY_STEPPING_LONG, *PKSPROPERTY_STEPPING_LONG;
````


## -struct-fields

### -field SteppingDelta

Specifies the step value that should be used to create legal values within the range defined in <b>Bounds</b>.

### -field Reserved

Reserved for system use.

### -field Bounds

A structure of type <a href="stream.ksproperty_bounds_long">KSPROPERTY_BOUNDS_LONG</a> that specifies the range of values over which the <b>SteppingDelta</b> is valid.

## -remarks
The <a href="stream.ksproperty_memberslist">KSPROPERTY_MEMBERSLIST</a> structure may contain structures of this type in its <b>Members</b> array.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksproperty_bounds_long">KSPROPERTY_BOUNDS_LONG</a>
</dt>
<dt>
<a href="stream.ksproperty_memberslist">KSPROPERTY_MEMBERSLIST</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_STEPPING_LONG structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
