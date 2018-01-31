---
UID : NF:ksproxy.KsGetMultiplePinFactoryItems
title : KsGetMultiplePinFactoryItems function
author : windows-driver-content
description : The KsGetMultiplePinFactoryItems function retrieves pin property items in a variable length data buffer.
old-location : stream\ksgetmultiplepinfactoryitems.htm
old-project : stream
ms.assetid : 43210484-dcae-49b7-bda3-50d6c06ee2c0
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ksproxy_cd252212-9317-4e1a-9f57-ee18afc23766.xml, KsGetMultiplePinFactoryItems function [Streaming Media Devices], ksproxy/KsGetMultiplePinFactoryItems, KsGetMultiplePinFactoryItems, stream.ksgetmultiplepinfactoryitems
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ksproxy.h
req.include-header : Ksproxy.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ksproxy.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PIPE_STATE
---


# KsGetMultiplePinFactoryItems function
The <b>KsGetMultiplePinFactoryItems</b> function retrieves pin property items in a variable length data buffer.

## Syntax

````
HRESULT KsGetMultiplePinFactoryItems(
  _In_  HANDLE FilterHandle,
  _In_  ULONG  PinFactoryId,
  _In_  ULONG  PropertyId,
  _Out_ PVOID  *Items
);
````

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
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksproxy.h (include Ksproxy.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="..\ks\ns-ks-ksp_pin.md">KSP_PIN</a>

<a href="..\ksproxy\nn-ksproxy-ikspinfactory.md">IKsPinFactory</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566584">KSPROPSETID_Pin</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetMultiplePinFactoryItems function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>