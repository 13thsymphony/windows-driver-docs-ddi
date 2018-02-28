---
UID: NC:dot11wdi.MINIPORT_WDI_ALLOCATE_ADAPTER
title: MINIPORT_WDI_ALLOCATE_ADAPTER
author: windows-driver-content
description: The MiniportWdiAllocateAdapter handler function allocates a WDI miniport adapter.
old-location: netvista\miniportwdiallocateadapter.htm
old-project: netvista
ms.assetid: 4CBC7230-6480-40C9-90B7-A286FCEB1FA8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: MINIPORT_WDI_ALLOCATE_ADAPTER, MiniportWdiAllocateAdapter, MiniportWdiAllocateAdapter callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiAllocateAdapter, netvista.miniportwdiallocateadapter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dot11wdi.h
api_name:
-	MiniportWdiAllocateAdapter
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# MINIPORT_WDI_ALLOCATE_ADAPTER callback function
The MiniportWdiAllocateAdapter handler function allocates a WDI miniport adapter.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_ALLOCATE_ADAPTER</b> type. For more
   information, see the following Examples section.</div><div> </div>

## Syntax

```
MINIPORT_WDI_ALLOCATE_ADAPTER MiniportWdiAllocateAdapter;

NDIS_STATUS MiniportWdiAllocateAdapter(
  NDIS_HANDLE NdisMiniportHandle,
  NDIS_HANDLE MiniportDriverContext,
  PNDIS_MINIPORT_INIT_PARAMETERS MiniportInitParameters,
  PNDIS_WDI_INIT_PARAMETERS NdisWdiInitParameters,
  PNDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES RegistrationAttributes
)
{...}
```

## Parameters

`NdisMiniportHandle`

The NDIS-supplied handle that identifies the miniport adapter.

`MiniportDriverContext`

The handle to a driver-allocated context area where the driver maintains state and configuration information. The miniport driver passed this context area to the <a href="..\dot11wdi\nf-dot11wdi-ndismregisterwdiminiportdriver.md">NdisMRegisterWdiMiniportDriver</a> function.

`MiniportInitParameters`

A pointer to an <a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">NDIS_MINIPORT_INIT_PARAMETERS</a> structure that defines the initialization parameters for the miniport adapter.

`NdisWdiInitParameters`

A pointer to an <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a> structure that defines the WDI initialization parameters for the miniport adapter.

`RegistrationAttributes`

A pointer to an <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_registration_attributes.md">NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a> structure that defines registration attributes that are associated with the miniport adapter.


## Return Value

MiniportWdiAllocateAdapter can return any of the following return values.

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
MiniportWdiAllocateAdapter successfully completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
MiniportWdiAllocateAdapter could not allocate the necessary resources.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">NDIS_MINIPORT_INIT_PARAMETERS</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_registration_attributes.md">NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_ALLOCATE_ADAPTER callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>