---
UID: NS:portcls._PCSTREAMRESOURCE_DESCRIPTOR
title: "_PCSTREAMRESOURCE_DESCRIPTOR"
author: windows-driver-content
description: PCSTREAMRESOURCE_DESCRIPTOR defines the stream resource. Use PCSTREAMRESOURCE_DESCRIPTOR_INIT to correctly initialize this structure.
old-location: audio\pcstreamresource_descriptor.htm
old-project: audio
ms.assetid: 978D06FC-B5CC-409C-BE5D-CA4B53005D8C
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PPCSTREAMRESOURCE_DESCRIPTOR, PCSTREAMRESOURCE_DESCRIPTOR, PCSTREAMRESOURCE_DESCRIPTOR structure [Audio Devices], PPCSTREAMRESOURCE_DESCRIPTOR, PPCSTREAMRESOURCE_DESCRIPTOR structure pointer [Audio Devices], _PCSTREAMRESOURCE_DESCRIPTOR, audio.pcstreamresource_descriptor, portcls/PCSTREAMRESOURCE_DESCRIPTOR, portcls/PPCSTREAMRESOURCE_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Portcls.h
api_name:
-	PCSTREAMRESOURCE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: PCSTREAMRESOURCE_DESCRIPTOR, *PPCSTREAMRESOURCE_DESCRIPTOR
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


`Size`

This field is init to the size of the struct.

`Flags`

Reserved for future use. Set to zero.

`Pdo`

The physical device object of the stack that created this resource.

`Type`

The union of the different stream resource types.

`Resource`

#### Thread

Thread.



#### ResourceSet

Reserved for future use, set to NULL. Only device-scoped resources are supported at this time.

## Remarks
Stream resources are any resources used by the audio driver to process audio streams or ensure audio data flow. Two type of stream resources are supported: interrupts and driver-owned threads. Audio drivers should register a resource after creating the resource, and unregister the resource before deleted it.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | portcls.h |

## See Also

<a href="..\portcls\ne-portcls-_pcstreamresourcetype.md">PcStreamResourceType</a>