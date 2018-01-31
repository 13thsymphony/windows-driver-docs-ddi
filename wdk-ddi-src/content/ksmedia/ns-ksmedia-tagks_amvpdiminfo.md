---
UID : NS:ksmedia.tagKS_AMVPDIMINFO
title : tagKS_AMVPDIMINFO
author : windows-driver-content
description : The KS_AMVPDIMINFO structure is used to describe the dimensions of a video port.
old-location : stream\ks_amvpdiminfo.htm
old-project : stream
ms.assetid : 5b8126ee-ba47-4eaf-887a-764e17a20e03
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KS_AMVPDIMINFO, PKS_AMVPDIMINFO structure pointer [Streaming Media Devices], ksmedia/PKS_AMVPDIMINFO, tagKS_AMVPDIMINFO, PKS_AMVPDIMINFO, KS_AMVPDIMINFO structure [Streaming Media Devices], dvdref_4c6b6231-a3ef-49a5-8b27-c7ba0062c53a.xml, ksmedia/KS_AMVPDIMINFO, *PKS_AMVPDIMINFO, stream.ks_amvpdiminfo
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : Ksmedia.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : KS_AMVPDIMINFO, *PKS_AMVPDIMINFO
---

# tagKS_AMVPDIMINFO structure
The KS_AMVPDIMINFO structure is used to describe the dimensions of a video port.

## Syntax
````
typedef struct tagKS_AMVPDIMINFO {
  DWORD dwFieldWidth;
  DWORD dwFieldHeight;
  DWORD dwVBIWidth;
  DWORD dwVBIHeight;
  RECT  rcValidRegion;
} KS_AMVPDIMINFO, *PKS_AMVPDIMINFO;
````

## Members


`dwFieldHeight`

Specifies the field height.

`dwFieldWidth`

Specifies the field width.

`dwVBIHeight`

Specifies the VBI data height.

`dwVBIWidth`

Specifies the VBI data width.

`rcValidRegion`

Describes a valid rectangle for data cropping.

## Remarks
This structure is used by the <a href="..\ksmedia\ns-ksmedia-tagks_amvpdatainfo.md">KS_AMVPDATAINFO</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ksmedia\ns-ksmedia-tagks_amvpdatainfo.md">KS_AMVPDATAINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_AMVPDIMINFO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>