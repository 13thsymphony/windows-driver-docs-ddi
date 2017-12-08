---
UID: NI.hidport.IOCTL_UMDF_HID_SET_FEATURE
title: IOCTL_UMDF_HID_SET_FEATURE
author: windows-driver-content
description: The IOCTL_UMDF_HID_GET_FEATURE control code sends a feature report to a HIDClass device.
old-location: hid\ioctl_umdf_hid_set_feature.htm
old-project: hid
ms.assetid: 7FFE7301-1C03-4221-9E3B-412FE89919FB
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: HidRegisterMinidriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hidport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: IOCTL_UMDF_HID_SET_FEATURE
req.alt-loc: Hidport.h
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
---

# IOCTL_UMDF_HID_SET_FEATURE IOCTL



## -description
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439657">IOCTL_UMDF_HID_GET_FEATURE</a> 
   control code sends a <a href="https://msdn.microsoft.com/477FF911-5A17-4EA5-9403-1D7B4E8B3BA5">feature report</a> to a HIDClass device.


## -syntax

````
UCHAR reportId;
SIZE_T outBufferSize;

FxRequest->GetDeviceIoControlParameters(NULL, NULL, &outBufferSize);
reportId = (UCHAR)outBufferSize;

````


## -ioctlparameters

### -input-buffer
A UMDF-based driver calls <a href="wdf.iwdfiorequest_getinputmemory">IWDFRequest::GetInputMemory</a> to retrieve a  requester-allocated input buffer that contains a feature report.

The driver retrieves the report ID associated with the top-level collection by calling <a href="wdf.iwdfiorequest_getdeviceiocontrolparameters">IWDFRequest::GetDeviceIoControlParameters</a> and providing the  <i>pOutBufferSize</i> parameter, as shown in the following example.<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>UCHAR reportId;
SIZE_T outBufferSize;

FxRequest-&gt;GetDeviceIoControlParameters(NULL, NULL, &amp;outBufferSize);
reportId = (UCHAR)outBufferSize;
</pre>
</td>
</tr>
</table></span></div>


### -input-buffer-length
None.

### -output-buffer
None.

### -output-buffer-length
The size of the buffer that is retrieved by calling <a href="wdf.iwdfiorequest_getoutputmemory">IWDFIoRequest::GetOutputMemory</a>.

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
HID minidrivers that carry out the I/O to the device must also:

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
1.11
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Hidport.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_set_feature.md">IOCTL_HID_SET_FEATURE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439657">IOCTL_UMDF_HID_GET_FEATURE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\wdf]:%20IOCTL_UMDF_HID_SET_FEATURE control code%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
