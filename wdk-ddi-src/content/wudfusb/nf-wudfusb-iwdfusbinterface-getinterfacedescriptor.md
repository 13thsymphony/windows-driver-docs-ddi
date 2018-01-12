---
UID: NF:wudfusb.IWDFUsbInterface.GetInterfaceDescriptor
title: IWDFUsbInterface::GetInterfaceDescriptor method
author: windows-driver-content
description: The GetInterfaceDescriptor method retrieves a descriptor for a USB interface.
old-location: wdf\iwdfusbinterface_getinterfacedescriptor.htm
old-project: wdf
ms.assetid: ae4cffc8-65db-452c-9b85-19752c32c421
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IWDFUsbInterface, IWDFUsbInterface::GetInterfaceDescriptor, GetInterfaceDescriptor
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
req.alt-api: IWDFUsbInterface.GetInterfaceDescriptor
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

# IWDFUsbInterface::GetInterfaceDescriptor method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInterfaceDescriptor</b> method retrieves a descriptor for a USB interface.



## -syntax

````
void GetInterfaceDescriptor(
  [out] PUSB_INTERFACE_DESCRIPTOR UsbAltInterfaceDescriptor
);
````


## -parameters

### -param UsbAltInterfaceDescriptor [out]

A pointer to a variable that receives the USB interface descriptor.


## -returns
None


## -remarks
After a UMDF driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560381">IWDFUsbTargetDevice::RetrieveUsbInterface</a> method to retrieve the first USB interface for the USB device, a UMDF driver should retrieve the descriptor for the USB interface. Therefore, the <b>GetInterfaceDescriptor</b> method does not fail.

For a code example of how to use the <b>GetInterfaceDescriptor</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560390">IWDFUsbTargetFactory::CreateUsbTargetDevice</a>.


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
<a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560381">IWDFUsbTargetDevice::RetrieveUsbInterface</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbInterface::GetInterfaceDescriptor method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

