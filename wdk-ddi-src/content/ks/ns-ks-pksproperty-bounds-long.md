---
UID: NS.ks.PKSPROPERTY_BOUNDS_LONG
title: PKSPROPERTY_BOUNDS_LONG
author: windows-driver-content
description: The KSPROPERTY_BOUNDS_LONG structure defines the bounds for a 32-bit property.
old-location: stream\ksproperty_bounds_long.htm
ms.assetid: 16804ff1-8531-48aa-baf6-b89ccfe25d07
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: stream
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_BOUNDS_LONG
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
ms.keywords: PKSPROPERTY_BOUNDS_LONG, KSPROPERTY_BOUNDS_LONG, *PKSPROPERTY_BOUNDS_LONG
req.iface: 
---

# PKSPROPERTY_BOUNDS_LONG structure



## -description
<p>The KSPROPERTY_BOUNDS_LONG structure defines the bounds for a 32-bit property.</p>


## -syntax

````
typedef union {
  struct {
    LONG SignedMinimum;
    LONG SignedMaximum;
  };
  struct {
    ULONG UnsignedMinimum;
    ULONG UnsignedMaximum;
  };
} KSPROPERTY_BOUNDS_LONG, *PKSPROPERTY_BOUNDS_LONG;
````


## -struct-fields
<dl>

### -field <b>SignedMinimum</b>

<dd>
<p>Specifies a minimum bound as a signed 32-bit value.</p>
</dd>

### -field <b>SignedMaximum</b>

<dd>
<p>Specifies a maximum bound as a signed 32-bit value.</p>
</dd>

### -field <b>UnsignedMinimum</b>

<dd>
<p>Specifies a minimum bound as an unsigned 32-bit value.</p>
</dd>

### -field <b>UnsignedMaximum</b>

<dd>
<p>Specifies a maximum bound as an unsigned 32-bit value.</p>
</dd>
</dl>

## -remarks
<p>This structure specifies a range of 32-bit values for a property. Use only when the <b>MembersFlags</b> member of the relevant <a href="https://msdn.microsoft.com/library/windows/hardware/ff565189">KSPROPERTY_MEMBERSHEADER</a> is set to KSPROPERTY_MEMBER_RANGES. Use this structure in the <b>Members</b> array in the relevant <a href="https://msdn.microsoft.com/library/windows/hardware/ff565190">KSPROPERTY_MEMBERSLIST</a> structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565966">KSPROPERTY_VALUES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565189">KSPROPERTY_MEMBERSHEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565190">KSPROPERTY_MEMBERSLIST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_BOUNDS_LONG union%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
