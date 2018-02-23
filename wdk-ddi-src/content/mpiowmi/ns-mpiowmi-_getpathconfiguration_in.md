---
UID: NS:mpiowmi._GetPathConfiguration_IN
title: "_GetPathConfiguration_IN"
author: windows-driver-content
description: The GetPathConfiguration_IN structure is used to retrieve the per path device information.
old-location: storage\getpathconfiguration_in.htm
old-project: storage
ms.assetid: 38396f75-6bcf-493e-9aab-661db59637ae
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PGetPathConfiguration_IN, PGetPathConfiguration_IN structure pointer [Storage Devices], _GetPathConfiguration_IN, GetPathConfiguration_IN, mpiowmi/PGetPathConfiguration_IN, structs-scsibus_28444162-ae96-47fb-8857-562d52191bfe.xml, mpiowmi/GetPathConfiguration_IN, GetPathConfiguration_IN structure [Storage Devices], storage.getpathconfiguration_in, *PGetPathConfiguration_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
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
-	mpiowmi.h
apiname:
-	GetPathConfiguration_IN
product: Windows
targetos: Windows
req.typenames: GetPathConfiguration_IN, *PGetPathConfiguration_IN
---

# _GetPathConfiguration_IN structure
The GetPathConfiguration_IN structure is used to retrieve the per path device information.

## Syntax
````
typedef struct _GetPathConfiguration_IN {
  ULONGLONG PathID;
} GetPathConfiguration_IN, *PGetPathConfiguration_IN;
````

## Members


`PathID`

A 64-bitfield that specifies the path that is associated with the device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mpiowmi.h (include Mpiowmi.h) |