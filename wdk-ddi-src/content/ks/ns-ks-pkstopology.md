---
UID: NS.KS.PKSTOPOLOGY
title: PKSTOPOLOGY
author: windows-driver-content
description: The KSTOPOLOGY structure describes the topology of pins and nodes.
old-location: stream\kstopology.htm
old-project: stream
ms.assetid: 8dbd37ed-5d71-43bd-a3ca-caa5b0d08075
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSTOPOLOGY, *PKSTOPOLOGY, KSTOPOLOGY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSTOPOLOGY
req.alt-loc: ks.h
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
---

# PKSTOPOLOGY structure



## -description
The KSTOPOLOGY structure describes the topology of pins and nodes.



## -syntax

````
typedef struct {
  ULONG                       CategoriesCount;
  const GUID                  *Categories;
  ULONG                       TopologyNodesCount;
  const GUID                  *TopologyNodes;
  ULONG                       TopologyConnectionsCount;
  const KSTOPOLOGY_CONNECTION *TopologyConnections;
  const GUID                  *TopologyNodesNames;
  ULONG                       Reserved;
} KSTOPOLOGY, *PKSTOPOLOGY;
````


## -struct-fields

### -field CategoriesCount

Specifies the number of functional categories that the driver supports.


### -field Categories

Points to the beginning of the array of functional categories that the driver supports.


### -field TopologyNodesCount

Specifies the number of nodes that the driver supports.


### -field TopologyNodes

Points to the beginning of the array of GUIDs that describe the type of each node. For a list of video kernel streaming related nodes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560886">Kernel Streaming Topology Nodes</a>. For a list of audio kernel streaming related nodes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536219">Audio Topology Nodes</a>.


### -field TopologyConnectionsCount

Specifies the number of entries in the array pointed to by <b>TopologyConnections</b>. The node numbers of each entry must correspond to the array offset of the node within <b>TopologyNodes</b>. When this structure is a part of a streaming minidriver's <a href="stream.hw_stream_header">HW_STREAM_HEADER</a>, the pin numbers must correspond to the offsets within the array of <a href="stream.hw_stream_information">HW_STREAM_INFORMATION</a> structures in the minidriver's <a href="stream.hw_stream_descriptor">HW_STREAM_DESCRIPTOR</a> structure.


### -field TopologyConnections

Points to the beginning of the array of topology connections for this structure.


### -field TopologyNodesNames

Specifies the GUID of the localized Unicode string name for the node, stored in the registry.


### -field Reserved

Reserved for system use. Drivers should set this to zero.


## -remarks
A stream class minidriver creates and passes this structure as part of its <a href="stream.hw_stream_header">HW_STREAM_HEADER</a> structure. The class driver uses this structure to process topology property requests. The property data that the class driver returns is determined from the KSTOPOLOGY structure as follows:



Returns the array that begins at the <b>Categories</b> member of KSTOPOLOGY.

Returns the array that begins at the <b>TopologyConnections</b> member of KSTOPOLOGY.

Returns the array that begins at the <b>Nodes</b> member of KSTOPOLOGY.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.hw_stream_header">HW_STREAM_HEADER</a>
</dt>
<dt>
<a href="stream.hw_stream_information">HW_STREAM_INFORMATION</a>
</dt>
<dt>
<a href="stream.hw_stream_descriptor">HW_STREAM_DESCRIPTOR</a>
</dt>
<dt>
<a href="stream.kstopology_connection">KSTOPOLOGY_CONNECTION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSTOPOLOGY structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

