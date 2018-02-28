---
UID: NS:portcls.__unnamed_struct_0cec_9
title: PCFILTER_DESCRIPTOR
author: windows-driver-content
description: The PCFILTER_DESCRIPTOR structure describes a miniport driver's implementation of a filter. The structure specifies the filter's pins, nodes, connections, and properties.
old-location: audio\pcfilter_descriptor.htm
old-project: audio
ms.assetid: 11fd8fc0-98aa-4b06-973c-2b175144da42
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PPCFILTER_DESCRIPTOR, PPCFILTER_DESCRIPTOR structure pointer [Audio Devices], PCFILTER_DESCRIPTOR structure [Audio Devices], PCFILTER_DESCRIPTOR, audio.pcfilter_descriptor, portcls/PCFILTER_DESCRIPTOR, portcls/PPCFILTER_DESCRIPTOR, *PPCFILTER_DESCRIPTOR, audpc-struct_8413fa35-0c5e-436a-8b0d-b7b08bc73621.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: portcls.h
req.include-header: Portcls.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	portcls.h
apiname:
-	PCFILTER_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: PCFILTER_DESCRIPTOR, *PPCFILTER_DESCRIPTOR
---

# *PPCFILTER_DESCRIPTOR structure
The <b>PCFILTER_DESCRIPTOR</b> structure describes a miniport driver's implementation of a filter. The structure specifies the filter's pins, nodes, connections, and properties.

## Syntax
````
typedef struct {
  ULONG                         Version;
  const PCAUTOMATION_TABLE      *AutomationTable;
  ULONG                         PinSize;
  ULONG                         PinCount;
  const PCPIN_DESCRIPTOR        *Pins;
  ULONG                         NodeSize;
  ULONG                         NodeCount;
  const PCNODE_DESCRIPTOR       *Nodes;
  ULONG                         ConnectionCount;
  const PCCONNECTION_DESCRIPTOR *Connections;
  ULONG                         CategoryCount;
  const GUID                    *Categories;
} PCFILTER_DESCRIPTOR, *PPCFILTER_DESCRIPTOR;
````

## Members


## Remarks
A port driver obtains the miniport driver's filter descriptor by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a> method. The filter descriptor is a <b>PCFILTER_DESCRIPTOR</b> structure describing the miniport driver's pins, nodes, connections, and properties. For more information, see <a href="https://msdn.microsoft.com/e0d52e97-459f-4095-9cf5-1474117ce66a">Filter, Pin, and Node Properties</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | portcls.h (include Portcls.h) |

## See Also

<a href="..\portcls\ns-portcls-__unnamed_struct_0cec_8.md">PCNODE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537688">PCCONNECTION_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a>



<a href="..\portcls\ns-portcls-__unnamed_struct_0cec_7.md">PCPIN_DESCRIPTOR</a>



<a href="..\portcls\ns-portcls-__unnamed_struct_0cec_6.md">PCAUTOMATION_TABLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PCFILTER_DESCRIPTOR structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>