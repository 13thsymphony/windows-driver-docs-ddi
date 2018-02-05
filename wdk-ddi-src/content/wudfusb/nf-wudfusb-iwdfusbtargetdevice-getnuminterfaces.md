---
UID : NF:wudfusb.IWDFUsbTargetDevice.GetNumInterfaces
title : IWDFUsbTargetDevice::GetNumInterfaces method
author : windows-driver-content
description : The GetNumInterfaces method retrieves the number of USB interfaces for the USB device.
old-location : wdf\iwdfusbtargetdevice_getnuminterfaces.htm
old-project : wdf
ms.assetid : 4da2f2b0-f2ad-465d-b63e-f11406d4c210
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.iwdfusbtargetdevice_getnuminterfaces, IWDFUsbTargetDevice::GetNumInterfaces, GetNumInterfaces, IWDFUsbTargetDevice, GetNumInterfaces method, wudfusb/IWDFUsbTargetDevice::GetNumInterfaces, umdf.iwdfusbtargetdevice_getnuminterfaces, UMDFUSBref_43f488a1-350d-473a-aa10-d88983ea39f7.xml, GetNumInterfaces method, IWDFUsbTargetDevice interface, IWDFUsbTargetDevice interface, GetNumInterfaces method
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfusb.h
req.include-header : Wudfusb.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.5
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : wudfusb.h
req.dll : WUDFx.dll
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


# GetNumInterfaces method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetNumInterfaces</b> method retrieves the number of USB interfaces for the USB device.

## Syntax

````
UCHAR GetNumInterfaces();
````

## Parameters

This function has no parameters.

## Return Value

<b>GetNumInterfaces</b> returns the number of <a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a> interfaces for the USB device in the default configuration. The default configuration is identified by index zero.

## Remarks

UMDF USB I/O target devices do not support multiple configurations.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfusb.h (include Wudfusb.h) |
| **Library** | wudfusb.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a>

<a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetDevice::GetNumInterfaces method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>