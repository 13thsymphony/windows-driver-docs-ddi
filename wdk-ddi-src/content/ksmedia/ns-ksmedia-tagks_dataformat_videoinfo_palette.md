---
UID: NS:ksmedia.tagKS_DATAFORMAT_VIDEOINFO_PALETTE
title: tagKS_DATAFORMAT_VIDEOINFO_PALETTE
author: windows-driver-content
description: The KS_DATAFORMAT_VIDEOINFO_PALETTE structure describes color palette information.
old-location: stream\ks_dataformat_videoinfo_palette.htm
old-project: stream
ms.assetid: bc984f10-8eae-45f7-9ab0-637b35e57e3c
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ksmedia/PKS_DATAFORMAT_VIDEOINFO_PALETTE, vidcapstruct_1c005432-ed48-43fb-b866-387903e45b93.xml, tagKS_DATAFORMAT_VIDEOINFO_PALETTE, KS_DATAFORMAT_VIDEOINFO_PALETTE, ksmedia/KS_DATAFORMAT_VIDEOINFO_PALETTE, PKS_DATAFORMAT_VIDEOINFO_PALETTE structure pointer [Streaming Media Devices], stream.ks_dataformat_videoinfo_palette, PKS_DATAFORMAT_VIDEOINFO_PALETTE, KS_DATAFORMAT_VIDEOINFO_PALETTE structure [Streaming Media Devices], *PKS_DATAFORMAT_VIDEOINFO_PALETTE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KS_DATAFORMAT_VIDEOINFO_PALETTE
product: Windows
targetos: Windows
req.typenames: "*PKS_DATAFORMAT_VIDEOINFO_PALETTE, KS_DATAFORMAT_VIDEOINFO_PALETTE"
---

# tagKS_DATAFORMAT_VIDEOINFO_PALETTE structure
The KS_DATAFORMAT_VIDEOINFO_PALETTE structure describes color palette information.

## Syntax
````
typedef struct tagKS_DATAFORMAT_VIDEOINFO_PALETTE {
  KSDATAFORMAT DataFormat;
  KS_VIDEOINFO VideoInfo;
} KS_DATAFORMAT_VIDEOINFO_PALETTE, *PKS_DATAFORMAT_VIDEOINFO_PALETTE;
````

## Members


`DataFormat`

Specifies the data format that is being proposed.

`VideoInfo`

Specifies the details of the video stream.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>



<a href="..\ksmedia\ns-ksmedia-tagks_videoinfo.md">KS_VIDEOINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATAFORMAT_VIDEOINFO_PALETTE structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>