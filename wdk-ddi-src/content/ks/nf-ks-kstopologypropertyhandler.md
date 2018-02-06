---
UID: NF:ks.KsTopologyPropertyHandler
title: KsTopologyPropertyHandler function
author: windows-driver-content
description: The KsTopologyPropertyHandler function performs standard handling of the static members of the KSPROPSETID_Topology Property Set. The function uses the KSTOPOLOGY structure, which describes the set of information that is returned by this property set.
old-location: stream\kstopologypropertyhandler.htm
old-project: stream
ms.assetid: fe033614-b1a0-490b-b45b-a8d8de650dbf
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.kstopologypropertyhandler, KsTopologyPropertyHandler, ksfunc_d007eab3-23b3-42ea-a1d9-b2be806cb4ea.xml, KsTopologyPropertyHandler function [Streaming Media Devices], ks/KsTopologyPropertyHandler
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsTopologyPropertyHandler
product: Windows
targetos: Windows
req.typenames: 
---


# KsTopologyPropertyHandler function
The <b>KsTopologyPropertyHandler</b> function performs standard handling of the static members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566598">KSPROPSETID_Topology</a> Property Set. The function uses the <a href="..\ks\ns-ks-kstopology.md">KSTOPOLOGY</a> structure, which describes the set of information that is returned by this property set.

## Syntax

````
NTSTATUS KsTopologyPropertyHandler(
  _In_          PIRP        Irp,
  _In_          PKSPROPERTY Property,
  _Inout_       PVOID       Data,
  _In_    const KSTOPOLOGY  *Topology
);
````

## Parameters

`Irp`

Specifies the IRP handling the property request.

`Property`

Specifies the specific property being queried.

`Data`

Specifies the topology property-specific data.

`Topology`

Points to a <a href="..\ks\ns-ks-kstopology.md">KSTOPOLOGY</a> structure containing the topology information.


## Return Value

The <b>KsTopologyPropertyHandler</b> function returns STATUS_SUCCESS if successful, or it returns an error specific to the property being handled. The function always fills in the IO_STATUS_BLOCK.Information field of the PIRP.IoStatus element within the IRP. It does not set the IO_STATUS_BLOCK.Status field, nor does it complete the IRP.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |