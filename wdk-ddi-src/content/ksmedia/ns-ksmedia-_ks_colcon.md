---
UID: NS:ksmedia._KS_COLCON
title: "_KS_COLCON"
author: windows-driver-content
description: The KS_COLCON structure is used to describe color and contrast settings.
old-location: stream\ks_colcon.htm
old-project: stream
ms.assetid: 8328c1b1-e72d-4e34-b69e-e02b3f5850bf
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "_KS_COLCON, stream.ks_colcon, KS_COLCON structure [Streaming Media Devices], *PKS_COLCON, KS_COLCON, PKS_COLCON, PKS_COLCON structure pointer [Streaming Media Devices], ksmedia/PKS_COLCON, ksmedia/KS_COLCON, dvdref_96e0b7a1-6131-445b-9a4f-9157997338aa.xml"
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
-	KS_COLCON
product: Windows
targetos: Windows
req.typenames: "*PKS_COLCON, KS_COLCON"
---

# _KS_COLCON structure
The KS_COLCON structure is used to describe color and contrast settings.

## Syntax
````
typedef struct _KS_COLCON {
  UCHAR emph1col  :4;
  UCHAR emph2col  :4;
  UCHAR backcol  :4;
  UCHAR patcol  :4;
  UCHAR emph1con  :4;
  UCHAR emph2con  :4;
  UCHAR backcon  :4;
  UCHAR patcon  :4;
} KS_COLCON, *PKS_COLCON;
````

## Members


`backcol`

Indicates

`backcon`

Indicates

`emph1col`

Indicates

`emph1con`

Indicates

`emph2col`

Indicates

`emph2con`

Indicates

`patcol`

Indicates

`patcon`

Indicates

## Remarks
The KS_COLCON structure is used by the <a href="..\ksmedia\ns-ksmedia-_ksproperty_sphli.md">KSPROPERTY_SPHLI</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ksmedia\ns-ksmedia-_ksproperty_sphli.md">KSPROPERTY_SPHLI</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_COLCON structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>