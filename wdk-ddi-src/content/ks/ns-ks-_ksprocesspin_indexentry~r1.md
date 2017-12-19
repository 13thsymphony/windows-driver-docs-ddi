---
UID: NS.KS._KSPROCESSPIN_INDEXENTRY~R1
title: _KSPROCESSPIN_INDEXENTRY
author: windows-driver-content
description: The KSPROCESSPIN_INDEXENTRY structure is used in Filter-Centric Processing to bring together all of the input and output pins in one context.
old-location: stream\ksprocesspin_indexentry.htm
old-project: stream
ms.assetid: 8fa26442-66a3-4eeb-89d4-21418d60a1af
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _KSPROCESSPIN_INDEXENTRY, *PKSPROCESSPIN_INDEXENTRY, KSPROCESSPIN_INDEXENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROCESSPIN_INDEXENTRY
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

# _KSPROCESSPIN_INDEXENTRY structure



## -description
The KSPROCESSPIN_INDEXENTRY structure is used in <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a> to bring together all of the input and output pins in one context.



## -syntax

````
typedef struct _KSPROCESSPIN_INDEXENTRY {
  PKSPROCESSPIN *Pins;
  ULONG         Count;
} KSPROCESSPIN_INDEXENTRY, *PKSPROCESSPIN_INDEXENTRY;
````


## -struct-fields

### -field Pins

A pointer to an array of <a href="stream.ksprocesspin">KSPROCESSPIN</a> structures. The array contains a listing of the instances of the given pin.


### -field Count

This member specifies the number of process pins in <i>Pins</i> that are currently instantiated.


## -remarks
This pointer table is indexed in order of the pins described in the pin descriptor table for the corresponding filter. The first pin described in the descriptor table has the first entry in the index table passed to the processing dispatch. See the processing dispatch in <a href="stream.kspin_dispatch">KSPIN_DISPATCH</a>.

For more information, see <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.

</td>
</tr>
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
<a href="stream.ksprocesspin">KSPROCESSPIN</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROCESSPIN_INDEXENTRY structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

