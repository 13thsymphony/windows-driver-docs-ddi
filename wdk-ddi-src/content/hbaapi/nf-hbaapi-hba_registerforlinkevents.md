---
UID: NF:hbaapi.HBA_RegisterForLinkEvents
title: HBA_RegisterForLinkEvents function
author: windows-driver-content
description: The HBA_RegisterForLinkEvents routine registers with a specified adapter for asynchronous fabric link-level events.
old-location: storage\hba_registerforlinkevents.htm
old-project: storage
ms.assetid: f0e6834c-b827-4342-83f1-5980f8edce24
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_RegisterForLinkEvents, HBA_RegisterForLinkEvents routine [Storage Devices], fibreHBA_rtns_7fd8f7c4-faaf-4190-99c8-560615e14365.xml, hbaapi/HBA_RegisterForLinkEvents, storage.hba_registerforlinkevents
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
-	HBA_RegisterForLinkEvents
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---


# HBA_RegisterForLinkEvents function
The <b>HBA_RegisterForLinkEvents</b> routine registers with a specified adapter for asynchronous fabric link-level events.

## Syntax

````
HBA_STATUS HBA_API HBA_RegisterForLinkEvents(
   HBA_LINK_CALLBACK  callback,
   void               *userData,
   void               *pRLIRBuffer,
   HBA_UINT32         RLIRBufferSize,
   HBA_HANDLE         handle,
   HBA_CALLBACKHANDLE *callbackHandle
);
````

## Parameters

`callback`

Pointer to a callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556121">HBA_LINK_CALLBACK</a> to call when the event occurs.

`userData`

Pointer to user input data that is passed to the callback routine when it is called with each occurrence of the event. This data can synchronize the event handling with event registration.

`pRLIRBuffer`

Pointer to registered link incident report (RLIR) data that is passed to the callback routine with each occurrence of the event. This data is overwritten by the callback routine each time it is called.

`RLIRBufferSize`

Contains the size, in bytes, of the buffer at <i>pRLIRBuffer</i>.

`Handle`

TBD

`pCallbackHandle`

TBD


## Return Value

The <b>HBA_RegisterForLinkEvents</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_RegisterForLinkEvents</b> returns one of the following values.

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
Returned if the callback registration was successful. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Returned if either the library or the system does not support events. 

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

Only RLIR events are reported. To stop event delivery, call <a href="..\hbaapi\nf-hbaapi-hba_removecallback.md">HBA_RemoveCallback</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** | Hbaapi.lib |
| **DLL** | Hbaapi.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556121">HBA_LINK_CALLBACK</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbaapi\nf-hbaapi-hba_removecallback.md">HBA_RemoveCallback</a>