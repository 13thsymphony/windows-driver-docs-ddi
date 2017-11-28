---
UID: NS.ksmedia.tagKSCAMERA_EXTENDEDPROP_VALUE
title: tagKSCAMERA_EXTENDEDPROP_VALUE
author: windows-driver-content
description: The KSCAMERA_EXTENDEDPROP_VALUE structure is a data type union used to express an extended property value.
old-location: stream\kscamera_extendedprop_value.htm
old-project: stream
ms.assetid: E595C2BF-C3C8-4FE8-90B0-CD53524F4852
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: tagKSCAMERA_EXTENDEDPROP_VALUE, KSCAMERA_EXTENDEDPROP_VALUE, *PKSCAMERA_EXTENDEDPROP_VALUE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_EXTENDEDPROP_VALUE
req.alt-loc: Ksmedia.h
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
req.iface: 
---

# tagKSCAMERA_EXTENDEDPROP_VALUE structure



## -description
<p>The <b>KSCAMERA_EXTENDEDPROP_VALUE</b> structure is a data type union used to express an extended property value.</p>


## -syntax

````
typedef struct _KSCAMERA_EXTENDEDPROP_VALUE {
  union {
    double        dbl;
    ULONGLONG     ull;
    ULONG         ul;
    LARGE_INTEGER ratio;
    LONG          l;
    LONG          ll;
  } Value;
} KSCAMERA_EXTENDEDPROP_VALUE, *PKSCAMERA_EXTENDEDPROP_VALUE;
````


## -struct-fields
<dl>

### -field <b>Value</b>

<dd>
<p>The extended property value. </p>
<dl>

### -field <b>dbl</b>

<dd>
<p>The extended property expressed as a <b>double</b> value.</p>
</dd>

### -field <b>ull</b>

<dd>
<p>The extended property expressed as a <b>ULONGLONG</b> value.</p>
</dd>

### -field <b>ul</b>

<dd>
<p>The extended property expressed as a <b>ULONG</b> value.</p>
</dd>

### -field <b>ratio</b>

<dd>
<p>The extended property value expressed as a ratio.</p>
</dd>

### -field <b>l</b>

<dd>
<p>The extended property expressed as a <b>LONG</b> value.</p>
</dd>

### -field <b>ll</b>

<dd>
<p>The extended property expressed as a <b>LONGLONG</b> value.</p>
</dd>
</dl>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn567563">KSCAMERA_EXTENDEDPROP_HEADER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSCAMERA_EXTENDEDPROP_VALUE structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
