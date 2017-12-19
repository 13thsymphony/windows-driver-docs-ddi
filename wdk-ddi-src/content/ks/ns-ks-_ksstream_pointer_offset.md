---
UID: NS.KS._KSSTREAM_POINTER_OFFSET
title: _KSSTREAM_POINTER_OFFSET
author: windows-driver-content
description: The KSSTREAM_POINTER_OFFSET structure indexes bytes or mappings within a frame.
old-location: stream\ksstream_pointer_offset.htm
old-project: stream
ms.assetid: ccbe77ee-2377-45d9-b8bf-714680c1920a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _KSSTREAM_POINTER_OFFSET, KSSTREAM_POINTER_OFFSET, *PKSSTREAM_POINTER_OFFSET
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
req.alt-api: KSSTREAM_POINTER_OFFSET
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

# _KSSTREAM_POINTER_OFFSET structure



## -description
The KSSTREAM_POINTER_OFFSET structure indexes bytes or mappings within a frame.



## -syntax

````
typedef struct _KSSTREAM_POINTER_OFFSET {
  union {
    PUCHAR     Data;
    PKSMAPPING Mappings;
  };
  ULONG Count;
  ULONG Remaining;
} KSSTREAM_POINTER_OFFSET, *PKSSTREAM_POINTER_OFFSET;
````


## -struct-fields

### -field Data

A pointer to a buffer containing input data or a buffer to which data is to be output. Specify <b>Data</b> if the minidriver does not set the KSPIN_FLAG_GENERATE_MAPPINGS flag in the <b>Flags</b> member of <a href="stream.kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>.


### -field Mappings

A pointer to the first element in an array of <a href="stream.ksmapping">KSMAPPING</a> structures. Specify <b>Mappings</b> if the minidriver sets the KSPIN_FLAG_GENERATE_MAPPINGS flag in the <b>Flags</b> member of <a href="stream.kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>. In this case, the <b>Mappings</b> array describes contiguous chunks of physical memory that the client can use to set up a scatter/gather DMA operation with hardware. 



### -field Count

If <b>Data</b> is specified above, <b>Count</b> contains the total number of bytes of data available in the <b>Data</b> buffer. If <b>Mappings</b> is specified above, <b>Count</b> contains the total number of mappings in the <b>Mappings</b> table. <b>Count</b> does not change unless the stream pointer moves to a different <i>Frame</i>.


### -field Remaining

This member specifies a value of type ULONG that indicates the number of bytes or mappings remaining at and ahead of the given stream pointer. This value is equal to <b>Count</b> minus the number of bytes or mappings that have been processed. <b>Remaining</b> starts equal to <b>Count</b> and decreases as the stream pointer moves forward.


## -remarks
See also <a href="https://msdn.microsoft.com/ba1c525b-26b0-4778-b58b-f4169cfb972e">AVStream DMA Services</a>.


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
<a href="stream.ksstream_pointer">KSSTREAM_POINTER</a>
</dt>
<dt>
<a href="stream.ksmapping">KSMAPPING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSSTREAM_POINTER_OFFSET structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

