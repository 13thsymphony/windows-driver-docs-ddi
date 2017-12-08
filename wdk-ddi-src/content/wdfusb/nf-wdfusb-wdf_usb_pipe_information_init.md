---
UID: NF.wdfusb.WDF_USB_PIPE_INFORMATION_INIT
title: WDF_USB_PIPE_INFORMATION_INIT function
author: windows-driver-content
description: The WDF_USB_PIPE_INFORMATION_INIT function initializes a WDF_USB_PIPE_INFORMATION structure.
old-location: wdf\wdf_usb_pipe_information_init.htm
old-project: wdf
ms.assetid: 13139135-22b4-4ca1-b95e-c4c704501368
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_USB_PIPE_INFORMATION_INIT
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
req.alt-api: WDF_USB_PIPE_INFORMATION_INIT
req.alt-loc: wdfusb.h
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

# WDF_USB_PIPE_INFORMATION_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WDF_USB_PIPE_INFORMATION_INIT</b> function initializes a <a href="wdf.wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a> structure. 


## -syntax

````
VOID WDF_USB_PIPE_INFORMATION_INIT(
  _Out_ PWDF_USB_PIPE_INFORMATION Info
);
````


## -parameters

### -param Info [out]

A pointer to a <a href="wdf.wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a> structure. 

## -returns
None

## -remarks
The <b>WDF_USB_PIPE_INFORMATION_INIT</b> function zeros the WDF_USB_PIPE_INFORMATION structure and sets the structure's <b>Size</b> member.

For a code example that uses <b>WDF_USB_PIPE_INFORMATION_INIT</b>, see <a href="wdf.wdfusbinterfacegetendpointinformation">WdfUsbInterfaceGetEndpointInformation</a>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfusb.h (include Wdfusb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_PIPE_INFORMATION_INIT function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
