---
UID: NF:dot11wdi.NdisMDeregisterWdiMiniportDriver
title: NdisMDeregisterWdiMiniportDriver function
author: windows-driver-content
description: A miniport driver calls the NdisMDeregisterWdiMiniportDriver function to release resources that it allocated with a previous call to the NdisMRegisterWdiMiniportDriver function.
old-location: netvista\ndismderegisterwdiminiportdriver.htm
old-project: netvista
ms.assetid: 6B2B0A88-9F63-4A68-894B-38424FBE161E
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMDeregisterWdiMiniportDriver, NdisMDeregisterWdiMiniportDriver function [Network Drivers Starting with Windows Vista], dot11wdi/NdisMDeregisterWdiMiniportDriver, netvista.ndismderegisterwdiminiportdriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMDeregisterWdiMiniportDriver
product: Windows
targetos: Windows
req.typenames: WDI_TX_PAUSE_REASON
---


# NdisMDeregisterWdiMiniportDriver function
A miniport driver calls the NdisMDeregisterWdiMiniportDriver function to release resources that it allocated with a previous call to the <a href="..\dot11wdi\nf-dot11wdi-ndismregisterwdiminiportdriver.md">NdisMRegisterWdiMiniportDriver</a> function.

## Syntax

````
VOID NdisMDeregisterWdiMiniportDriver(
  _In_ NDIS_MINIPORT_DRIVER_HANDLE NdisMiniportDriverHandle
);
````

## Parameters

`NdisMiniportDriverHandle`

The NDIS handle for a miniport driver.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |
| **Library** | Ndis.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\dot11wdi\nf-dot11wdi-ndismregisterwdiminiportdriver.md">NdisMRegisterWdiMiniportDriver</a>