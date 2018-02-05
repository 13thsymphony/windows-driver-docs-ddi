---
UID : NF:wdfusb.WdfUsbInterfaceGetInterfaceNumber
title : WdfUsbInterfaceGetInterfaceNumber function
author : windows-driver-content
description : The WdfUsbInterfaceGetInterfaceNumber method returns the interface number of a specified USB interface object.
old-location : wdf\wdfusbinterfacegetinterfacenumber.htm
old-project : wdf
ms.assetid : bc39e3ae-6899-423d-be1d-b3322efface8
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : DFUsbRef_035fbae3-67d4-4df6-8718-30851a0d60ca.xml, kmdf.wdfusbinterfacegetinterfacenumber, WdfUsbInterfaceGetInterfaceNumber, WdfUsbInterfaceGetInterfaceNumber method, wdfusb/WdfUsbInterfaceGetInterfaceNumber, PFN_WDFUSBINTERFACEGETINTERFACENUMBER, wdf.wdfusbinterfacegetinterfacenumber
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfusb.h
req.include-header : Wdfusb.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product : Windows 10 or later.
---


# WdfUsbInterfaceGetInterfaceNumber function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbInterfaceGetInterfaceNumber</b> method returns the interface number of a specified USB interface object.

## Syntax

````
BYTE WdfUsbInterfaceGetInterfaceNumber(
  _In_ WDFUSBINTERFACE UsbInterface
);
````

## Parameters

`UsbInterface`

A handle to a USB interface object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>.


## Return Value

<b>WdfUsbInterfaceGetInterfaceNumber</b> returns the interface number. 

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about interface numbers, see the USB specification.

For more information about the <b>WdfUsbInterfaceGetInterfaceNumber</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2 |

## See Also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbInterfaceGetInterfaceNumber method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>