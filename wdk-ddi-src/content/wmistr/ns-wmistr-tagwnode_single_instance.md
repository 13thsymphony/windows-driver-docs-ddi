---
UID: NS:wmistr.tagWNODE_SINGLE_INSTANCE
title: tagWNODE_SINGLE_INSTANCE
author: windows-driver-content
description: The WNODE_SINGLE_INSTANCE structure contains values for all data items in one instance of a data block.
old-location: kernel\wnode_single_instance.htm
old-project: kernel
ms.assetid: 03e922af-f42a-4801-adc5-fc7a0b90f4a7
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PWNODE_SINGLE_INSTANCE, PWNODE_SINGLE_INSTANCE, PWNODE_SINGLE_INSTANCE structure pointer [Kernel-Mode Driver Architecture], WNODE_SINGLE_INSTANCE, WNODE_SINGLE_INSTANCE structure [Kernel-Mode Driver Architecture], kernel.wnode_single_instance, kstruct_d_c6ae2ea3-5e64-466d-b479-02a9eea71b20.xml, tagWNODE_SINGLE_INSTANCE, wmistr/PWNODE_SINGLE_INSTANCE, wmistr/WNODE_SINGLE_INSTANCE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wmistr.h
req.include-header: Wmistr.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wmistr.h
api_name:
-	WNODE_SINGLE_INSTANCE
product: Windows
targetos: Windows
req.typenames: WNODE_SINGLE_INSTANCE, *PWNODE_SINGLE_INSTANCE
req.product: Windows 10 or later.
---

# tagWNODE_SINGLE_INSTANCE structure
The <b>WNODE_SINGLE_INSTANCE</b> structure contains values for all data items in one instance of a data block.

## Syntax
```
typedef struct tagWNODE_SINGLE_INSTANCE {
  _WNODE_HEADER WnodeHeader;
  struct        _WNODE_HEADER;
  ULONG         OffsetInstanceName;
  ULONG         InstanceIndex;
  ULONG         DataBlockOffset;
  ULONG         SizeDataBlock;
  UCHAR         VariableData[];
} *PWNODE_SINGLE_INSTANCE, WNODE_SINGLE_INSTANCE;
```

## Members


`WnodeHeader`

Is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566375">WNODE_HEADER</a> structure that contains information common to all <b>WNODE_<i>XXX</i></b> structures, such as the buffer size, the GUID that represents a data block associated with a request, and flags that provide information about the <b>WNODE_<i>XXX</i></b> data being passed or returned.

`OffsetInstanceName`

Indicates the offset from the beginning of this structure to the dynamic instance name of this instance, aligned on a USHORT boundary. This member is valid only if WNODE_FLAG_STATIC_INSTANCE_NAMES is clear in <b>WnodeHeader.Flags</b>. If the data block was registered with static instance names, WMI ignores <b>OffsetInstanceName</b>.

`InstanceIndex`

Indicates the index of an instance registered with static instance names. This member is valid only if WNODE_FLAG_STATIC_INSTANCE_NAMES is set in <b>WnodeHeader.Flags</b>. If the data block was registered with dynamic instance names, WMI ignores <b>InstanceIndex</b>.

`DataBlockOffset`

Indicates the offset from the beginning of this structure to the beginning of the instance.

`SizeDataBlock`

Indicates the size of the data block for this instance.

`VariableData`

Contains additional data, including the dynamic instance name if any, padding so the instance begins on an 8-byte boundary, and the instance of the data block to be returned.

## Remarks
WMI passes a <b>WNODE_SINGLE_INSTANCE</b> with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550831">IRP_MN_CHANGE_SINGLE_INSTANCE</a> request to set read/write data items in an instance of a data block. A driver can ignore values passed for read-only data items in the instance.

A driver fills in a <b>WNODE_SINGLE_INSTANCE</b> in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551718">IRP_MN_QUERY_SINGLE_INSTANCE</a> request or to generate an event that consists of a single instance.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wmistr.h (include Wmistr.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566373">WNODE_EVENT_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566375">WNODE_HEADER</a>