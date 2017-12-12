---
UID: NS.KS.PKSALLOCATOR_FRAMING_EX
title: PKSALLOCATOR_FRAMING_EX
author: windows-driver-content
description: The KSALLOCATOR_FRAMING_EX structure is the AVStream replacement for KSALLOCATOR_FRAMING. KSALLOCATOR_FRAMING_EX defines allocator requirements on a pin in a kernel level filter.
old-location: stream\ksallocator_framing_ex.htm
old-project: stream
ms.assetid: 39101009-ba03-472b-8664-d00c7a5cd335
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSALLOCATOR_FRAMING_EX, KSALLOCATOR_FRAMING_EX, *PKSALLOCATOR_FRAMING_EX
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
req.alt-api: KSALLOCATOR_FRAMING_EX
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

# PKSALLOCATOR_FRAMING_EX structure



## -description
The KSALLOCATOR_FRAMING_EX structure is the AVStream replacement for KSALLOCATOR_FRAMING. KSALLOCATOR_FRAMING_EX defines allocator requirements on a pin in a kernel level filter.



## -syntax

````
typedef struct {
  ULONG           CountItems;
  ULONG           PinFlags;
  KS_COMPRESSION  OutputCompression;
  ULONG           PinWeight;
  KS_FRAMING_ITEM FramingItem[1];
} KSALLOCATOR_FRAMING_EX, *PKSALLOCATOR_FRAMING_EX;
````


## -struct-fields

### -field CountItems

Specifies the number of framing items that are present in the <b>FramingItem</b> array.


### -field PinFlags

Reserved, set to zero.


### -field OutputCompression

Points to a structure of type <a href="stream.ks_compression">KS_COMPRESSION</a> that defines the frame ratio for transforms that change the size of a frame.


### -field PinWeight

This pin framing's weight graph-wide. Reserved, set to zero.


### -field FramingItem

An array of <a href="stream.ks_framing_item">KS_FRAMING_ITEM</a> structures specifying the actual framing items.


## -remarks
A minidriver can also use DECLARE_SIMPLE_FRAMING_EX to declare an extended framing structure in line with the original structure. This macro is defined in <i>Ks.h</i> as follows:

DECLARE_SIMPLE_FRAMING_EX declares a KSALLOCATOR_FRAMING_EX structure called <b>FramingExName</b> with the specified memory type (often either STATIC_KS_TYPE_DONT_CARE or one of the kernel paged or nonpaged GUIDs). The <b>Frames</b> and <b>Alignment</b> fields of the macro correspond to the <a href="stream.ksallocator_framing">KSALLOCATOR_FRAMING</a>. <b>MinFrameSize</b> and <b>MaxFrameSize</b> ensure that frames are within a specific size range. Flags corresponds to the <b>OptionsFlags</b> and <b>RequirementsFlags</b> in <b>KSALLOCATOR_FRAMING</b>.


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
<a href="stream.ks_framing_item">KS_FRAMING_ITEM</a>
</dt>
<dt>
<a href="stream.ksallocator_framing">KSALLOCATOR_FRAMING</a>
</dt>
<dt>
<a href="stream.ks_compression">KS_COMPRESSION</a>
</dt>
<dt>
<a href="stream.ks_framing_range">KS_FRAMING_RANGE</a>
</dt>
<dt>
<a href="stream.ks_framing_range_weighted">KS_FRAMING_RANGE_WEIGHTED</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSALLOCATOR_FRAMING_EX structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

