---
UID: NF:ndis.NdisFGetOptionalSwitchHandlers
title: NdisFGetOptionalSwitchHandlers function
author: windows-driver-content
description: Hyper-V extensible switch extensions call the NdisFGetOptionalSwitchHandlers function to obtain a list of pointers to the Hyper-V extensible switch handler functions.
old-location: netvista\ndisfgetoptionalswitchhandlers.htm
old-project: netvista
ms.assetid: bf034ecd-5c1b-4117-a7b0-bcca3971386b
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisFGetOptionalSwitchHandlers, NdisFGetOptionalSwitchHandlers function [Network Drivers Starting with Windows Vista], ndis/NdisFGetOptionalSwitchHandlers, netvista.ndisfgetoptionalswitchhandlers
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFGetOptionalSwitchHandlers
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisFGetOptionalSwitchHandlers function
Hyper-V extensible switch extensions call the <b>NdisFGetOptionalSwitchHandlers</b> function to obtain a list of pointers to the Hyper-V extensible switch handler functions.

## Syntax

```
NDIS_STATUS NdisFGetOptionalSwitchHandlers(
  NDIS_HANDLE                    NdisFilterHandle,
  PNDIS_SWITCH_CONTEXT           NdisSwitchContext,
  PNDIS_SWITCH_OPTIONAL_HANDLERS NdisSwitchHandlers
);
```

## Parameters

`NdisFilterHandle`

The NDIS handle that identifies this filter module. When NDIS called the extension's  <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function, it passed this handle in the <i>NdisFilterHandle</i> parameter.

`NdisSwitchContext`

A pointer to the NDIS_SWITCH_CONTEXT value that identifies the extensible switch module to which the extension is attached. When  the  extension calls an extensible switch  handler  function, it must set the     <i>NdisSwitchContext</i> parameter to the value of this handle.

`NdisSwitchHandlers`

A pointer to a caller-allocated  <a href="https://msdn.microsoft.com/library/windows/hardware/hh598219">NDIS_SWITCH_OPTIONAL_HANDLERS</a> structure. If the call succeeds, this structure will contain a list of pointers to the extensible switch handler functions.

For more information about these handler functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh598172">Hyper-V Extensible Switch Handler Functions</a>.

<div class="alert"><b>Note</b>  Before the extension calls <b>NdisFGetOptionalSwitchHandlers</b>, it must initialize the <b>Header</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598219">NDIS_SWITCH_OPTIONAL_HANDLERS</a> structure.</div>
<div> </div>


## Return Value

If the call succeeds, <b>NdisFGetOptionalSwitchHandlers</b> returns NDIS_STATUS_SUCCESS. Otherwise, it returns NDIS_STATUS_NOT_SUPPORTED if the extensible switch extension is not bound to the underlying extensible switch component.

## Remarks

The  extension calls the <b>NdisFGetOptionalSwitchHandlers</b> function from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function. 

If the extension is installed with multiple <b>FilterMediaTypes</b> INF entries, the call to <b>NdisFGetOptionalSwitchHandlers</b> lets the extension  determine whether it is bound and attached to the driver stack for either the extensible switch or a physical network adapter. If the call returns NDIS_STATUS_SUCCESS, the extension is attached within the extensible switch driver stack. If the call returns NDIS_STATUS_NOT_SUPPORTED, the extension is attached within the driver stack for a physical network adapter.

For more information about <b>FilterMediaTypes</b> INF entries for extensible switch extensions, see <a href="https://msdn.microsoft.com/378F619A-C799-4330-A388-9955A67251F8">INF Requirements for Hyper-V Extensible Switch Extensions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598219">NDIS_SWITCH_OPTIONAL_HANDLERS</a>