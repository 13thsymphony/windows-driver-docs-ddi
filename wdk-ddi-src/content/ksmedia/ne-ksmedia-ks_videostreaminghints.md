---
UID : NE:ksmedia.KS_VideoStreamingHints
title : KS_VideoStreamingHints
author : windows-driver-content
description : The KS_VideoStreamingHints enumeration defines video compression hints.
old-location : stream\ks_videostreaminghints.htm
old-project : stream
ms.assetid : 06f26404-c955-4034-8dd3-ad641c7b8010
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KS_VideoStreamingHints, KS_VideoStreamingHints
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ksmedia.h
req.include-header : Ksmedia.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KS_VideoStreamingHints
req.alt-loc : ksmedia.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : KS_VideoStreamingHints
---

# KS_VideoStreamingHints Enumeration
The KS_VideoStreamingHints enumeration defines video compression hints.

## Syntax
````
typedef enum  { 
  KS_StreamingHint_FrameInterval   = 0x0100,
  KS_StreamingHint_KeyFrameRate    = 0x0200,
  KS_StreamingHint_PFrameRate      = 0x0400,
  KS_StreamingHint_CompQuality     = 0x0800,
  KS_StreamingHint_CompWindowSize  = 0x1000
} KS_VideoStreamingHints;
````

## Constants

<table>

<tr>
<td>KS_StreamingHint_CompQuality</td>
<td>Specifies compression that is based on compression quality.</td>
</tr>

<tr>
<td>KS_StreamingHint_CompWindowSize</td>
<td>Specifies compression that is based on compression window size.</td>
</tr>

<tr>
<td>KS_StreamingHint_FrameInterval</td>
<td>Specifies compression that is based on the interval between video frames.</td>
</tr>

<tr>
<td>KS_StreamingHint_KeyFrameRate</td>
<td>Specifies compression that is based on key frames.</td>
</tr>

<tr>
<td>KS_StreamingHint_PFrameRate</td>
<td>Specifies compression that is based on predicted frames.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |