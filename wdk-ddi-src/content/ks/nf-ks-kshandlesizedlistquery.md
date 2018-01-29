---
UID : NF:ks.KsHandleSizedListQuery
title : KsHandleSizedListQuery function
author : windows-driver-content
description : The KsHandleSizedListQuery function, depending on the length of the system buffer, returns either the size of the buffer needed, number of entries in the specified data list, or copies the entries themselves.
old-location : stream\kshandlesizedlistquery.htm
old-project : stream
ms.assetid : 014ca1bd-6e18-4110-aefb-ec36e816f013
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.kshandlesizedlistquery, KsHandleSizedListQuery function [Streaming Media Devices], ksfunc_31d10c58-ce60-43ca-aae7-27a0bd83d2e2.xml, KsHandleSizedListQuery, ks/KsHandleSizedListQuery
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ks.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : 
---


# KsHandleSizedListQuery function
The <b>KsHandleSizedListQuery</b> function, depending on the length of the system buffer, returns either the size of the buffer needed, number of entries in the specified data list, or copies the entries themselves. This assumes the structure of KSMULTIPLE_ITEM to be a Size followed by a Count.

## Syntax

````
NTSTATUS KsHandleSizedListQuery(
  _In_       PIRP  Irp ,
  _In_       ULONG DataItemsCount ,
  _In_       ULONG DataItemSize ,
  _In_ const VOID  *DataItems 
);
````

## Parameters

`Irp`

Specifies the IRP with the identifier list request.

`DataItemsCount`

Specifies the number of items in the identifier list.

`DataItemSize`

Specifies the size of a data item.

`DataItems`

Specifies the list of data items.


## Return Value

The <b>KsHandleSizedListQuery</b> function returns STATUS_SUCCESS if the number of entries and the data can be copied. If the buffer is larger than the size to store just the size and the count of entries but too small to contain all the entries, the function returns status STATUS_BUFFER_TOO_SMALL.

## Remarks

Use the <b>KsHandleSizedListQuery</b> function when implementing properties that are to return information in the multiple item format.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |