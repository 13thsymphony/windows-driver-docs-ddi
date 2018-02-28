---
UID: NS:ksmedia.tagKS_AMVPSIZE
title: tagKS_AMVPSIZE
author: windows-driver-content
description: The KS_AMVPSIZE structure is used to describe the dimension of a video port (width by height).
old-location: stream\ks_amvpsize.htm
old-project: stream
ms.assetid: 31430419-8f83-4f46-b398-841895f415d5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_AMVPSIZE, KS_AMVPSIZE, KS_AMVPSIZE structure [Streaming Media Devices], PKS_AMVPSIZE, PKS_AMVPSIZE structure pointer [Streaming Media Devices], dvdref_fa534150-3678-4def-945b-59d23ea84e83.xml, ksmedia/KS_AMVPSIZE, ksmedia/PKS_AMVPSIZE, stream.ks_amvpsize, tagKS_AMVPSIZE"
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
-	KS_AMVPSIZE
product: Windows
targetos: Windows
req.typenames: KS_AMVPSIZE, *PKS_AMVPSIZE
---

# tagKS_AMVPSIZE structure
The KS_AMVPSIZE structure is used to describe the dimension of a video port (width by height).

## Syntax
````
typedef struct tagKS_AMVPSIZE {
  DWORD dwWidth;
  DWORD dwHeight;
} KS_AMVPSIZE, *PKS_AMVPSIZE;
````

## Members


`dwHeight`

Specifies the height of the video port, in pixels.

`dwWidth`

Specifies the width of the video port, in pixels.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566502">KSPROPERTY_VPCONFIG_SCALEFACTOR</a> property.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566502">KSPROPERTY_VPCONFIG_SCALEFACTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_AMVPSIZE structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>