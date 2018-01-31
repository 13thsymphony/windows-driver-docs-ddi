---
UID : NE:wdfusb._WdfUsbTargetDeviceSelectConfigType
title : "_WdfUsbTargetDeviceSelectConfigType"
author : windows-driver-content
description : The WdfUsbTargetDeviceSelectConfigType enumeration defines types of configuration operations for USB devices.
old-location : wdf\wdfusbtargetdeviceselectconfigtype.htm
old-project : wdf
ms.assetid : d3637f5e-d4c1-430c-8511-8aac18fceee2
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : kmdf.wdfusbtargetdeviceselectconfigtype, wdfusb/WdfUsbTargetDeviceSelectConfigTypeDeconfig, wdfusb/WdfUsbTargetDeviceSelectConfigTypeMultiInterface, WdfUsbTargetDeviceSelectConfigTypeInvalid, WdfUsbTargetDeviceSelectConfigType, WdfUsbTargetDeviceSelectConfigTypeMultiInterface, WdfUsbTargetDeviceSelectConfigType enumeration, WdfUsbTargetDeviceSelectConfigTypeUrb, DFUsbRef_e4ab4d2c-dbca-4d6e-a690-4b362331e53e.xml, WdfUsbTargetDeviceSelectConfigTypeSingleInterface, WdfUsbTargetDeviceSelectConfigTypeDeconfig, wdfusb/WdfUsbTargetDeviceSelectConfigTypeUrb, WdfUsbTargetDeviceSelectConfigTypeInterfacesDescriptor, wdfusb/WdfUsbTargetDeviceSelectConfigTypeInvalid, wdfusb/WdfUsbTargetDeviceSelectConfigTypeInterfacesDescriptor, WdfUsbTargetDeviceSelectConfigTypeInterfacesPairs, wdfusb/WdfUsbTargetDeviceSelectConfigTypeSingleInterface, wdf.wdfusbtargetdeviceselectconfigtype, wdfusb/WdfUsbTargetDeviceSelectConfigTypeInterfacesPairs, _WdfUsbTargetDeviceSelectConfigType, wdfusb/WdfUsbTargetDeviceSelectConfigType
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wdfusb.h
req.include-header : Wdfusb.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<=DISPATCH_LEVEL  (See Remarks section.)"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WdfUsbTargetDeviceSelectConfigType
req.product : Windows 10 or later.
---

# _WdfUsbTargetDeviceSelectConfigType Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceSelectConfigType</b> enumeration defines types of configuration operations for USB devices.

## Syntax
````
typedef enum _WdfUsbTargetDeviceSelectConfigType { 
  WdfUsbTargetDeviceSelectConfigTypeInvalid               = 0,
  WdfUsbTargetDeviceSelectConfigTypeDeconfig              = 1,
  WdfUsbTargetDeviceSelectConfigTypeSingleInterface       = 2,
  WdfUsbTargetDeviceSelectConfigTypeMultiInterface        = 3,
  WdfUsbTargetDeviceSelectConfigTypeInterfacesPairs       = 4,
  WdfUsbTargetDeviceSelectConfigTypeInterfacesDescriptor  = 5,
  WdfUsbTargetDeviceSelectConfigTypeUrb                   = 6
} WdfUsbTargetDeviceSelectConfigType;
````

## Constants

<table>

<tr>
<td>WdfUsbTargetDeviceSelectConfigTypeDeconfig</td>
<td>Deconfigure the device. This value applies to KMDF only.</td>
</tr>

<tr>
<td>WdfUsbTargetDeviceSelectConfigTypeInterfacesDescriptor</td>
<td>Configure the device by using configuration parameters that are contained in USB descriptors. This value applies to KMDF only.</td>
</tr>

<tr>
<td>WdfUsbTargetDeviceSelectConfigTypeInterfacesPairs</td>
<td>Configure the device to use multiple interfaces, possibly with alternate settings. Alternate settings are described in the USB specification.  This value applies to KMDF and UMDF.</td>
</tr>

<tr>
<td>WdfUsbTargetDeviceSelectConfigTypeInvalid</td>
<td>For internal use only.</td>
</tr>

<tr>
<td>WdfUsbTargetDeviceSelectConfigTypeMultiInterface</td>
<td>Configure the device to use multiple interfaces. This value applies to KMDF and UMDF.</td>
</tr>

<tr>
<td>WdfUsbTargetDeviceSelectConfigTypeSingleInterface</td>
<td>Configure the device to use a single, specified interface. This value applies to KMDF and UMDF.</td>
</tr>

<tr>
<td>WdfUsbTargetDeviceSelectConfigTypeUrb</td>
<td>Configure the device by using configuration parameters that are contained in a driver-supplied URB structure. This value applies to KMDF only.</td>
</tr>
</table>

## Remarks

The <b>WdfUsbTargetDeviceSelectConfigType</b> enumeration is used to specify the <b>Type</b> member of the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_select_config_params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure. That structure is used as input to the <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |

## See Also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a>

<a href="..\usb\ns-usb-_urb.md">URB</a>

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_select_config_params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceSelectConfigType enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>