---
UID: NF:wdfusb.WdfUsbTargetDeviceCreateUrb
title: WdfUsbTargetDeviceCreateUrb function
author: windows-driver-content
description: The WdfUsbTargetDeviceCreateUrb method allocates a USB request block (URB).
old-location: wdf\wdfusbtargetdevicecreateurb.htm
old-project: wdf
ms.assetid: 274232FF-573A-47B4-B363-2FA7F810BF84
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFUSBTARGETDEVICECREATEURB, wdfusb/WdfUsbTargetDeviceCreateUrb, wdf.wdfusbtargetdevicecreateurb, kmdf.wdfusbtargetdevicecreateurb, WdfUsbTargetDeviceCreateUrb method, WdfUsbTargetDeviceCreateUrb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfUsbTargetDeviceCreateUrb
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---


# WdfUsbTargetDeviceCreateUrb function
<p class="CCE_Message">[Applies to KMDF only]


   The 
  <b>WdfUsbTargetDeviceCreateUrb</b> method allocates a USB request block (URB).

## Syntax

````
NTSTATUS WdfUsbTargetDeviceCreateUrb(
  _In_      WDFUSBDEVICE           UsbDevice,
  _In_opt_  PWDF_OBJECT_ATTRIBUTES Attributes,
  _Out_     WDFMEMORY              *UrbMemory,
  _Out_opt_ PURB                   *Urb
);
````

## Parameters

`UsbDevice`

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.

`Attributes`

A pointer to a caller-supplied <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new memory object.   If the driver provides this parameter, the structure's <b>ParentObject</b> member must be a USB device object (WDFUSBDEVICE) or a request object (WDFREQUEST) created by the framework, or any object whose chain of parents leads to one of these types. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

`UrbMemory`

A pointer to a WDFMEMORY-typed location that receives a handle to a framework memory object.

`Urb`

A pointer to an URB structure that receives the address of the newly allocated URB. This parameter is optional and can be NULL.


## Return Value

<b>WdfUsbTargetDeviceCreateUrb</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The driver did not specify a client contract version when it called <a href="..\wdfusb\nf-wdfusb-wdf_usb_device_create_config_init.md">WDF_USB_DEVICE_CREATE_CONFIG_INIT</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory to create a new URB.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

Before calling <b>WdfUsbTargetDeviceCreateUrb</b>, a driver must call <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>. If successful, <b>WdfUsbTargetDeviceCreateUrb</b> returns a handle to a framework memory object that describes the newly allocated URB. Typically, a driver calls <b>WdfUsbTargetDeviceCreateUrb</b> from within a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a>.

A driver can call <b>WdfUsbTargetDeviceCreateUrb</b> to allocate an URB structure before calling <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforurb.md">WdfUsbTargetDeviceFormatRequestForUrb</a>.

<b>WdfUsbTargetDeviceCreateUrb</b> is similar in operation to  <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a>. Both methods allocate a framework memory object, and both methods also provide the option of receiving the buffer (in this case, the URB) associated with the memory object. In both cases, the caller can also retrieve the buffer later by calling <a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a>.

If the driver provides an <i>Urb</i> parameter when it calls <b>WdfUsbTargetDeviceCreateUrb</b>, you can format the URB manually or by calling the UsbBuildXxx routines.

The memory object and its buffer are deleted when the parent object is deleted. A driver can also delete a memory object and its buffer by calling <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>.


#### Examples

The following code example declares a framework memory object. The example calls <b>WdfUsbTargetDeviceCreateUrb</b> to allocate a USB request block, and then calls <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforurb.md">WdfUsbTargetDeviceFormatRequestForUrb</a> to format a request that uses the URB structure's contents. Finally, the example registers a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function and sends the request to an I/O target.


<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFMEMORY memory;
PURB urb = NULL;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;objectAttribs);  
objectAttribs.ParentObject = UsbDevice;

status = WdfUsbTargetDeviceCreateUrb(
                                     pDevContext-&gt;WdfUsbTargetDevice,  
                                     &amp;objectAttribs,  
                                     &amp;memory,  
                                     &amp;urb  
                                     ); 
 
status = WdfUsbTargetDeviceFormatRequestForUrb(
                                               deviceContext-&gt;WdfUsbTargetDevice,
                                               request,
                                               memory,
                                               NULL
                                               );
WdfRequestSetCompletionRoutine(
                               request,
                               MyCompletionRoutine,
                               NULL
                               );

if (WdfRequestSend(
                   request,
                   WdfUsbTargetDeviceGetIoTarget(UsbDevice),
                   NULL
                   ) == FALSE) {
    status = WdfRequestGetStatus(request);
}

</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows Vista  |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.11 |
| **Header** | wdfusb.h (include Wdfusb.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate |

## See Also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreateisochurb.md">WdfUsbTargetDeviceCreateIsochUrb</a>



<a href="..\wdfusb\nf-wdfusb-wdf_usb_device_create_config_init.md">WDF_USB_DEVICE_CREATE_CONFIG_INIT</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforurb.md">WdfUsbTargetDeviceFormatRequestForUrb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceCreateUrb method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>