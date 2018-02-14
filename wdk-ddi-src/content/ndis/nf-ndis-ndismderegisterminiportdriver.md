---
UID: NF:ndis.NdisMDeregisterMiniportDriver
title: NdisMDeregisterMiniportDriver function
author: windows-driver-content
description: A miniport driver calls the NdisMDeregisterMiniportDriver function to release resources that it allocated with a previous call to the NdisMRegisterMiniportDriver function.
old-location: netvista\ndismderegisterminiportdriver.htm
old-project: netvista
ms.assetid: c428e30d-ce86-4ca0-bc65-45d84a7c910e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisMDeregisterMiniportDriver function [Network Drivers Starting with Windows Vista], netvista.ndismderegisterminiportdriver, miniport_ndis_functions_ref_bd8d7bcd-098a-4367-82d2-6a35753a4a3b.xml, NdisMDeregisterMiniportDriver, ndis/NdisMDeregisterMiniportDriver
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
req.ddi-compliance: Irql_Miniport_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMDeregisterMiniportDriver
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisMDeregisterMiniportDriver function
A miniport driver calls the 
  <b>NdisMDeregisterMiniportDriver</b> function to release resources that it allocated with a previous call to
  the 
  <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a> function.

## Syntax

````
VOID NdisMDeregisterMiniportDriver(
  _In_ NDIS_HANDLE NdisMiniportDriverHandle
);
````

## Parameters

`NdisMiniportDriverHandle`

The handle that the miniport driver obtained in a previous call to 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>.


## Return Value

None

## Remarks

If an error occurs in the miniport driver's 
    <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine after the 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
    NdisMRegisterMiniportDriver</a> function returns successfully, the driver must call 
    <b>NdisMDeregisterMiniportDriver</b> before 
    <b>DriverEntry</b> returns. If 
    <b>DriverEntry</b> succeeds, the driver must call 
    <b>NdisMDeregisterMiniportDriver</b> from its 
    <a href="..\ndis\nc-ndis-miniport_unload.md">MiniportDriverUnload</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Miniport_Driver_Function |

## See Also

<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>



<a href="..\ndis\nc-ndis-miniport_unload.md">MiniportDriverUnload</a>



<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMDeregisterMiniportDriver function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>