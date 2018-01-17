---
UID: NF:wudfusb.IWDFUsbInterface.GetNumEndPoints
title: IWDFUsbInterface::GetNumEndPoints method
author: windows-driver-content
description: The GetNumEndPoints method retrieves the number of endpoints (pipes) on a USB interface.
old-location: wdf\iwdfusbinterface_getnumendpoints.htm
old-project: wdf
ms.assetid: 60ec8b38-8ab2-45d8-92ab-5943fd9bba79
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFUsbInterface, IWDFUsbInterface::GetNumEndPoints, GetNumEndPoints
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfusb.h
req.include-header: Wudfusb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFUsbInterface.GetNumEndPoints
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.typenames: *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbInterface::GetNumEndPoints method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetNumEndPoints</b> method retrieves the number of endpoints (pipes) on a USB interface.



## -syntax

````
UCHAR GetNumEndPoints();
````


## -parameters


## -returns
<b>GetNumEndPoints</b> returns the number of endpoints on the USB interface.

<b>GetNumEndPoints</b> returns the number of endpoints on the USB interface.

<b>GetNumEndPoints</b> returns the number of endpoints on the USB interface.


## -remarks
The <b>GetNumEndPoints</b> method is provided for convenience because a UMDF driver can obtain the number of endpoints from the <b>bNumEndpoints</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a> structure that the driver retrieves when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560320">IWDFUsbInterface::GetInterfaceDescriptor</a> method. 

The following code example retrieves the number of pipes on a USB interface and then retrieves particular types of pipes.


## -see-also
<dl>
<dt>
<a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560320">IWDFUsbInterface::GetInterfaceDescriptor</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbInterface::GetNumEndPoints method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

