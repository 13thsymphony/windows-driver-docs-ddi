---
UID: NS:avc._AVC_IRB
title: _AVC_IRB
author: windows-driver-content
description: The AVC_IRB structure is an I/O Request Block (IRB) header structure where a function number is stored.
old-location: stream\avc_irb.htm
old-project: stream
ms.assetid: 8798e152-6586-48d0-a8f6-2e861660dd62
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _AVC_IRB, *PAVC_IRB, AVC_IRB
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVC_IRB
req.alt-loc: avc.h
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
req.typenames: *PAVC_IRB, AVC_IRB
---

# _AVC_IRB structure



## -description
The AVC_IRB structure is an I/O Request Block (IRB) header structure where a function number is stored.



## -syntax

````
typedef struct _AVC_IRB {
  AVC_FUNCTION Function;
} AVC_IRB, *PAVC_IRB;
````


## -struct-fields

### -field Function

Value from the AVC_FUNCTION enumeration specifying a function number.


## -remarks
This structure is included at the head of the AVC_COMMAND_IRB and AVC_MULTIFUNC_IRB structures. These structures represent the I/O request block (IRB) associated with specific types of AV/C functions. Each specific type of AV/C function is documented in IOCTL_AVC_CLASS.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Avc.h (include Avc.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\avc\ns-avc-_avc_command_irb.md">AVC_COMMAND_IRB</a>
</dt>
<dt>
<a href="..\avc\ns-avc-_avc_multifunc_irb.md">AVC_MULTIFUNC_IRB</a>
</dt>
<dt>
<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>
</dt>
<dt>
<a href="..\avc\ni-avc-ioctl_avc_class.md">IOCTL_AVC_CLASS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_IRB structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

