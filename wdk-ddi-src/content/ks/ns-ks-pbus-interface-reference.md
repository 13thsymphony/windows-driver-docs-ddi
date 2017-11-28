---
UID: NS.ks.PBUS_INTERFACE_REFERENCE
title: PBUS_INTERFACE_REFERENCE
author: windows-driver-content
description: A software device enumerator exports this interface to allow drivers to reference count physical device objects (PDOs) such that the device remains active while in use and is unloaded when not in use.
old-location: stream\bus_interface_reference.htm
old-project: stream
ms.assetid: 17c2c46c-ff79-4c80-82c9-c49b18426789
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: PBUS_INTERFACE_REFERENCE, BUS_INTERFACE_REFERENCE, *PBUS_INTERFACE_REFERENCE
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
req.alt-api: BUS_INTERFACE_REFERENCE
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
req.iface: 
---

# PBUS_INTERFACE_REFERENCE structure



## -description
<p>A software device enumerator exports this interface to allow drivers to reference count physical device objects (PDOs) such that the device remains active while in use and is unloaded when not in use.</p>


## -syntax

````
typedef struct {
  INTERFACE                  Interface;
  PFNREFERENCEDEVICEOBJECT   ReferenceDeviceObject;
  PFNDEREFERENCEDEVICEOBJECT DereferenceDeviceObject;
  PFNQUERYREFERENCESTRING    QueryReferenceString;
} BUS_INTERFACE_REFERENCE, *PBUS_INTERFACE_REFERENCE;
````


## -struct-fields
<dl>

### -field <b>Interface</b>

<dd>
<p>Specifies the exported <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a>.</p>
</dd>

### -field <b>ReferenceDeviceObject</b>

<dd>
<p>Pointer to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff567198">KStrReferenceDeviceObject</a> routine.</p>
</dd>

### -field <b>DereferenceDeviceObject</b>

<dd>
<p>Pointer to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff567170">KStrDereferenceDeviceObject</a> routine.</p>
</dd>

### -field <b>QueryReferenceString</b>

<dd>
<p>Pointer to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff567193">KStrQueryReferenceString</a> routine.</p>
</dd>
</dl>

## -remarks
<p>A driver obtains a BUS_INTERFACE_REFERENCE interface by creating and sending an IRP_MJ_PNP request that specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> minor function code. To do this, the driver should:</p>

<p>Allocate and zero-fill a BUS_INTERFACE_REFERENCE structure from the paged memory pool.</p>

<p>Create an IRP for the query interface request and get the next stack location for the new IRP.</p>

<p>In the new stack location, provide a pointer to the new BUS_INTERFACE_REFERENCE structure in the <b>Parameters.QueryInterface.Interface</b> member.</p>

<p>Set a completion routine and send the request down the driver stack.</p>

<p>If your request is successful, the system fills in the BUS_INTERFACE_REFERENCE structure pointed to by <b>Parameters.QueryInterface.Interface</b>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>