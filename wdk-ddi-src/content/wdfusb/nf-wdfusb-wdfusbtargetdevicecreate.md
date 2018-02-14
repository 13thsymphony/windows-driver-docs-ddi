---
UID: NF:wdfusb.WdfUsbTargetDeviceCreate
title: WdfUsbTargetDeviceCreate function
author: windows-driver-content
description: The WdfUsbTargetDeviceCreate method creates a framework USB device object for a specified framework device object and opens the USB device for I/O operations.
old-location: wdf\wdfusbtargetdevicecreate.htm
old-project: wdf
ms.assetid: 5a2d3430-ca94-42f0-bfeb-fd38d9d4958a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfusb/WdfUsbTargetDeviceCreate, DFUsbRef_be9c210e-6cf0-4e0b-a5d5-f0b02d7a2141.xml, wdf.wdfusbtargetdevicecreate, PFN_WDFUSBTARGETDEVICECREATE, WdfUsbTargetDeviceCreate method, WdfUsbTargetDeviceCreate, kmdf.wdfusbtargetdevicecreate
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
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbDeviceCreate, UsbDeviceCreateFail, UsbDeviceCreateTarget, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfUsbTargetDeviceCreate
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---


# WdfUsbTargetDeviceCreate function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceCreate</b> method creates a framework USB device object for a specified framework device object and opens the USB device for I/O operations.
<div class="alert"><b>Note</b>  If you are building your driver using KMDF 1.11 or UMDF 2.0, or later, we recommend that you call <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a> instead of  <b>WdfUsbTargetDeviceCreate</b>.</div><div> </div>

## Syntax

````
NTSTATUS WdfUsbTargetDeviceCreate(
  _In_     WDFDEVICE              Device,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES Attributes,
  _Out_    WDFUSBDEVICE           *UsbDevice
);
````

## Parameters

`Device`

A handle to a framework device object.

`Attributes`

A pointer to a caller-supplied <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new USB device object. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

`UsbDevice`

A pointer to a location that receives a handle to the new framework USB device object.


## Return Value

<b>WdfUsbTargetDeviceCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

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
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory to create a new USB device object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
An attempt to get USB configuration information failed.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfUsbTargetDeviceCreate</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

A driver that uses a USB I/O target must call <b>WdfUsbTargetDeviceCreate</b> after its device enters its working (D0) state. Typically, a driver calls <b>WdfUsbTargetDeviceCreate</b> from within its <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function. (The driver cannot call <b>WdfUsbTargetDeviceCreate</b> from within its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.)

<b>WdfUsbTargetDeviceCreate</b> obtains the USB device descriptor and the first USB configuration descriptor from the device and stores them. It also creates a framework USB interface object for each interface in the device's first configuration. To determine the number of interfaces that the configuration supports, the driver can call <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetnuminterfaces.md">WdfUsbTargetDeviceGetNumInterfaces</a>.

After calling <b>WdfUsbTargetDeviceCreate</b>, your driver can call additional <a href="https://msdn.microsoft.com/CDD13B29-62C8-4CF7-9027-E55A5B37AA2E">framework USB device object methods</a>.

The parent of each USB device object is the driver's framework driver object. The driver cannot change this parent, and the <b>ParentObject</b> member or the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>.

For more information about the <b>WdfUsbTargetDeviceCreate</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example is part of an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function that calls <b>WdfUsbTargetDeviceCreate</b>. The example stores the USB device object's handle in driver-defined context space. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
MyEvtDevicePrepareHardware(
    IN WDFDEVICE  Device,
    IN WDFCMRESLIST  ResourceList,
    IN WDFCMRESLIST  ResourceListTranslated
    )
{
    NTSTATUS  status;
    PMY_DEVICE_CONTEXT  pMyDeviceContext;

    pMyDeviceContext = GetDeviceContext(Device);

    // If object handle is not NULL, MyEvtDevicePrepareHardware
    // was called previously and the handle is still valid.
    if (pMyDeviceContext-&gt;UsbDevice != NULL) {
        return STATUS_SUCCESS;
    }
 status = WdfUsbTargetDeviceCreate(
                                      Device,
                                      WDF_NO_OBJECT_ATTRIBUTES,
                                      &amp;pMyDeviceContext-&gt;UsbDevice
                                      );
    if (!NT_SUCCESS(status)) {
        return status;
    }
...
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2, UsbDeviceCreate, UsbDeviceCreateFail, UsbDeviceCreateTarget, UsbKmdfIrql, UsbKmdfIrql2 |

## See Also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetnuminterfaces.md">WdfUsbTargetDeviceGetNumInterfaces</a>



<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceCreate method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>