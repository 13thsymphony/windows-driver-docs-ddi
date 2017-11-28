---
UID: NS.hbapiwmi._MS_SMHBA_SAS_Port
title: MS_SMHBA_SAS_Port
author: windows-driver-content
description: The MS_SMHBA_SAS_Port structure is used to report the SAS port information.
old-location: storage\ms_smhba_sas_port.htm
old-project: storage
ms.assetid: d294d97a-e6b2-4ab3-bebf-e545aa2f862d
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: MS_SMHBA_SAS_Port, MS_SMHBA_SAS_Port, *PMS_SMHBA_SAS_Port
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MS_SMHBA_SAS_Port
req.alt-loc: hbapiwmi.h
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
req.iface: 
---

# MS_SMHBA_SAS_Port structure



## -description
<p>The MS_SMHBA_SAS_Port structure is used to report the SAS port information.</p>


## -syntax

````
typedef struct _MS_SMHBA_SAS_Port {
  ULONG PortProtocol;
  UCHAR LocalSASAddress[8];
  UCHAR AttachedSASAddress[8];
  ULONG NumberofDiscoveredPorts;
  ULONG NumberofPhys;
} MS_SMHBA_SAS_Port, *PMS_SMHBA_SAS_Port;
````


## -struct-fields
<dl>

### -field <b>PortProtocol</b>

<dd>
<p>The protocols that are supported by this SAS port.</p>
</dd>

### -field <b>LocalSASAddress</b>

<dd>
<p>The Port_Identifier of this SAS port</p>
</dd>

### -field <b>AttachedSASAddress</b>

<dd>
<p>The SAS address of the entity that is at the opposite end of the SAS link from this local SAS port.</p>
</dd>

### -field <b>NumberofDiscoveredPorts</b>

<dd>
<p>The number of end ports that are visible to the local SAS port. The discovered ports might also include SMP ports that are contained within SAS expander devices.</p>
</dd>

### -field <b>NumberofPhys</b>

<dd>
<p>The number of physical ports that are associated with this SAS port. If the value is more than one, this SAS port is considered to be a wide port.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>