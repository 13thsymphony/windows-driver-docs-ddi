---
UID : NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_VALUE
title : tagKSCAMERA_EXTENDEDPROP_VALUE
author : windows-driver-content
description : The KSCAMERA_EXTENDEDPROP_VALUE structure is a data type union used to express an extended property value.
old-location : stream\kscamera_extendedprop_value.htm
old-project : stream
ms.assetid : E595C2BF-C3C8-4FE8-90B0-CD53524F4852
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : "*PKSCAMERA_EXTENDEDPROP_VALUE, ksmedia/KSCAMERA_EXTENDEDPROP_VALUE, tagKSCAMERA_EXTENDEDPROP_VALUE, ksmedia/PKSCAMERA_EXTENDEDPROP_VALUE, stream.kscamera_extendedprop_value, PKSCAMERA_EXTENDEDPROP_VALUE structure pointer [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_VALUE, KSCAMERA_EXTENDEDPROP_VALUE, KSCAMERA_EXTENDEDPROP_VALUE structure [Streaming Media Devices]"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : Ksmedia.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
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
req.typenames : "*PKSCAMERA_EXTENDEDPROP_VALUE, KSCAMERA_EXTENDEDPROP_VALUE"
---

# tagKSCAMERA_EXTENDEDPROP_VALUE structure
The <b>KSCAMERA_EXTENDEDPROP_VALUE</b> structure is a data type union used to express an extended property value.

## Syntax
````
typedef struct _KSCAMERA_EXTENDEDPROP_VALUE {
  union {
    double        dbl;
    ULONGLONG     ull;
    ULONG         ul;
    LARGE_INTEGER ratio;
    LONG          l;
    LONG          ll;
  } Value;
} KSCAMERA_EXTENDEDPROP_VALUE, *PKSCAMERA_EXTENDEDPROP_VALUE;
````

## Members


`Value`

The extended property value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_header.md">KSCAMERA_EXTENDEDPROP_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSCAMERA_EXTENDEDPROP_VALUE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>