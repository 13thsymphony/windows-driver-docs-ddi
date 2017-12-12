---
UID: NF.ks.KsTopologyPropertyHandler
title: KsTopologyPropertyHandler function
author: windows-driver-content
description: The KsTopologyPropertyHandler function performs standard handling of the static members of the KSPROPSETID_Topology Property Set. The function uses the KSTOPOLOGY structure, which describes the set of information that is returned by this property set.
old-location: stream\kstopologypropertyhandler.htm
old-project: stream
ms.assetid: fe033614-b1a0-490b-b45b-a8d8de650dbf
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsTopologyPropertyHandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsTopologyPropertyHandler
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
---

# KsTopologyPropertyHandler function



## -description
The <b>KsTopologyPropertyHandler</b> function performs standard handling of the static members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566598">KSPROPSETID_Topology</a> Property Set. The function uses the <a href="stream.kstopology">KSTOPOLOGY</a> structure, which describes the set of information that is returned by this property set.



## -syntax

````
NTSTATUS KsTopologyPropertyHandler(
  _In_          PIRP        Irp,
  _In_          PKSPROPERTY Property,
  _Inout_       PVOID       Data,
  _In_    const KSTOPOLOGY  *Topology
);
````


## -parameters

### -param Irp [in]

Specifies the IRP handling the property request.


### -param Property [in]

Specifies the specific property being queried.


### -param Data [in, out]

Specifies the topology property-specific data.


### -param Topology [in]

Points to a <a href="stream.kstopology">KSTOPOLOGY</a> structure containing the topology information.


## -returns
The <b>KsTopologyPropertyHandler</b> function returns STATUS_SUCCESS if successful, or it returns an error specific to the property being handled. The function always fills in the IO_STATUS_BLOCK.Information field of the PIRP.IoStatus element within the IRP. It does not set the IO_STATUS_BLOCK.Status field, nor does it complete the IRP. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
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
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>