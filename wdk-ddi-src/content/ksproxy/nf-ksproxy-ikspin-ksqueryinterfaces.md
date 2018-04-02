---
UID: NF:ksproxy.IKsPin.KsQueryInterfaces
title: IKsPin::KsQueryInterfaces method
author: windows-driver-content
description: The KsQueryInterfaces method retrieves interfaces that a pin supports.
old-location: stream\ikspin_ksqueryinterfaces.htm
old-project: stream
ms.assetid: e8b0a1c0-c018-4556-b43c-fae4f7cf43de
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsPin, IKsPin interface [Streaming Media Devices], KsQueryInterfaces method, IKsPin::KsQueryInterfaces, KsQueryInterfaces method [Streaming Media Devices], KsQueryInterfaces method [Streaming Media Devices], IKsPin interface, KsQueryInterfaces,IKsPin.KsQueryInterfaces, ksproxy/IKsPin::KsQueryInterfaces, ksproxy_6a22f676-b7bd-4212-a79a-3a02da890e9f.xml, stream.ikspin_ksqueryinterfaces
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ksproxy.h
api_name:
-	IKsPin.KsQueryInterfaces
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# IKsPin::KsQueryInterfaces method
The <b>KsQueryInterfaces</b> method retrieves interfaces that a pin supports.

## Syntax

```
HRESULT KsQueryInterfaces(
  PKSMULTIPLE_ITEM *InterfaceList
);
```

## Parameters

`InterfaceList`

Pointer to a buffer that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563441">KSMULTIPLE_ITEM</a> structure, followed by a sequence of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563537">KSPIN_INTERFACE</a> structures that describe interface types. The KSMULTIPLE_ITEM structure is a header that describes the size of the buffer and the number of entries in the list that follows the header.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.

## Remarks

The returned interfaces are ordered by preference.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ksproxy.h (include Ksproxy.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563441">KSMULTIPLE_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563537">KSPIN_INTERFACE</a>