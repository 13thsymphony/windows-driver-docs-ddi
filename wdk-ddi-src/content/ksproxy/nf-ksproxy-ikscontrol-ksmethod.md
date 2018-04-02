---
UID: NF:ksproxy.IKsControl.KsMethod
title: IKsControl::KsMethod method
author: windows-driver-content
description: The KsMethod method sends a method to a KS object, along with any other defined support operations available on a method set.
old-location: stream\ikscontrol_ksmethod.htm
old-project: stream
ms.assetid: 9f9121be-786d-4a1c-bb01-7bf3c1d3b6cf
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsControl, IKsControl interface [Streaming Media Devices], KsMethod method, IKsControl::KsMethod, KsMethod method [Streaming Media Devices], KsMethod method [Streaming Media Devices], IKsControl interface, KsMethod,IKsControl.KsMethod, ksproxy/IKsControl::KsMethod, ksproxy_700d1bc3-f01e-4fff-9976-f64cdfd54f82.xml, stream.ikscontrol_ksmethod
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: DesktopMobile
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
-	IKsControl.KsMethod
product:
- Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# IKsControl::KsMethod method
The <b>KsMethod</b> method sends a method to a KS object, along with any other defined support operations available on a method set.

## Syntax

```
HRESULT KsMethod(
  PKSMETHOD Method,
  ULONG     MethodLength,
  LPVOID    MethodData,
  ULONG     DataLength,
  ULONG     *BytesReturned
);
```

## Parameters

`Method`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a> structure that describes a method and the request type of the method request.

`MethodLength`

Size, in bytes, of the buffer at <i>Method</i>.

`MethodData`

Pointer to a buffer that contains data and buffer space for a KSMETHOD_TYPE_SEND operation, or buffer space that receives data for all other operations.

`DataLength`

Size, in bytes, of the buffer at <i>MethodData</i>.

`BytesReturned`

Pointer to a variable that receives the size, in bytes, of the data that <b>KsMethod</b> stores in the buffer at <i>MethodData</i>.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.

## Remarks

This is a synchronous call. It will not complete until the method is completed from kernel-mode.

To determine the buffer size that is required for a specific method request, you can call this method with MethodData set to <b>NULL</b> and DataLength equal to zero. The method returns HRESULT_FROM_WIN32(ERROR_MORE_DATA and BytesReturned contains the size of the required buffer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | DesktopMobile |
| **Header** | ksproxy.h (include Ksproxy.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>