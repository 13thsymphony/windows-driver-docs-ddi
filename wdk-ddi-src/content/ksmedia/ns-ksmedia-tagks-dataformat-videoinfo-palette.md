---
UID: NS.ksmedia.tagKS_DATAFORMAT_VIDEOINFO_PALETTE
title: tagKS_DATAFORMAT_VIDEOINFO_PALETTE
author: windows-driver-content
description: The KS_DATAFORMAT_VIDEOINFO_PALETTE structure describes color palette information.
old-location: stream\ks_dataformat_videoinfo_palette.htm
ms.assetid: bc984f10-8eae-45f7-9ab0-637b35e57e3c
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: stream
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_DATAFORMAT_VIDEOINFO_PALETTE
req.alt-loc: ksmedia.h
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
ms.keywords: tagKS_DATAFORMAT_VIDEOINFO_PALETTE, KS_DATAFORMAT_VIDEOINFO_PALETTE, *PKS_DATAFORMAT_VIDEOINFO_PALETTE
req.iface: 
---

# tagKS_DATAFORMAT_VIDEOINFO_PALETTE structure



## -description
<p>The KS_DATAFORMAT_VIDEOINFO_PALETTE structure describes color palette information.</p>


## -syntax

````
typedef struct tagKS_DATAFORMAT_VIDEOINFO_PALETTE {
  KSDATAFORMAT DataFormat;
  KS_VIDEOINFO VideoInfo;
} KS_DATAFORMAT_VIDEOINFO_PALETTE, *PKS_DATAFORMAT_VIDEOINFO_PALETTE;
````


## -struct-fields
<dl>

### -field <b>DataFormat</b>

<dd>
<p>Specifies the data format that is being proposed.</p>
</dd>

### -field <b>VideoInfo</b>

<dd>
<p>Specifies the details of the video stream.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567698">KS_VIDEOINFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATAFORMAT_VIDEOINFO_PALETTE structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
