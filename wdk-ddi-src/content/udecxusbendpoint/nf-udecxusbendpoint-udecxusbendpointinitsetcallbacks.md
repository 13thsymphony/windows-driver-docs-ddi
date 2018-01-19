---
UID : NF:udecxusbendpoint.UdecxUsbEndpointInitSetCallbacks
title : UdecxUsbEndpointInitSetCallbacks function
author : windows-driver-content
description : Sets pointers to UDE client driver-implemented callback functions in the initialization parameters of the simple endpoint to create.
old-location : buses\udecxusbendpointinitsetcallbacks.htm
old-project : usbref
ms.assetid : 0F6EBBDA-FA0B-4044-905B-535D4FFEC5D2
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : UdecxUsbEndpointInitSetCallbacks
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : udecxusbendpoint.h
req.include-header : Udecx.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 1.15
req.umdf-ver : 
req.alt-api : UdecxUsbEndpointInitSetCallbacks
req.alt-loc : Udecxstub.lib,Udecxstub.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Udecxstub.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PUDECX_USB_ENDPOINT_INIT_AND_METADATA, UDECX_USB_ENDPOINT_INIT_AND_METADATA"
req.product : Windows 10 or later.
---


# UdecxUsbEndpointInitSetCallbacks function
Sets pointers to UDE client driver-implemented  callback functions in the initialization parameters of the simple endpoint to create.

## Syntax

````
FORCEINLINE void UdecxUsbEndpointInitSetCallbacks(
  _Inout_ PUDECXUSBENDPOINT_INIT        Init,
  _In_    PUDECX_USB_ENDPOINT_CALLBACKS EndpointCallbacks
);
````

## Parameters

`UdecxUsbEndpointInit`



`EndpointCallbacks`

A pointer to <a href="..\udecxusbendpoint\ns-udecxusbendpoint-_udecx_usb_endpoint_callbacks.md">UDECX_USB_ENDPOINT_CALLBACKS</a> that contains function pointers to event callback functions implemented by the UDE client driver.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** |  |
| **Header** | udecxusbendpoint.h (include Udecx.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointcreate.md">UdecxUsbEndpointCreate</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbEndpointInitSetCallbacks function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>