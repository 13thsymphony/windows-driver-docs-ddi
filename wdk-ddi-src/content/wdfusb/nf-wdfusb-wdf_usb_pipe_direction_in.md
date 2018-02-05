---
UID : NF:wdfusb.WDF_USB_PIPE_DIRECTION_IN
title : WDF_USB_PIPE_DIRECTION_IN function
author : windows-driver-content
description : The WDF_USB_PIPE_DIRECTION_IN function determines whether a specified USB endpoint is an input endpoint.
old-location : wdf\wdf_usb_pipe_direction_in.htm
old-project : wdf
ms.assetid : 3fca6d50-ac38-4edf-b24a-ea4fe5d8a4fd
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : DFUsbRef_e0e1b604-8973-4901-91ea-76fce4e69b7c.xml, wdfusb/WDF_USB_PIPE_DIRECTION_IN, WDF_USB_PIPE_DIRECTION_IN, kmdf.wdf_usb_pipe_direction_in, wdf.wdf_usb_pipe_direction_in, WDF_USB_PIPE_DIRECTION_IN function
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfusb.h
req.include-header : Wdfusb.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : None
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product : Windows 10 or later.
---


# WDF_USB_PIPE_DIRECTION_IN function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_PIPE_DIRECTION_IN</b> function determines whether a specified USB endpoint is an input endpoint.

## Syntax

````
BOOLEAN WDF_USB_PIPE_DIRECTION_IN(
  _In_ UCHAR EndpointAddress
);
````

## Parameters

`EndpointAddress`

A USB endpoint address.


## Return Value

<b>WDF_USB_PIPE_DIRECTION_IN</b> returns <b>TRUE</b> if the specified endpoint is an input endpoint. Otherwise, this function returns <b>FALSE</b>.

## Remarks

The high bit of the endpoint address determines the direction (input or output) of an endpoint. For more information about endpoint addresses, see the USB specification.

For more information about the <b>WDF_USB_PIPE_DIRECTION_IN</b> function and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |
| **Library** | None |

## See Also

<a href="..\wdfusb\nf-wdfusb-wdf_usb_pipe_direction_out.md">WDF_USB_PIPE_DIRECTION_OUT</a>

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeisinendpoint.md">WdfUsbTargetPipeIsInEndpoint</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_PIPE_DIRECTION_IN function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>