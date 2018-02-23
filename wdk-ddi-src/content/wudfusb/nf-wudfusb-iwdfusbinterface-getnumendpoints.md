---
UID: NF:wudfusb.IWDFUsbInterface.GetNumEndPoints
title: IWDFUsbInterface::GetNumEndPoints method
author: windows-driver-content
description: The GetNumEndPoints method retrieves the number of endpoints (pipes) on a USB interface.
old-location: wdf\iwdfusbinterface_getnumendpoints.htm
old-project: wdf
ms.assetid: 60ec8b38-8ab2-45d8-92ab-5943fd9bba79
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wudfusb/IWDFUsbInterface::GetNumEndPoints, GetNumEndPoints, wdf.iwdfusbinterface_getnumendpoints, IWDFUsbInterface::GetNumEndPoints, IWDFUsbInterface, GetNumEndPoints method, IWDFUsbInterface interface, GetNumEndPoints method, GetNumEndPoints method, IWDFUsbInterface interface, UMDFUSBref_ae1352c4-217e-49fd-9275-6c80103af753.xml, umdf.iwdfusbinterface_getnumendpoints
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
req.lib: wudfusb.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFUsbInterface.GetNumEndPoints
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---


# GetNumEndPoints method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetNumEndPoints</b> method retrieves the number of endpoints (pipes) on a USB interface.

## Syntax

````
UCHAR GetNumEndPoints();
````

## Parameters

This function has no parameters.

## Return Value

<b>GetNumEndPoints</b> returns the number of endpoints on the USB interface.

## Remarks

The <b>GetNumEndPoints</b> method is provided for convenience because a UMDF driver can obtain the number of endpoints from the <b>bNumEndpoints</b> member of the <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> structure that the driver retrieves when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560320">IWDFUsbInterface::GetInterfaceDescriptor</a> method. 


#### Examples

The following code example retrieves the number of pipes on a USB interface and then retrieves particular types of pipes.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre> HRESULT  hr;
 UCHAR  NumEndPoints;
 NumEndPoints = pIUsbInterface-&gt;GetNumEndPoints();

 if (NumEndPoints != NUM_OSRUSB_ENDPOINTS) {
     hr = E_UNEXPECTED;
 }
 if (SUCCEEDED(hr))  {
     for (UCHAR PipeIndex = 0; PipeIndex &lt; NumEndPoints; PipeIndex++) {
     hr = pIUsbInterface-&gt;RetrieveUsbPipeObject(PipeIndex, 
                                                &amp;pIUsbPipe);
     if (FAILED(hr)) {
        // Output an error.
     }
     else {
         if ( pIUsbPipe-&gt;IsInEndPoint() &amp;&amp; (UsbdPipeTypeBulk == pIUsbPipe-&gt;GetType()) ) {
             pIUsbInputPipe = pIUsbPipe;
         }
         else if ( pIUsbPipe-&gt;IsOutEndPoint() &amp;&amp; (UsbdPipeTypeBulk == pIUsbPipe-&gt;GetType()) )
         {
              pIUsbOutputPipe = pIUsbPipe;
         }
         else
              {
                  SAFE_RELEASE(pIUsbPipe);
              }
          }</pre>
</td>
</tr>
</table></span></div>

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

<a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560320">IWDFUsbInterface::GetInterfaceDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560320">IWDFUsbInterface::GetInterfaceDescriptor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbInterface::GetNumEndPoints method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>