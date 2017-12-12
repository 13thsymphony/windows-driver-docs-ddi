---
UID: NS.KS.PKSPROPERTY_BOUNDS_LONGLONG
title: PKSPROPERTY_BOUNDS_LONGLONG
author: windows-driver-content
description: The KSPROPERTY_BOUNDS_LONGLONG structure defines the bounds for a 64-bit property.
old-location: stream\ksproperty_bounds_longlong.htm
old-project: stream
ms.assetid: 25e3e430-abce-4d14-a336-4cb32a4fe5df
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSPROPERTY_BOUNDS_LONGLONG, *PKSPROPERTY_BOUNDS_LONGLONG, KSPROPERTY_BOUNDS_LONGLONG
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
req.alt-api: KSPROPERTY_BOUNDS_LONGLONG
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

# PKSPROPERTY_BOUNDS_LONGLONG structure



## -description
The KSPROPERTY_BOUNDS_LONGLONG structure defines the bounds for a 64-bit property.



## -syntax

````
typedef union {
  struct {
    LONGLONG SignedMinimum;
    LONGLONG SignedMaximum;
  };
  struct {
    ULONGLONG UnsignedMinimum;
    ULONGLONG UnsignedMaximum;
  };
} KSPROPERTY_BOUNDS_LONGLONG, *PKSPROPERTY_BOUNDS_LONGLONG;
````


## -struct-fields

### -field SignedMinimum

Specifies a minimum bound as a signed 64-bit value.


### -field SignedMaximum

Specifies a maximum bound as a signed 64-bit value.


### -field UnsignedMinimum

Specifies a minimum bound as an unsigned 64-bit value.


### -field UnsignedMaximum

Specifies a maximum bound as an unsigned 64-bit value.


## -remarks
This structure specifies a range of 64-bit values for a property. Use only when the <b>MembersFlags</b> member of the relevant <a href="stream.ksproperty_membersheader">KSPROPERTY_MEMBERSHEADER</a> is set to KSPROPERTY_MEMBER_RANGES. Use this structure in the <b>Members</b> array in the relevant <a href="stream.ksproperty_memberslist">KSPROPERTY_MEMBERSLIST</a> structure.


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
<a href="stream.ksproperty_values">KSPROPERTY_VALUES</a>
</dt>
<dt>
<a href="stream.ksproperty_membersheader">KSPROPERTY_MEMBERSHEADER</a>
</dt>
<dt>
<a href="stream.ksproperty_memberslist">KSPROPERTY_MEMBERSLIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_BOUNDS_LONGLONG union%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

