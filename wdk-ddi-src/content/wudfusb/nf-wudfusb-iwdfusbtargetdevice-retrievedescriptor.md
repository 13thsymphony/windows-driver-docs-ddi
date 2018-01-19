---
UID : NF:wudfusb.IWDFUsbTargetDevice.RetrieveDescriptor
title : IWDFUsbTargetDevice::RetrieveDescriptor method
author : windows-driver-content
description : The RetrieveDescriptor method retrieves a USB descriptor, which can describe a device, configuration, or string.
old-location : wdf\iwdfusbtargetdevice_retrievedescriptor.htm
old-project : wdf
ms.assetid : c97b399e-fb25-475a-a2a0-0cf4fb24433c
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IWDFUsbTargetDevice, IWDFUsbTargetDevice::RetrieveDescriptor, RetrieveDescriptor
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
req.alt-api : IWDFUsbTargetDevice.RetrieveDescriptor
req.alt-loc : WUDFx.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : WUDFx.dll
req.irql : 
req.typenames : "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product : Windows 10 or later.
---


# RetrieveDescriptor method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveDescriptor</b> method retrieves a USB descriptor, which can describe a device, configuration, or string.

## Syntax

````
HRESULT RetrieveDescriptor(
  [in]      UCHAR  DescriptorType,
  [in]      UCHAR  Index,
  [in]      USHORT LanguageID,
  [in, out] ULONG  *BufferLength,
  [out]     PVOID  Buffer
);
````

## Parameters

`DescriptorType`

A value that specifies the type of descriptor to return. This parameter corresponds to the <b>bDescriptorType</b> field of a standard device descriptor, whose values are described in the <i>Universal Serial Bus</i> specification. (This resource may not be available in some languages 

and countries.) Some of these values are listed in the description of the DescriptorType member of the <a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a> structure.

`Index`

The index of the descriptor, according to the <i>Universal Serial Bus</i> specification. (This resource may not be available in some languages 

and countries.)

`LanguageID`

The identifier of the language, if the UMDF driver requests a string descriptor; otherwise, this parameter is zero.

`BufferLength`

A pointer to a variable that, on input, contains the size, in bytes, of the buffer that the <i>Buffer</i> points to. If the operation succeeds, the variable receives the number of bytes that the framework copied into the buffer.

`Buffer`

A pointer to a caller-supplied buffer that receives the USB descriptor. The type of buffer should match the value specified in <i>DescriptorType</i>.


## Return Value

<b>RetrieveDescriptor</b> returns one of the following values: 
<dl>
<dt><b>S_OK </b></dt>
</dl>
<a href="https://msdn.microsoft.com/c97b399e-fb25-475a-a2a0-0cf4fb24433c">RetrieveDescriptor</a> successfully retrieved the USB descriptor. 
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
<a href="https://msdn.microsoft.com/c97b399e-fb25-475a-a2a0-0cf4fb24433c">RetrieveDescriptor</a> encountered an allocation failure.
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>This value corresponds to the error code that the WinUsb API returned.

## Remarks

For information about valid descriptor types that a UMDF driver can pass for the <i>DescriptorType</i> parameter, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540257">WinUsb_GetDescriptor</a> function.

The <b>RetrieveDescriptor</b> method generates a UMDF request and synchronously sends the request to the I/O target.

The following code example retrieves a USB configuration descriptor.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfusb.h (include Wudfusb.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540257">WinUsb_GetDescriptor</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetDevice::RetrieveDescriptor method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>