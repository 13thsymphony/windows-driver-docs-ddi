---
UID: NS:wmistr.tagWNODE_EVENT_REFERENCE
title: tagWNODE_EVENT_REFERENCE
author: windows-driver-content
description: The WNODE_EVENT_REFERENCE structure contains information that WMI can use to query for an event that exceeds the event size limit set in the registry.
old-location: kernel\wnode_event_reference.htm
old-project: kernel
ms.assetid: 9dfe75e5-301e-4378-a2ad-f43676d8c208
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PWNODE_EVENT_REFERENCE, PWNODE_EVENT_REFERENCE, PWNODE_EVENT_REFERENCE structure pointer [Kernel-Mode Driver Architecture], WNODE_EVENT_REFERENCE, WNODE_EVENT_REFERENCE structure [Kernel-Mode Driver Architecture], kernel.wnode_event_reference, kstruct_d_cf8551b3-5506-4c02-b56a-a4836429d5e1.xml, tagWNODE_EVENT_REFERENCE, wmistr/PWNODE_EVENT_REFERENCE, wmistr/WNODE_EVENT_REFERENCE"
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
-	Wmistr.h
api_name:
-	WNODE_EVENT_REFERENCE
product:
- Windows
targetos: Windows
req.typenames: WNODE_EVENT_REFERENCE, *PWNODE_EVENT_REFERENCE
req.product: Windows 10 or later.
---

# tagWNODE_EVENT_REFERENCE structure
The <b>WNODE_EVENT_REFERENCE</b> structure contains information that WMI can use to query for an event that exceeds the event size limit set in the registry.

## Syntax
```
typedef struct tagWNODE_EVENT_REFERENCE {
  _WNODE_HEADER WnodeHeader;
  struct        _WNODE_HEADER;
  GUID          TargetGuid;
  ULONG         TargetDataBlockSize;
  union {
    ULONG TargetInstanceIndex;
    WCHAR TargetInstanceName[];
  } DUMMYUNIONNAME;
} *PWNODE_EVENT_REFERENCE, WNODE_EVENT_REFERENCE;
```

## Members


`WnodeHeader`

Is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566375">WNODE_HEADER</a> structure that contains information common to all <b>WNODE_<i>XXX</i></b> structures, such as the buffer size, the provider ID, the GUID that represents a data block associated with a request, and flags that provide information about the <b>WNODE_<i>XXX</i></b> data being passed or returned.

`TargetGuid`

Indicates the GUID that represents the event to query.

`TargetDataBlockSize`

Indicates the size of the event.

`DUMMYUNIONNAME`



## Remarks
If the amount of data for an event exceeds the maximum size set in the registry, a driver can generate a <b>WNODE_EVENT_REFERENCE</b> that specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566373">WNODE_EVENT_ITEM</a> that WMI can query to obtain the event. For more information about defining and generating WMI events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547139">Implementing WMI</a>.

The <b>ProviderId</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566375">WNODE_HEADER</a> structure for use in a <b>WNODE_EVENT_REFERENCE</b> structure should be initialized using <a href="https://msdn.microsoft.com/library/windows/hardware/ff550433">IoWMIDeviceObjectToProviderId</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wmistr.h (include Wmistr.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550433">IoWMIDeviceObjectToProviderId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566373">WNODE_EVENT_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566375">WNODE_HEADER</a>