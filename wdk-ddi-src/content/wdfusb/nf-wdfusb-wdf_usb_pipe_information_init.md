---
UID: NF:wdfusb.WDF_USB_PIPE_INFORMATION_INIT
title: WDF_USB_PIPE_INFORMATION_INIT function
author: windows-driver-content
description: The WDF_USB_PIPE_INFORMATION_INIT function initializes a WDF_USB_PIPE_INFORMATION structure.
old-location: wdf\wdf_usb_pipe_information_init.htm
old-project: wdf
ms.assetid: 13139135-22b4-4ca1-b95e-c4c704501368
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfusb/WDF_USB_PIPE_INFORMATION_INIT, wdf.wdf_usb_pipe_information_init, WDF_USB_PIPE_INFORMATION_INIT function, kmdf.wdf_usb_pipe_information_init, WDF_USB_PIPE_INFORMATION_INIT, DFUsbRef_ed525fc0-384b-4e9c-877a-075386f5d667.xml
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfusb.h
apiname:
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

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_PIPE_INFORMATION_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>