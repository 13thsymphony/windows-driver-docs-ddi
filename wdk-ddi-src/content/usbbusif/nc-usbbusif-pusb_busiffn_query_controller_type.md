---
UID: NC:usbbusif.PUSB_BUSIFFN_QUERY_CONTROLLER_TYPE
title: USB_BUSIFFN_QUERY_CONTROLLER_TYPE
author: windows-driver-content
description: The QueryControllerType routine gets information about the USB host controller to which the USB device is attached.
old-location: buses\querycontrollertype.htm
old-project: usbref
ms.assetid: a3155544-cfb6-41a6-9d75-82618f7c7a48
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PUSB_BUSIFFN_QUERY_CONTROLLER_TYPE, QueryControllerType, QueryControllerType callback function [Buses], USB_BUSIFFN_QUERY_CONTROLLER_TYPE, buses.querycontrollertype, usbbusif/QueryControllerType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbbusif.h
req.include-header: Usbbusif.h
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
req.irql: "< = DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbbusif.h
api_name:
-	QueryControllerType
product: Windows
targetos: Windows
req.typenames: USBD_VERSION_INFORMATION, *PUSBD_VERSION_INFORMATION
req.product: Windows 10 or later.
---


# PUSB_BUSIFFN_QUERY_CONTROLLER_TYPE callback function
The <b>QueryControllerType</b> routine gets information about the USB host controller to which the USB device is attached.

## Syntax

```
PUSB_BUSIFFN_QUERY_CONTROLLER_TYPE PusbBusiffnQueryControllerType;

NTSTATUS PusbBusiffnQueryControllerType(
  PVOID ,
  PULONG ,
  PUSHORT ,
  PUSHORT ,
  PUCHAR ,
  PUCHAR ,
  PUCHAR ,
  PUCHAR 
)
{...}
```

## Parameters

`Arg1`



`Arg1`



`Arg1`



`Arg1`



`Arg1`



`Arg1`



`Arg1`



`Arg1`




## Return Value

Returns STATUS_SUCCESS on success, and the appropriate error code on failure.

## Remarks

<i>PciClass</i> is typically set to PCI_CLASS_SERIAL_BUS_CTLR (0x0C).


<i>PciSubClass</i> is typically set to PCI_SUBCLASS_SB_USB (0x03).


<i>PciProgif</i> is typically set to one of the following values:
	

0x00 - Universal Host Controller Interface (UHCI)


	0x10 - Open Host Controller Interface (OHCI)
	

0x20 - Enhanced Host Controller Interface (EHCI)


The function definition that is provided on this reference page is an example function whose parameters are just placeholder names. The actual prototype of the function is declared in usbbusif.h as follows:



<pre class="syntax" xml:space="preserve"><code>typedef NTSTATUS
  (USB_BUSIFFN *PUSB_BUSIFFN_QUERY_CONTROLLER_TYPE) (
    IN PVOID,
    OUT PULONG,
    OUT PUSHORT,
    OUT PUSHORT,
    OUT PUCHAR,
    OUT PUCHAR,
    OUT PUCHAR,
    OUT PUCHAR
</code></pre>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbbusif.h (include Usbbusif.h) |
| **IRQL** | "< = DISPATCH_LEVEL" |

## See Also

<a href="..\usbbusif\ns-usbbusif-_usb_bus_interface_usbdi_v3.md">USB_BUS_INTERFACE_USBDI_V3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_BUSIFFN_QUERY_CONTROLLER_TYPE callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>