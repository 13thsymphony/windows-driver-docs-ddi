---
UID: NE.wudfusb._WDF_USB_REQUEST_TYPE~r1
title: _WDF_USB_REQUEST_TYPE
author: windows-driver-content
description: The WDF_USB_REQUEST_TYPE enumeration contains values that identify a type of USB request object.
old-location: wdf\wdf_usb_request_type_umdf.htm
old-project: wdf
ms.assetid: fb952527-a8df-41e7-8194-b4a82b7f550f
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfusb.h
req.include-header: Wudfusb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDF_USB_REQUEST_TYPE
req.alt-loc: wudfusb.h
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
req.product: Windows 10 or later.
---

# _WDF_USB_REQUEST_TYPE enumeration



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


      The <a href="wdf.wdf_usb_request_type">WDF_USB_REQUEST_TYPE</a> enumeration contains values that identify a type of USB request object.



## -syntax

````
typedef enum _WDF_USB_REQUEST_TYPE { 
  WdfUsbRequestTypeInvalid                = 0,
  WdfUsbRequestTypeNoFormat               = ( WdfUsbRequestTypeInvalid + 1 ),
  WdfUsbRequestTypeDeviceControlTransfer  = ( WdfUsbRequestTypeNoFormat + 1 ),
  WdfUsbRequestTypePipeWrite              = ( WdfUsbRequestTypeDeviceControlTransfer + 1 ),
  WdfUsbRequestTypePipeRead               = ( WdfUsbRequestTypePipeWrite + 1 )
} WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE;
````


## -enum-fields

### -field WdfUsbRequestTypeInvalid

The type of the request object is invalid. 


### -field WdfUsbRequestTypeNoFormat

The request object is not formatted.


### -field WdfUsbRequestTypeDeviceControlTransfer

The request object is sent when the application calls the Win32 <b>DeviceIoControl</b> function on the file object that is associated with the target device. 


### -field WdfUsbRequestTypePipeWrite

The request object is sent when the application calls the Win32 <b>WriteFile</b> or <b>WriteFileEx</b> function on the file object that is associated with the target device. 


### -field WdfUsbRequestTypePipeRead

The request object is sent when the application calls the Win32 <b>ReadFile</b> or <b>ReadFileEx</b> function on the file object that is associated with the target device. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfusb.h (include Wudfusb.h)</dt>
</dl>
</td>
</tr>
</table>