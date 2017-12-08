---
UID: NS.BDATYPES._BDA_TEMPLATE_CONNECTION
title: _BDA_TEMPLATE_CONNECTION
author: windows-driver-content
description: The BDA_TEMPLATE_CONNECTION structure describes the template for a BDA connection in terms of where it begins and ends.
old-location: stream\bda_template_connection.htm
old-project: stream
ms.assetid: f3b5d06d-0557-49a8-9c0d-be964203108a
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _BDA_TEMPLATE_CONNECTION, BDA_TEMPLATE_CONNECTION, *PBDA_TEMPLATE_CONNECTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
req.include-header: Bdatypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BDA_TEMPLATE_CONNECTION
req.alt-loc: bdatypes.h
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
---

# _BDA_TEMPLATE_CONNECTION structure



## -description
The BDA_TEMPLATE_CONNECTION structure describes the template for a BDA connection in terms of where it begins and ends. 


## -syntax

````
typedef struct _BDA_TEMPLATE_CONNECTION {
  ULONG FromNodeType;
  ULONG FromNodePinType;
  ULONG ToNodeType;
  ULONG ToNodePinType;
} BDA_TEMPLATE_CONNECTION, *PBDA_TEMPLATE_CONNECTION;
````


## -struct-fields

### -field FromNodeType

Index of the element in the zero-based array of internal node types (KSNODE_DESCRIPTOR array) that indicates the node type where the connection begins or −1 to indicate that the connection begins at an upstream filter. 

### -field FromNodePinType

Index of the element in the zero-based array of pin types (KSPIN_DESCRIPTOR_EX array) that indicates the pin type where the connection begins. The array of pin types is the list of pin types that are available in the filter's template topology. 

### -field ToNodeType

Index of the element in the zero-based array of internal node types (KSNODE_DESCRIPTOR array) that indicates the node type where the connection ends or −1 to indicate that the connection ends at a downstream filter. 

### -field ToNodePinType

Index of the element in the zero-based array of pin types (KSPIN_DESCRIPTOR_EX array) that indicates the pin type where the connection ends. The array of pin types is the list of pin types that are available in the filter's template topology. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Bdatypes.h (include Bdatypes.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.bda_pin_pairing">BDA_PIN_PAIRING</a>
</dt>
<dt>
<a href="stream.bdapropertytemplateconnections">BdaPropertyTemplateConnections</a>
</dt>
<dt>
<a href="stream.ksnode_descriptor">KSNODE_DESCRIPTOR</a>
</dt>
<dt>
<a href="stream.kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>
</dt>
<dt>
<a href="stream.kstopology_connection">KSTOPOLOGY_CONNECTION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BDA_TEMPLATE_CONNECTION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
