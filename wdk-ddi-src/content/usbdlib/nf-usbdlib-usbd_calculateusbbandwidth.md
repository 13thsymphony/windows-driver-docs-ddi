---
UID: NF.usbdlib.USBD_CalculateUsbBandwidth
title: USBD_CalculateUsbBandwidth function
author: windows-driver-content
description: The USBD_CalculateUsbBandwidth routine has been deprecated in Windows XP and later operating systems. Do not use.
old-location: buses\usbd_calculateusbbandwidth.htm
old-project: usbref
ms.assetid: a54f3fb4-032a-4538-8b6d-20d6834d08c4
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: USBD_CalculateUsbBandwidth
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Universal
req.target-min-winverclnt: Deprecated.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBD_CalculateUsbBandwidth
req.alt-loc: Usbd.lib,Usbd.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Usbd.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# USBD_CalculateUsbBandwidth function



## -description
The <b>USBD_CalculateUsbBandwidth</b> routine has been deprecated in Windows XP and later operating systems. Do not use. 


## -syntax

````
ULONG USBD_CalculateUsbBandwidth(
  _In_ ULONG   MaxPacketSize,
  _In_ UCHAR   EndpointType,
  _In_ BOOLEAN LowSpeed
);
````


## -parameters

### -param MaxPacketSize [in]

Specifies the maximum packet size. 

### -param EndpointType [in]

Contains a value of type <a href="buses.usbd_pipe_type">USBD_PIPE_TYPE</a> that specifies the pipe type.

### -param LowSpeed [in]

Indicates, when <b>TRUE</b>, that the device is a low speed device. When <b>FALSE</b>, this member indicates that the device is a hi-speed device. 

## -returns
The <b>USBD_CalculateUsbBandwidth</b> routine returns zero for bulk and control endpoints and the bandwidth consumed in bits per millisecond. returns for all other endpoints. 

## -remarks
The <b>USBD_CalculateUsbBandwidth</b> routine approximates the bandwidth using the following procedure. First, <b>USBD_CalculateUsbBandwidth</b> adds the largest possible packet size, specified in <i>MaxPacketSize</i>, to the overhead associated with the type of end point specified in <i>EndpointType</i>. Next, <b>USBD_CalculateUsbBandwidth</b> multiplies this sum by 8 to convert the units from <i>bytes</i> per millisecond into <i>bits</i> per millisecond. Finally, <b>USBD_CalculateUsbBandwidth</b> multiplies this quantity by 7/6 to account for filler bits. In a worst case scenario, there will be one bit of filler data stuffed into the data stream for every six bits of data. <b>USBD_CalculateUsbBandwidth</b> uses worst-case assumptions to calculate the bandwidth required by the pipe. 

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
Version
</th>
<td width="70%">
Deprecated.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Usbdlib.h (include Usbdlib.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Usbd.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;=DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.usbd_pipe_type">USBD_PIPE_TYPE</a>
</dt>
<dt><a href="usb_reference.htm#client">USB device driver programming reference</a></dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_CalculateUsbBandwidth routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
