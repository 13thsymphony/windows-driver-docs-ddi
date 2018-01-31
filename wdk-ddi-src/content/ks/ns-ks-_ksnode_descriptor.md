---
UID : NS:ks._KSNODE_DESCRIPTOR
title : "_KSNODE_DESCRIPTOR"
author : windows-driver-content
description : The KSNODE_DESCRIPTOR structure describes a topology node within a filter.
old-location : stream\ksnode_descriptor.htm
old-project : stream
ms.assetid : dfc5760f-fdd6-45f3-aeac-4406892e518a
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.ksnode_descriptor, ks/KSNODE_DESCRIPTOR, _KSNODE_DESCRIPTOR, PKSNODE_DESCRIPTOR structure pointer [Streaming Media Devices], KSNODE_DESCRIPTOR structure [Streaming Media Devices], KSNODE_DESCRIPTOR, PKSNODE_DESCRIPTOR, *PKSNODE_DESCRIPTOR, avstruct_c4e79318-e112-4f57-ad6f-58e71ec53532.xml, ks/PKSNODE_DESCRIPTOR
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ks.h
req.include-header : Ks.h
req.target-type : Windows
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
req.typenames : KSNODE_DESCRIPTOR, *PKSNODE_DESCRIPTOR
---

# _KSNODE_DESCRIPTOR structure
The KSNODE_DESCRIPTOR structure describes a topology node within a filter.

## Syntax
````
typedef struct _KSNODE_DESCRIPTOR {
  const KSAUTOMATION_TABLE *AutomationTable;
  const GUID               *Type;
  const GUID               *Name;
} KSNODE_DESCRIPTOR, *PKSNODE_DESCRIPTOR;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-_ksfilter_descriptor.md">KSFILTER_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSNODE_DESCRIPTOR structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>