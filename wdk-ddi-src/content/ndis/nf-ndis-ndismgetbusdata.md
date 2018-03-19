---
UID: NF:ndis.NdisMGetBusData
title: NdisMGetBusData function
author: windows-driver-content
description: NDIS drivers call the NdisMGetBusData function to read the configuration space of a device.
old-location: netvista\ndismgetbusdata.htm
old-project: netvista
ms.assetid: 495191f4-a5c6-4223-8c5d-e4c0ecb0cc5d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMGetBusData, NdisMGetBusData function [Network Drivers Starting with Windows Vista], hardware_configuration_ref_e2ffab8c-2dba-4b49-a7dc-246a4792ca43.xml, ndis/NdisMGetBusData, netvista.ndismgetbusdata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMGetBusData
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMGetBusData function
NDIS drivers call the 
  <b>NdisMGetBusData</b> function to read the configuration space of a device.

## Syntax

````
ULONG NdisMGetBusData(
  _In_  NDIS_HANDLE MiniportAdapterHandle,
  _In_  ULONG       WhichSpace,
  _In_  ULONG       Offset,
  _Out_ PVOID       Buffer,
  _In_  ULONG       Length
);
````

## Parameters

`NdisMiniportHandle`

TBD

`WhichSpace`

The type of bus data to be read. For further information, see the discussion of the 
     <i>WhichSpace</i> parameter on the reference page for 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a>.

`Offset`

The byte offset in the configuration space, specified by 
     <i>WhichSpace</i>, from which data is read.

`Buffer`

A pointer to a buffer that receives the data read from the bus. Must be at least as large as 
     <i>Length</i> .

`Length`

The length, in bytes, of the data to read.


## Return Value

<b>NdisMGetBusData</b> returns the number of bytes read.

## Remarks

This function replaces the NDIS 5.1 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff554554">NdisReadPciSlotInformation</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndismsetbusdata.md">NdisMSetBusData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>