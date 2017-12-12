---
UID: NF.ks.KsHandleSizedListQuery
title: KsHandleSizedListQuery function
author: windows-driver-content
description: The KsHandleSizedListQuery function, depending on the length of the system buffer, returns either the size of the buffer needed, number of entries in the specified data list, or copies the entries themselves.
old-location: stream\kshandlesizedlistquery.htm
old-project: stream
ms.assetid: 014ca1bd-6e18-4110-aefb-ec36e816f013
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsHandleSizedListQuery
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
req.alt-api: KsHandleSizedListQuery
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

# KsHandleSizedListQuery function



## -description
The <b>KsHandleSizedListQuery</b> function, depending on the length of the system buffer, returns either the size of the buffer needed, number of entries in the specified data list, or copies the entries themselves. This assumes the structure of KSMULTIPLE_ITEM to be a Size followed by a Count.



## -syntax

````
NTSTATUS KsHandleSizedListQuery(
  _In_       PIRP  Irp ,
  _In_       ULONG DataItemsCount ,
  _In_       ULONG DataItemSize ,
  _In_ const VOID  *DataItems 
);
````


## -parameters

### -param Irp  [in]

Specifies the IRP with the identifier list request.


### -param DataItemsCount  [in]

Specifies the number of items in the identifier list.


### -param DataItemSize  [in]

Specifies the size of a data item.


### -param DataItems  [in]

Specifies the list of data items.


## -returns
The <b>KsHandleSizedListQuery</b> function returns STATUS_SUCCESS if the number of entries and the data can be copied. If the buffer is larger than the size to store just the size and the count of entries but too small to contain all the entries, the function returns status STATUS_BUFFER_TOO_SMALL.


## -remarks
Use the <b>KsHandleSizedListQuery</b> function when implementing properties that are to return information in the multiple item format.


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