---
UID: NF:ndis.NdisMResetMiniport
title: NdisMResetMiniport function
author: windows-driver-content
description: A miniport driver calls the NdisMResetMiniport function to trigger a later reset operation from NDIS.
old-location: netvista\ndismresetminiport.htm
old-project: netvista
ms.assetid: 614C6E21-00D0-4F57-9E09-D1BAB166BA42
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisMResetMiniport, ndis/NdisMResetMiniport, NdisMResetMiniport function [Network Drivers Starting with Windows Vista], netvista.ndismresetminiport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMResetMiniport
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMResetMiniport function
A miniport driver calls the <b>NdisMResetMiniport</b> function to trigger a later reset operation from NDIS.

## Syntax

````
void NdisMResetMiniport(
  _In_ NDIS_HANDLE MiniportAdapterHandle
);
````

## Parameters

`MiniportAdapterHandle`

The miniport adapter handle that NDIS passed to the <i>MiniportAdapterHandle</i> parameter of <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.


## Return Value

This function does not return a value.

## Remarks

A miniport driver calls <b>NdisMResetMiniport</b> when it determines that the device requires a hardware reset.

As a result, NDIS schedules a work item for calling the miniport driver's <a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a> function asynchronously.

<b>NdisMResetMiniport</b> must be called at IRQL &lt;= DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |