---
UID: NS:ehstorioctl.tagSILO_COMMAND
title: tagSILO_COMMAND
author: windows-driver-content
description: This structure describes a storage silo driver command.
old-location: storage\silo_command.htm
old-project: storage
ms.assetid: 4d40ac4b-9aca-4be6-8d4f-db94c3daf4e8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: structs-silo_6058ee8b-c6ff-4e84-8b20-304bb6646a4f.xml, ehstorioctl/SILO_COMMAND, *PSILO_COMMAND, storage.silo_command, PSILO_COMMAND, tagSILO_COMMAND, PSILO_COMMAND structure pointer [Storage Devices], SILO_COMMAND structure [Storage Devices], ehstorioctl/PSILO_COMMAND, SILO_COMMAND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
-	EhStorIoctl.h
apiname:
-	SILO_COMMAND
product: Windows
targetos: Windows
req.typenames: "*PSILO_COMMAND, SILO_COMMAND"
---

# tagSILO_COMMAND structure
This structure describes a storage silo driver command.

## Syntax
````
typedef struct tagSILO_COMMAND {
  UCHAR SiloIndex;
  UCHAR Command;
  ULONG cbCommandBuffer;
  UCHAR rgbCommandBuffer[ANYSIZE_ARRAY];
} SILO_COMMAND, *PSILO_COMMAND;
````

## Members


`cbCommandBuffer`

This member contains the size of the 1667 command buffer.

`Command`

This member contains the 1667 command value.

`rgbCommandBuffer`



`SiloIndex`



## Remarks
Together, <b>cbCommandBufferSize</b> and <b>rgbCommandBuffer</b> members indicate the raw data payload for the silo command, and are sent as-is to the device. The structure of the data in this buffer is silo-dependent. The structure is assumed to be shared knowledge between the client issuing this IOCTL and the device firmware implementation of this particular silo.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ehstorioctl.h (include EhStorIoctl.h) |