---
UID: NF.swenum.KsGetBusEnumIdentifier
title: KsGetBusEnumIdentifier function
author: windows-driver-content
description: The KsGetBusEnumIdentifier function retrieves the software bus enumerator identifier for the bus device associated with the given IRP.
old-location: stream\ksgetbusenumidentifier.htm
old-project: stream
ms.assetid: 50e14e01-5879-4a84-a8c2-f03c953dbeec
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsGetBusEnumIdentifier
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: swenum.h
req.include-header: Swenum.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsGetBusEnumIdentifier
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
req.product: Windows 10 or later.
---

# KsGetBusEnumIdentifier function



## -description
<i>This function is intended for internal use only.</i>

The <b>KsGetBusEnumIdentifier</b> function retrieves the software bus enumerator identifier for the bus device associated with the given IRP. 



## -syntax

````
NTSTATUS KsGetBusEnumIdentifier(
  _Inout_ PIRP Irp
);
````


## -parameters

### -param Irp [in, out]

Pointer to the IRP that specifies the address and size of the user output buffer to receive the requested bus enumerator identifier.


## -returns
Returns STATUS_SUCCESS if the bus enumerator identifier was retrieved successfully. Otherwise, it returns one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The specified device is not valid
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The specified buffer was not large enough
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>No buffer was specified (the required buffer size is returned in the Irp).

 


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
<dt>Swenum.h (include Swenum.h)</dt>
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