---
UID: NF:ksproxy.KsGetMultiplePinFactoryItems
title: KsGetMultiplePinFactoryItems function
author: windows-driver-content
description: The KsGetMultiplePinFactoryItems function retrieves pin property items in a variable length data buffer.
old-location: stream\ksgetmultiplepinfactoryitems.htm
old-project: stream
ms.assetid: 43210484-dcae-49b7-bda3-50d6c06ee2c0
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGetMultiplePinFactoryItems, KsGetMultiplePinFactoryItems function [Streaming Media Devices], ksproxy/KsGetMultiplePinFactoryItems, ksproxy_cd252212-9317-4e1a-9f57-ee18afc23766.xml, stream.ksgetmultiplepinfactoryitems
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ksproxy.lib
-	Ksproxy.dll
api_name:
-	KsGetMultiplePinFactoryItems
product:
- Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# KsGetMultiplePinFactoryItems function
The <b>KsGetMultiplePinFactoryItems</b> function retrieves pin property items in a variable length data buffer.

## Syntax

```
KSDDKAPI HRESULT KsGetMultiplePinFactoryItems(
  HANDLE FilterHandle,
  ULONG  PinFactoryId,
  ULONG  PropertyId,
  PVOID  *Items
);
```

## Parameters

`FilterHandle`

Handle to the filter that contains the pin factory to query.

`PinFactoryId`

Identifier of the pin factory against which the property items are being returned.

`PropertyId`

Identifier of the property in the pin property set (<a href="https://msdn.microsoft.com/library/windows/hardware/ff566584">KSPROPSETID_Pin</a>) to query.

`Items`

Pointer to a buffer to receive the property items. If successfully retrieved, this pointer must be subsequently deleted with the <b>CoTaskMemFree</b> function.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.

## Remarks

The <b>KsGetMultiplePinFactoryItems</b> function queries for the data size, in bytes, of the requested property, allocates a buffer, and retrieves the data.

For more information about <b>CoTaskMemFree</b>, see the Microsoft Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ksproxy.h (include Ksproxy.h) |
| **Library** | Ksproxy.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559910">IKsPinFactory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566584">KSPROPSETID_Pin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566722">KSP_PIN</a>