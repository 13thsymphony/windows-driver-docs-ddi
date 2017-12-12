---
UID: NS.KSMEDIA.TAGKS_DATAFORMAT_VIDEOINFOHEADER2
title: tagKS_DATAFORMAT_VIDEOINFOHEADER2
author: windows-driver-content
description: The KS_DATAFORMAT_VIDEOINFOHEADER2 structure describes a video stream that includes settings for bob or weave.
old-location: stream\ks_dataformat_videoinfoheader2.htm
old-project: stream
ms.assetid: 92deaecd-69d7-4e64-bdb0-a2736add0c2f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: tagKS_DATAFORMAT_VIDEOINFOHEADER2, KS_DATAFORMAT_VIDEOINFOHEADER2, *PKS_DATAFORMAT_VIDEOINFOHEADER2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_DATAFORMAT_VIDEOINFOHEADER2
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
---

# tagKS_DATAFORMAT_VIDEOINFOHEADER2 structure



## -description
The KS_DATAFORMAT_VIDEOINFOHEADER2 structure describes a video stream that includes settings for bob or weave.



## -syntax

````
typedef struct tagKS_DATAFORMAT_VIDEOINFOHEADER2 {
  KSDATAFORMAT        DataFormat;
  KS_VIDEOINFOHEADER2 VideoInfoHeader2;
} KS_DATAFORMAT_VIDEOINFOHEADER2, *PKS_DATAFORMAT_VIDEOINFOHEADER2;
````


## -struct-fields

### -field DataFormat

Specifies the data format.


### -field VideoInfoHeader2

Specifies the details of the video stream, including options for specifying bob or weave settings.


## -remarks
Minidrivers that do not need to specify bob or weave settings may use the <a href="stream.ks_dataformat_videoinfoheader">KS_DATAFORMAT_VIDEOINFOHEADER</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Header

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
<a href="stream.ks_videoinfoheader">KS_VIDEOINFOHEADER</a>
</dt>
<dt>
<a href="stream.ks_videoinfoheader2">KS_VIDEOINFOHEADER2</a>
</dt>
<dt>
<a href="stream.ksdataformat">KSDATAFORMAT</a>
</dt>
<dt>
<a href="stream.ks_dataformat_videoinfoheader">KS_DATAFORMAT_VIDEOINFOHEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATAFORMAT_VIDEOINFOHEADER2 structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

