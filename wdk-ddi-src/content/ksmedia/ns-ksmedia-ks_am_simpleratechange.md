---
UID: NS:ksmedia.KS_AM_SimpleRateChange
title: KS_AM_SimpleRateChange
author: windows-driver-content
description: The KS_AM_SimpleRateChange structure is used to describe a simple rate change (fast-forward or rewind) for an MPEG2 stream.
old-location: stream\ks_am_simpleratechange.htm
old-project: stream
ms.assetid: d797b377-6c27-41f9-932d-264d0e8b5dd0
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_AM_SimpleRateChange, KS_AM_SimpleRateChange, KS_AM_SimpleRateChange structure [Streaming Media Devices], PKS_AM_SimpleRateChange, PKS_AM_SimpleRateChange structure pointer [Streaming Media Devices], dvdref_8c318967-5f7d-4597-ab40-924e95b86dd7.xml, ksmedia/KS_AM_SimpleRateChange, ksmedia/PKS_AM_SimpleRateChange, stream.ks_am_simpleratechange"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KS_AM_SimpleRateChange
product: Windows
targetos: Windows
req.typenames: KS_AM_SimpleRateChange, *PKS_AM_SimpleRateChange
---

# KS_AM_SimpleRateChange structure
The KS_AM_SimpleRateChange structure is used to describe a simple rate change (fast-forward or rewind) for an MPEG2 stream.

## Syntax
````
typedef struct {
  REFERENCE_TIME StartTime;
  LONG           Rate;
} KS_AM_SimpleRateChange, *PKS_AM_SimpleRateChange;
````

## Members


`Rate`

Specifies the new rate. This value is multiplied by 10000 (decimal).

`StartTime`

Indicates the stream time at which to start this rate.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567288">KS_AM_RATE_SimpleRateChange</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_AM_SimpleRateChange structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>