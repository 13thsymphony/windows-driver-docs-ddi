---
UID : NS:ksmedia._tagKSTOPOLOGY_ENDPOINTID
title : _tagKSTOPOLOGY_ENDPOINTID
author : windows-driver-content
description : The KSTOPOLOGY_ENDPOINTID structure specifies the name and the pin ID of a topology endpoint.
old-location : audio\kstopology_endpointid.htm
old-project : audio
ms.assetid : A84BE3D6-7D2A-4123-979B-F6E1CA8C8B23
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : PKSTOPOLOGY_ENDPOINTID structure pointer [Audio Devices], _tagKSTOPOLOGY_ENDPOINTID, ksmedia/KSTOPOLOGY_ENDPOINTID, KSTOPOLOGY_ENDPOINTID structure [Audio Devices], audio.kstopology_endpointid, PKSTOPOLOGY_ENDPOINTID, ksmedia/PKSTOPOLOGY_ENDPOINTID, *PKSTOPOLOGY_ENDPOINTID, KSTOPOLOGY_ENDPOINTID
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10,Windows 10 Mobile
req.target-min-winversvr : Windows Server 2016
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
req.typenames : KSTOPOLOGY_ENDPOINTID, *PKSTOPOLOGY_ENDPOINTID
---

# _tagKSTOPOLOGY_ENDPOINTID structure
The <b>KSTOPOLOGY_ENDPOINTID</b> structure specifies the name and the pin ID of a topology endpoint.

## Syntax
````
typedef struct _tagKSTOPOLOGY_ENDPOINTID {
  WCHAR TopologyName[MAX_PATH];
  ULONG PinId;
} KSTOPOLOGY_ENDPOINTID, *PKSTOPOLOGY_ENDPOINTID;
````

## Members


`PinId`

The pin ID of the topology endpoint.

`TopologyName`

The name of the topology endpoint.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h |

## See Also

<a href="..\ksmedia\ns-ksmedia-_tagkstopology_endpointidpair.md">KSTOPOLOGY_ENDPOINTIDPAIR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSTOPOLOGY_ENDPOINTID structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>