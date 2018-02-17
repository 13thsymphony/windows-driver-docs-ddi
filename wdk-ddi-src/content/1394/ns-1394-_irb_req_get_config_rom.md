---
UID: NS:1394._IRB_REQ_GET_CONFIG_ROM
title: "_IRB_REQ_GET_CONFIG_ROM"
author: windows-driver-content
description: This structure contains the fields necessary for the bus driver to carry out a GetConfigRom request.
old-location: ieee\irb_req_get_config_rom.htm
old-project: IEEE
ms.assetid: 9C4EC9CA-3B7F-4611-BB96-A86C0FEDDF25
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: 1394/IRB_REQ_GET_CONFIG_ROM, IRB_REQ_GET_CONFIG_ROM structure [Buses], _IRB_REQ_GET_CONFIG_ROM, IEEE.irb_req_get_config_rom, IRB_REQ_GET_CONFIG_ROM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 
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
-	1394.h
apiname:
-	IRB_REQ_GET_CONFIG_ROM
product: Windows
targetos: Windows
req.typenames: IRB_REQ_GET_CONFIG_ROM
---

# _IRB_REQ_GET_CONFIG_ROM structure
This structure contains the fields necessary for the bus driver to carry out a GetConfigRom request.

## Syntax
````
typedef struct _IRB_REQ_GET_CONFIG_ROM {
  ULONG GenerationCount;
  PCROM ConfigRom;
  ULONG UnitDirectoryIndex;
  ULONG UnitDependentDirectoryIndex;
  ULONG VendorLeafIndex;
  ULONG ModelLeafIndex;
} IRB_REQ_GET_CONFIG_ROM;
````

## Members


`ConfigRom`

Receives a pointer to a <b>ConfigRom</b> object.

`GenerationCount`

Receives the generation of the bus for which the contents of this configuration ROM was retrieved.

`ModelLeafIndex`

Receives the index to the node's model textual leaf in the configuration ROM. This is an index to the <b>Entries</b> array in the <b>u.GetConfigRom.ConfigRom</b> structure.

`UnitDependentDirectoryIndex`

Receives the index to the node's unit dependent directory in its configuration ROM. This is an index to the <b>Entries</b> array in the <b>u.GetConfigRom.ConfigRom</b> structure.

`UnitDirectoryIndex`

Receives the index to the node's unit directory in its configuration ROM. This is an index to the <b>Entries</b> array in the <b>u.GetConfigRom.ConfigRom</b> structure.

`VendorLeafIndex`

Receives the index to the node's vendor textual leaf in the configuration ROM. This is an index to the <b>Entries</b> array in the <b>u.GetConfigRom.ConfigRom</b> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 1394.h |