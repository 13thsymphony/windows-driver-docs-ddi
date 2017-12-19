---
UID: NF.wudfusb.IWDFUsbTargetDevice.RetrieveDescriptor
title: IWDFUsbTargetDevice::RetrieveDescriptor method
author: windows-driver-content
description: The RetrieveDescriptor method retrieves a USB descriptor, which can describe a device, configuration, or string.
old-location: wdf\iwdfusbtargetdevice_retrievedescriptor.htm
old-project: wdf
ms.assetid: c97b399e-fb25-475a-a2a0-0cf4fb24433c
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFUsbTargetDevice, IWDFUsbTargetDevice::RetrieveDescriptor, RetrieveDescriptor
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
req.alt-api: IWDFUsbTargetDevice.RetrieveDescriptor
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
req.product: Windows 10 or later.
---

# IWDFUsbTargetDevice::RetrieveDescriptor method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveDescriptor</b> method retrieves a USB descriptor, which can describe a device, configuration, or string.



## -syntax

````
HRESULT RetrieveDescriptor(
  [in]      UCHAR  DescriptorType,
  [in]      UCHAR  Index,
  [in]      USHORT LanguageID,
  [in, out] ULONG  *BufferLength,
  [out]     PVOID  Buffer
);
````


## -parameters

### -param DescriptorType [in]

A value that specifies the type of descriptor to return. This parameter corresponds to the <b>bDescriptorType</b> field of a standard device descriptor, whose values are described in the <i>Universal Serial Bus</i> specification. (This resource may not be available in some languages 

and countries.) Some of these values are listed in the description of the DescriptorType member of the <a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a> structure.



### -param Index [in]

The index of the descriptor, according to the <i>Universal Serial Bus</i> specification. (This resource may not be available in some languages 

and countries.)


### -param LanguageID [in]

The identifier of the language, if the UMDF driver requests a string descriptor; otherwise, this parameter is zero. 


### -param BufferLength [in, out]

A pointer to a variable that, on input, contains the size, in bytes, of the buffer that the <i>Buffer</i> points to. If the operation succeeds, the variable receives the number of bytes that the framework copied into the buffer.


### -param Buffer [out]

A pointer to a caller-supplied buffer that receives the USB descriptor. The type of buffer should match the value specified in <i>DescriptorType</i>.


## -returns
<b>RetrieveDescriptor</b> returns one of the following values: 
<dl>
<dt><b>S_OK </b></dt>
</dl>
<a href="wdf.iwdfusbtargetdevice_retrievedescriptor">RetrieveDescriptor</a> successfully retrieved the USB descriptor. 
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
<a href="wdf.iwdfusbtargetdevice_retrievedescriptor">RetrieveDescriptor</a> encountered an allocation failure.
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>This value corresponds to the error code that the WinUsb API returned.

 


## -remarks
For information about valid descriptor types that a UMDF driver can pass for the <i>DescriptorType</i> parameter, see the <a href="buses.winusb_getdescriptor">WinUsb_GetDescriptor</a> function.

The <b>RetrieveDescriptor</b> method generates a UMDF request and synchronously sends the request to the I/O target.

The following code example retrieves a USB configuration descriptor.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.5

</td>
</tr>
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
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a>
</dt>
<dt>
<a href="buses.winusb_getdescriptor">WinUsb_GetDescriptor</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetDevice::RetrieveDescriptor method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

