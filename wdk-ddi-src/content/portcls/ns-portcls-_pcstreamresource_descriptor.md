---
UID : NS:portcls._PCSTREAMRESOURCE_DESCRIPTOR
title : "_PCSTREAMRESOURCE_DESCRIPTOR"
author : windows-driver-content
description : PCSTREAMRESOURCE_DESCRIPTOR defines the stream resource. Use PCSTREAMRESOURCE_DESCRIPTOR_INIT to correctly initialize this structure.
old-location : audio\pcstreamresource_descriptor.htm
old-project : audio
ms.assetid : 978D06FC-B5CC-409C-BE5D-CA4B53005D8C
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : "_PCSTREAMRESOURCE_DESCRIPTOR, PPCSTREAMRESOURCE_DESCRIPTOR structure pointer [Audio Devices], portcls/PPCSTREAMRESOURCE_DESCRIPTOR, PCSTREAMRESOURCE_DESCRIPTOR, PPCSTREAMRESOURCE_DESCRIPTOR, portcls/PCSTREAMRESOURCE_DESCRIPTOR, PCSTREAMRESOURCE_DESCRIPTOR structure [Audio Devices], *PPCSTREAMRESOURCE_DESCRIPTOR, audio.pcstreamresource_descriptor"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : portcls.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PCSTREAMRESOURCE_DESCRIPTOR, *PPCSTREAMRESOURCE_DESCRIPTOR
---

# _PCSTREAMRESOURCE_DESCRIPTOR structure
PCSTREAMRESOURCE_DESCRIPTOR defines the stream resource. Use PCSTREAMRESOURCE_DESCRIPTOR_INIT to correctly initialize this structure.

## Syntax
````
typedef struct _PCSTREAMRESOURCE_DESCRIPTOR {
  ULONG                Size;
  ULONG                Flags;
  PDEVICE_OBJECT       Pdo;
  PcStreamResourceType Type;
  union {
    struc {
      ULONG Version;
      PVOID Generic;
    }     Interrupt;
    PETHREAD Thread;
    PVOID     ResourceSet;
  } Resource;
} PCSTREAMRESOURCE_DESCRIPTOR, *PPCSTREAMRESOURCE_DESCRIPTOR;
````

## Members


`Flags`

Reserved for future use. Set to zero.

`Pdo`

The physical device object of the stack that created this resource.

`Resource`



`Size`

This field is init to the size of the struct.

`Type`

The union of the different stream resource types.

## Remarks
Stream resources are any resources used by the audio driver to process audio streams or ensure audio data flow. Two type of stream resources are supported: interrupts and driver-owned threads. Audio drivers should register a resource after creating the resource, and unregister the resource before deleted it.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | portcls.h |

## See Also

<a href="..\portcls\ne-portcls-_pcstreamresourcetype.md">PcStreamResourceType</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PCSTREAMRESOURCE_DESCRIPTOR structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>