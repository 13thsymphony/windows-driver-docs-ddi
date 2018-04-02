---
UID: NF:dot11wdi.NdisMRegisterWdiMiniportDriver
title: NdisMRegisterWdiMiniportDriver function
author: windows-driver-content
description: A miniport driver calls the NdisMRegisterWdiMiniportDriver function to register MiniportWdiXxx entry points with NDIS as the first step in initialization.
old-location: netvista\ndismregisterwdiminiportdriver.htm
old-project: netvista
ms.assetid: 60FE4E6C-38D4-438F-983B-7336926F6FE2
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMRegisterWdiMiniportDriver, NdisMRegisterWdiMiniportDriver function [Network Drivers Starting with Windows Vista], dot11wdi/NdisMRegisterWdiMiniportDriver, netvista.ndismregisterwdiminiportdriver
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
-	NdisMRegisterWdiMiniportDriver
product: Windows
targetos: Windows
req.typenames: WDI_TX_PAUSE_REASON
---


# NdisMRegisterWdiMiniportDriver function
A miniport driver calls the NdisMRegisterWdiMiniportDriver function to register MiniportWdiXxx entry points with NDIS as the first step in initialization.

## Syntax

```
NDIS_EXPORT NDIS_STATUS NdisMRegisterWdiMiniportDriver(
  DRIVER_OBJECT                            *DriverObject,
  PCUNICODE_STRING                         RegistryPath,
  NDIS_MINIPORT_DRIVER_CONTEXT             NdisDriverContext,
  NDIS_MINIPORT_DRIVER_CHARACTERISTICS     *MiniportDriverCharacteristics,
  NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS *MiniportWdiCharacteristics,
  NDIS_MINIPORT_DRIVER_HANDLE              *NdisMiniportDriverHandle
);
```

## Parameters

`DriverObject`

A pointer to an opaque driver object that the miniport driver received in its 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine at the 
     <i>Argument1</i> parameter (see 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff548818">DriverEntry of NDIS
     Miniport Drivers</a>).

`RegistryPath`

A pointer to an opaque registry path that the miniport driver received in its 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine at the 
     <i>Argument2</i> parameter.

`NdisDriverContext`

A handle to a driver-allocated context area where the driver maintains state and configuration
     information.

`MiniportDriverCharacteristics`

A pointer to an 
     <a href="https://msdn.microsoft.com/2e2c8522-127d-49d5-a5d6-97f9403bec89">
     NDIS_MINIPORT_DRIVER_CHARACTERISTICS</a> structure that the caller initialized.

`MiniportWdiCharacteristics`

A pointer to an 
     
     <a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a> structure that the caller initialized.

`NdisMiniportDriverHandle`

A pointer to a caller-supplied handle variable. NDIS writes a handle to this variable that
     uniquely identifies this driver. The driver must save this handle for use in subsequent 
     <b>Ndis<i>Xxx</i></b> function calls.


## Return Value

NdisMRegisterWdiMiniportDriver can return any of the following return values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
NdisMRegisterWdiMiniportDriver registered the WDI miniport driver successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_CHARACTERISTICS</b></dt>
</dl>
</td>
<td width="60%">
The 
       <i>CharacteristicsLength</i> parameter is incorrect for the NDIS version that is specified at the 
       <b>MajorNdisVersion</b> member in the structure at 
       <i>MiniportDriverCharacteristics</i> .

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_VERSION</b></dt>
</dl>
</td>
<td width="60%">
The 
       <b>MajorNdisVersion</b> or 
       <b>MinorNdisVersion</b> specified in the characteristics structure is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A shortage of resources, possibly memory, prevented NDIS from registering the caller.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
This is a default error status, returned when none of the preceding errors caused the
       registration to fail.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other NDIS_STATUS codes</b></dt>
</dl>
</td>
<td width="60%">
An appropriate NDIS_STATUS code in the case of a failure.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |
| **Library** | Ndis.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565958">NDIS_MINIPORT_DRIVER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>