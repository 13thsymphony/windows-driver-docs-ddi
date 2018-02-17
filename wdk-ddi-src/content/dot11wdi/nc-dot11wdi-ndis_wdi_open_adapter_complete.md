---
UID: NC:dot11wdi.NDIS_WDI_OPEN_ADAPTER_COMPLETE
title: NDIS_WDI_OPEN_ADAPTER_COMPLETE
author: windows-driver-content
description: The NdisWdiOpenAdapterComplete callback function is called by the IHV when an Open Task operation from MiniportWdiOpenAdapter has been successfully started.
old-location: netvista\ndiswdiopenadaptercomplete.htm
old-project: netvista
ms.assetid: FD6FF134-A8D7-433E-9353-88965E67749E
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndiswdiopenadaptercomplete, NdisWdiOpenAdapterComplete callback function [Network Drivers Starting with Windows Vista], NdisWdiOpenAdapterComplete, NDIS_WDI_OPEN_ADAPTER_COMPLETE, NDIS_WDI_OPEN_ADAPTER_COMPLETE, dot11wdi/NdisWdiOpenAdapterComplete
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dot11wdi.h
apiname:
-	NdisWdiOpenAdapterComplete
product: Windows
targetos: Windows
req.typenames: "*PSYNTH_STATS, SYNTH_STATS"
---


# NDIS_WDI_OPEN_ADAPTER_COMPLETE callback function
The NdisWdiOpenAdapterComplete callback function is called by the IHV when an Open Task operation from <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_open_adapter.md">MiniportWdiOpenAdapter</a> has been successfully started.

This is a control path callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a>.

## Syntax

```
NDIS_WDI_OPEN_ADAPTER_COMPLETE NdisWdiOpenAdapterComplete;

void NdisWdiOpenAdapterComplete(
  NDIS_HANDLE MiniportAdapterHandle,
  NDIS_STATUS CompletionStatus
)
{...}
```

## Parameters

`MiniportAdapterHandle`

The miniport handle.

`CompletionStatus`

The completion status.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a>



<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_open_adapter.md">MiniportWdiOpenAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_OPEN_ADAPTER_COMPLETE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>