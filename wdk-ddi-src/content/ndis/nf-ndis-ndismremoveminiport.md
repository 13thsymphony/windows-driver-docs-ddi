---
UID : NF:ndis.NdisMRemoveMiniport
title : NdisMRemoveMiniport function
author : windows-driver-content
description : The NdisMRemoveMiniport function removes the specified miniport driver adapter that the miniport driver has determined is unrecoverable from the system.
old-location : netvista\ndismremoveminiport.htm
old-project : netvista
ms.assetid : 70745b03-f9a3-4398-b41a-dc75bd16ffe0
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : NdisMRemoveMiniport
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported in NDIS 5.1, and NDIS 6.0 and later. For NDIS 5.1 drivers, see    NdisMRemoveMiniport (NDIS   5.1).
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NdisMRemoveMiniport
req.alt-loc : ndis.lib,ndis.dll
req.ddi-compliance : Irql_Miniport_Driver_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : <= DISPATCH_LEVEL
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMRemoveMiniport function
The
  <b>NdisMRemoveMiniport</b> function removes the specified miniport driver adapter that the miniport driver
  has determined is unrecoverable from the system.

## Syntax

````
NDIS_STATUS NdisMRemoveMiniport(
  _In_ NDIS_HANDLE MiniportAdapterHandle
);
````

## Parameters

`MiniportHandle`




## Return Value

<b>NdisMRemoveMiniport</b> can return either of the following:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The miniport adapter has been removed.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>An attempt to remove the miniport adapter failed.

## Remarks

If a miniport driver has determined that a particular miniport adapter has failed and is
    unrecoverable, the miniport driver can call 
    <b>NdisMRemoveMiniport</b> to remove the miniport adapter from the local computer system. In this call,
    the miniport driver passes the handle to the miniport adapter to remove.

For example, if a miniport driver detects that a miniport adapter is resetting very frequently and is
    causing the computer to freeze every few seconds, the driver can request NDIS to remove the miniport
    adapter.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** | Irql_Miniport_Driver_Function |