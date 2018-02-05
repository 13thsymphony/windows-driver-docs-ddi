---
UID : NF:udecxusbendpoint.UdecxUsbEndpointCreate
title : UdecxUsbEndpointCreate function
author : windows-driver-content
description : Creates a UDE endpoint object.
old-location : buses\udecxusbendpointcreate.htm
old-project : usbref
ms.assetid : F97642A2-FE77-41D0-A194-8DE6F9B17BB0
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : buses.udecxusbendpointcreate, UdecxUsbEndpointCreate, udecxusbendpoint/UdecxUsbEndpointCreate, UdecxUsbEndpointCreate function [Buses]
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PUDECX_USB_ENDPOINT_INIT_AND_METADATA, UDECX_USB_ENDPOINT_INIT_AND_METADATA"
req.product : Windows 10 or later.
---


# UdecxUsbEndpointCreate function
Creates a UDE endpoint object.

## Syntax

````
FORCEINLINE NTSTATUS UdecxUsbEndpointCreate(
  _Inout_  PUDECXUSBENDPOINT_INIT Init,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES Attributes,
  _Out_    UDECXUSBENDPOINT       *UdecxUsbEndpoint
);
````

## Parameters

`EndpointInit`

TBD

`Attributes`

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the USB device object.

`UdecxUsbEndpoint`

A pointer to a variable that receives a handle to the new UDE endpoint object that represents the simple endpoint on the  USB device.


## Return Value

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Header** | udecxusbendpoint.h (include Udecx.h) |
| **Library** | Udecxstub.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>

<a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbsimpleendpointinitallocate.md">UdecxUsbSimpleEndpointInitAllocate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbEndpointCreate function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>