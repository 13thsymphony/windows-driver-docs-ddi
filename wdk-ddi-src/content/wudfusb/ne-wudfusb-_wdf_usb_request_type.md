---
UID : NE:wudfusb._WDF_USB_REQUEST_TYPE
title : "_WDF_USB_REQUEST_TYPE"
author : windows-driver-content
description : The WDF_USB_REQUEST_TYPE enumeration contains values that identify a type of USB request object.
old-location : wdf\wdf_usb_request_type_umdf.htm
old-project : wdf
ms.assetid : fb952527-a8df-41e7-8194-b4a82b7f550f
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.wdf_usb_request_type_umdf, wudfusb/WdfUsbRequestTypeInvalid, wudfusb/PWDF_USB_REQUEST_TYPE, umdfstructs_e6072726-4218-4018-91bd-7122031416ca.xml, wudfusb/WdfUsbRequestTypePipeRead, umdf.wdf_usb_request_type, wudfusb/WDF_USB_REQUEST_TYPE, wudfusb/WdfUsbRequestTypeDeviceControlTransfer, wudfusb/WdfUsbRequestTypeNoFormat, _WDF_USB_REQUEST_TYPE, PWDF_USB_REQUEST_TYPE, PWDF_USB_REQUEST_TYPE enumeration pointer, WdfUsbRequestTypeInvalid, WDF_USB_REQUEST_TYPE, WdfUsbRequestTypeDeviceControlTransfer, WdfUsbRequestTypeNoFormat, WdfUsbRequestTypePipeWrite, *PWDF_USB_REQUEST_TYPE, WdfUsbRequestTypePipeRead, WDF_USB_REQUEST_TYPE enumeration, wudfusb/WdfUsbRequestTypePipeWrite
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wudfusb.h
req.include-header : Wudfusb.h
req.target-type : Windows
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
req.lib : 
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

# _WDF_USB_REQUEST_TYPE Enumeration
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


      The <a href="..\wudfusb\ne-wudfusb-_wdf_usb_request_type.md">WDF_USB_REQUEST_TYPE</a> enumeration contains values that identify a type of USB request object.

## Syntax
````
typedef enum _WDF_USB_REQUEST_TYPE { 
  WdfUsbRequestTypeInvalid                = 0,
  WdfUsbRequestTypeNoFormat               = ( WdfUsbRequestTypeInvalid + 1 ),
  WdfUsbRequestTypeDeviceControlTransfer  = ( WdfUsbRequestTypeNoFormat + 1 ),
  WdfUsbRequestTypePipeWrite              = ( WdfUsbRequestTypeDeviceControlTransfer + 1 ),
  WdfUsbRequestTypePipeRead               = ( WdfUsbRequestTypePipeWrite + 1 )
} WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE;
````

## Constants

<table>

<tr>
<td>WdfUsbRequestTypeDeviceControlTransfer</td>
<td>The request object is sent when the application calls the Win32 <b>DeviceIoControl</b> function on the file object that is associated with the target device.</td>
</tr>

<tr>
<td>WdfUsbRequestTypeInvalid</td>
<td>The type of the request object is invalid.</td>
</tr>

<tr>
<td>WdfUsbRequestTypeNoFormat</td>
<td>The request object is not formatted.</td>
</tr>

<tr>
<td>WdfUsbRequestTypePipeRead</td>
<td>The request object is sent when the application calls the Win32 <b>ReadFile</b> or <b>ReadFileEx</b> function on the file object that is associated with the target device.</td>
</tr>

<tr>
<td>WdfUsbRequestTypePipeWrite</td>
<td>The request object is sent when the application calls the Win32 <b>WriteFile</b> or <b>WriteFileEx</b> function on the file object that is associated with the target device.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wudfusb.h (include Wudfusb.h) |