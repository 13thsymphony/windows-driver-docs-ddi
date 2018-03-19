---
UID: NF:wudfusb.IWDFUsbTargetDevice.RetrieveUsbInterface
title: IWDFUsbTargetDevice::RetrieveUsbInterface method
author: windows-driver-content
description: The RetrieveUsbInterface method retrieves the specified USB interface for a USB device.
old-location: wdf\iwdfusbtargetdevice_retrieveusbinterface.htm
old-project: wdf
ms.assetid: 9dfa8686-a815-417c-9488-dd86de0e15a2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFUsbTargetDevice, IWDFUsbTargetDevice interface, RetrieveUsbInterface method, IWDFUsbTargetDevice::RetrieveUsbInterface, RetrieveUsbInterface method, RetrieveUsbInterface method, IWDFUsbTargetDevice interface, RetrieveUsbInterface,IWDFUsbTargetDevice.RetrieveUsbInterface, UMDFUSBref_cc346a35-4508-40ac-b959-20174a1b39af.xml, umdf.iwdfusbtargetdevice_retrieveusbinterface, wdf.iwdfusbtargetdevice_retrieveusbinterface, wudfusb/IWDFUsbTargetDevice::RetrieveUsbInterface
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFUsbTargetDevice.RetrieveUsbInterface
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# RetrieveUsbInterface method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveUsbInterface</b> method retrieves the specified USB interface for a USB device.

## Syntax

````
HRESULT RetrieveUsbInterface(
  [in]  UCHAR            InterfaceIndex,
  [out] IWDFUsbInterface **ppUsbInterface
);
````

## Parameters

`InterfaceIndex`

The index of the interface to retrieve.

`ppUsbInterface`

A pointer to a variable that receives a pointer to the specified <a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a> interface for the USB device.


## Return Value

<b>RetrieveUsbInterface</b> returns one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/9dfa8686-a815-417c-9488-dd86de0e15a2">RetrieveUsbInterface</a> successfully retrieved the specified USB interface for the USB device. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/9dfa8686-a815-417c-9488-dd86de0e15a2">RetrieveUsbInterface</a> encountered an allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>
</td>
<td width="60%">
This value corresponds to the error code that the WinUsb API returned.

</td>
</tr>
</table>

## Remarks

The driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560366">IWDFUsbTargetDevice::GetNumInterfaces</a> method to retrieve the total number of USB interfaces that are available. 

The driver can use the interface pointer that <b>RetrieveUsbInterface</b> retrieves, to call the methods that the <a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a> interface provides. For more information about using these methods, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/working-with-usb-interfaces-in-umdf-1-x-drivers">Working with USB Interfaces in UMDF</a>.


#### Examples

For a code example of how to use the <b>RetrieveUsbInterface</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560390">IWDFUsbTargetFactory::CreateUsbTargetDevice</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfusb.h (include Wudfusb.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560366">IWDFUsbTargetDevice::GetNumInterfaces</a>



<a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a>



<a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a>