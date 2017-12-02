---
UID: NS.ks.PKSERROR
title: PKSERROR
author: windows-driver-content
description: The KSERROR structure is used to report streaming errors in both kernel and user mode to their respective quality managers.
old-location: stream\kserror.htm
old-project: stream
ms.assetid: c475810c-505e-446a-9b98-d512e745b6ce
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSERROR, KSERROR, *PKSERROR
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
req.alt-api: KSERROR
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
req.iface: 
---

# PKSERROR structure



## -description
<p>The KSERROR structure is used to report streaming errors in both kernel and user mode to their respective quality managers.</p>


## -syntax

````
typedef struct {
  PVOID Context;
  ULONG Status;
} KSERROR, *PKSERROR;
````


## -struct-fields
<dl>

### -field Context

<dd>
<p>Specifies a context parameter that was originally passed to the connection.</p>
</dd>

### -field Status

<dd>
<p>Specifies the NTSTATUS error.</p>
</dd>
</dl>

## -remarks
<p>Streaming error notifications can be generated against the Quality Management sink, if assigned. The same method of proxying Quality Management complaints is used for forwarding error reports for DirectShow graphs. For more information, see <a href="https://msdn.microsoft.com/359e6e12-903f-4037-8f35-b090ce41f770">Quality Management</a>.</p>

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
<a href="stream.ksdegrade">KSDEGRADE</a>
</dt>
<dt>
<a href="..\ks\ne-ks-ksdegrade-standard.md">KSDEGRADE_STANDARD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565211">KSPROPERTY_QUALITY_ERROR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSERROR structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
