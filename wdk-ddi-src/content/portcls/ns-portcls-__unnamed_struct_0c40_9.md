---
UID: NS:portcls.__unnamed_struct_0c40_9
title: PCFILTER_DESCRIPTOR
author: windows-driver-content
description: The PCFILTER_DESCRIPTOR structure describes a miniport driver's implementation of a filter. The structure specifies the filter's pins, nodes, connections, and properties.
old-location: audio\pcfilter_descriptor.htm
old-project: audio
ms.assetid: 11fd8fc0-98aa-4b06-973c-2b175144da42
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PCFILTER_DESCRIPTOR, PCFILTER_DESCRIPTOR, *PPCFILTER_DESCRIPTOR
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
req.alt-api: PCFILTER_DESCRIPTOR
req.alt-loc: portcls.h
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
req.typenames: PCFILTER_DESCRIPTOR, *PPCFILTER_DESCRIPTOR
---

# PCFILTER_DESCRIPTOR structure



## -description
The <b>PCFILTER_DESCRIPTOR</b> structure describes a miniport driver's implementation of a filter. The structure specifies the filter's pins, nodes, connections, and properties.



## -syntax

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


## -struct-fields

### -field Version

Reserved. Initialize to zero.


### -field AutomationTable

Pointer to the automation table. This is a structure of type <a href="..\portcls\ns-portcls-__unnamed_struct_0c40_6.md">PCAUTOMATION_TABLE</a>. The automation table specifies the handlers for the properties of the filter instance.


### -field PinSize

Specifies the size in bytes of each element in the <b>Pins</b> array. This value should be a multiple of eight and should be at least <b>sizeof</b>(<a href="..\portcls\ns-portcls-__unnamed_struct_0c40_7.md">PCPIN_DESCRIPTOR</a>). Larger values allow client-specific descriptor information to be appended to pin descriptors.


### -field PinCount

Specifies the number of pin descriptors in the <b>Pins</b> array.


### -field Pins

Pointer to the array of pin descriptors. Each array element is a <a href="..\portcls\ns-portcls-__unnamed_struct_0c40_7.md">PCPIN_DESCRIPTOR</a> structure.


### -field NodeSize

Specifies the size in bytes of each element in the <b>Nodes</b> array. This value should be a multiple of eight and should be at least <b>sizeof</b>(<a href="..\portcls\ns-portcls-__unnamed_struct_0c40_8.md">PCNODE_DESCRIPTOR</a>). Larger values allow client-specific descriptor information to be appended to node descriptors.


### -field NodeCount

Specifies the number of node descriptors in the <b>Nodes</b> array.


### -field Nodes

Pointer to the array of node descriptors. Each array element is a <a href="..\portcls\ns-portcls-__unnamed_struct_0c40_8.md">PCNODE_DESCRIPTOR</a> structure.


### -field ConnectionCount

Specifies the number of connections in the <b>Connections</b> array.


### -field Connections

Pointer to the array of connections descriptors. Each array element is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537688">PCCONNECTION_DESCRIPTOR</a> structure.


### -field CategoryCount

Specifies the number of GUIDs in the <b>Categories</b> array.


### -field Categories

Pointer to the array of GUIDs that specifies the categories that the object belongs to. See the discussion of topology categories in <a href="https://msdn.microsoft.com/824cc6a2-702a-4e51-91b1-ab776b1babf1">Installing Device Interfaces for an Audio Adapter</a>.


## -remarks
A port driver obtains the miniport driver's filter descriptor by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a> method. The filter descriptor is a <b>PCFILTER_DESCRIPTOR</b> structure describing the miniport driver's pins, nodes, connections, and properties. For more information, see <a href="https://msdn.microsoft.com/e0d52e97-459f-4095-9cf5-1474117ce66a">Filter, Pin, and Node Properties</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\ns-portcls-__unnamed_struct_0c40_6.md">PCAUTOMATION_TABLE</a>
</dt>
<dt>
<a href="..\portcls\ns-portcls-__unnamed_struct_0c40_7.md">PCPIN_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\portcls\ns-portcls-__unnamed_struct_0c40_8.md">PCNODE_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537688">PCCONNECTION_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PCFILTER_DESCRIPTOR structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

