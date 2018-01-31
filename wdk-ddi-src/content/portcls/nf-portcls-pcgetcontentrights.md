---
UID : NF:portcls.PcGetContentRights
title : PcGetContentRights function
author : windows-driver-content
description : The PcGetContentRights function retrieves the DRM content rights assigned to a DRM content ID. Note that this function call is identical in operation to the DrmGetContentRights function, and its parameter definitions and return value are also identical.
old-location : audio\pcgetcontentrights.htm
old-project : audio
ms.assetid : a4e8aee0-d3ac-4086-99a3-a0339b198372
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : audio.pcgetcontentrights, PcGetContentRights, portcls/PcGetContentRights, audpc-routines_0f94b5f4-2667-488d-a191-4cf13a1f3a27.xml, PcGetContentRights function [Audio Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : portcls.h
req.include-header : Portcls.h
req.target-type : Universal
req.target-min-winverclnt : The PortCls system driver implements the PcGetContentRights function in Microsoft Windows XP and later operating systems.
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
req.lib : Portcls.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# PcGetContentRights function
The <b>PcGetContentRights</b> function retrieves the DRM content rights assigned to a DRM content ID. Note that this function call is identical in operation to the <a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a> function, and its parameter definitions and return value are also identical.

## Syntax

````
PORTCLASSAPI NTSTATUS NTAPI  PcGetContentRights(void);
````

## Parameters

`ContentId`

TBD

`DrmRights`

TBD


## Return Value

See return value definition in <a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a>.

## Remarks

For more information, see the comments in <a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | portcls.h (include Portcls.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcGetContentRights function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>