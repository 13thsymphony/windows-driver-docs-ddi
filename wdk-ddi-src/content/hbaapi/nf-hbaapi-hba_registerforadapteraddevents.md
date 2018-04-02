---
UID: NF:hbaapi.HBA_RegisterForAdapterAddEvents
title: HBA_RegisterForAdapterAddEvents function
author: windows-driver-content
description: The HBA_RegisterForAdapterAddEvents routine registers the indicated user callback routine to call when a new adapter is added to the system.
old-location: storage\hba_registerforadapteraddevents.htm
old-project: storage
ms.assetid: 7395ccb8-2608-46ae-a378-987bd757761b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_RegisterForAdapterAddEvents, HBA_RegisterForAdapterAddEvents routine [Storage Devices], fibreHBA_rtns_d44e8303-9d14-4f36-830e-bca76a494dfd.xml, hbaapi/HBA_RegisterForAdapterAddEvents, storage.hba_registerforadapteraddevents
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_RegisterForAdapterAddEvents
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---


# HBA_RegisterForAdapterAddEvents function
The <b>HBA_RegisterForAdapterAddEvents</b> routine registers the indicated user callback routine to call when a new adapter is added to the system.

## Syntax

```
HBA_STATUS HBA_API HBA_RegisterForAdapterAddEvents(
  IN void(* )(void *pData,HBA_WWN PortWWN,HBA_UINT32 eventType) callback,
  IN void                                                       *pUserData,
  OUT HBA_CALLBACKHANDLE                                        *pCallbackHandle
);
```

## Parameters

`callback`

Pointer to a callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556045">HBA_ADAPTER_CALLBACK</a> that is called when an adapter is added to the system.

`pUserData`

TBD

`pCallbackHandle`

TBD


## Return Value

The <b>HBA_RegisterForAdapterAddEvents</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, this member should have one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the callback routine was successfully registered. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the registration of the callback routine. 

</td>
</tr>
</table>

## Remarks

When a new adapter is added to the system, an event of type HBA_EVENT_ADAPTER_ADD is generated.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** | Hbaapi.lib |
| **DLL** | Hbaapi.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556045">HBA_ADAPTER_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557175">HBA_RemoveCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>