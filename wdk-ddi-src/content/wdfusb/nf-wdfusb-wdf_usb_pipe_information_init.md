---
UID: NF:wdfusb.WDF_USB_PIPE_INFORMATION_INIT
title: WDF_USB_PIPE_INFORMATION_INIT function
author: windows-driver-content
description: The WDF_USB_PIPE_INFORMATION_INIT function initializes a WDF_USB_PIPE_INFORMATION structure.
old-location: wdf\wdf_usb_pipe_information_init.htm
old-project: wdf
ms.assetid: 13139135-22b4-4ca1-b95e-c4c704501368
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_ed525fc0-384b-4e9c-877a-075386f5d667.xml, WDF_USB_PIPE_INFORMATION_INIT, WDF_USB_PIPE_INFORMATION_INIT function, kmdf.wdf_usb_pipe_information_init, wdf.wdf_usb_pipe_information_init, wdfusb/WDF_USB_PIPE_INFORMATION_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	HeaderDef
api_location:
-	wdfusb.h
api_name:
-	WDF_USB_PIPE_INFORMATION_INIT
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WDF_USB_PIPE_INFORMATION_INIT function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_PIPE_INFORMATION_INIT</b> function initializes a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a> structure.

## Syntax

````
VOID WDF_USB_PIPE_INFORMATION_INIT(
  _Out_ PWDF_USB_PIPE_INFORMATION Info
);
````

## Parameters

`Info`

A pointer to a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a> structure.


## Return Value

None

## Remarks

The <b>WDF_USB_PIPE_INFORMATION_INIT</b> function zeros the WDF_USB_PIPE_INFORMATION structure and sets the structure's <b>Size</b> member.


#### Examples

For a code example that uses <b>WDF_USB_PIPE_INFORMATION_INIT</b>, see <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetendpointinformation.md">WdfUsbInterfaceGetEndpointInformation</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |

## See Also

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a>