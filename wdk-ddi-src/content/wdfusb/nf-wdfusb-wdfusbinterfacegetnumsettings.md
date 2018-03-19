---
UID: NF:wdfusb.WdfUsbInterfaceGetNumSettings
title: WdfUsbInterfaceGetNumSettings function
author: windows-driver-content
description: The WdfUsbInterfaceGetNumSettings method returns the number of alternate settings that a specified USB interface supports.
old-location: wdf\wdfusbinterfacegetnumsettings.htm
old-project: wdf
ms.assetid: 07de1b64-bafb-4b5b-8ef3-24b87ae0c273
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_5515a8bf-1a43-434c-9806-75393a17fdf5.xml, WdfUsbInterfaceGetNumSettings, WdfUsbInterfaceGetNumSettings method, kmdf.wdfusbinterfacegetnumsettings, wdf.wdfusbinterfacegetnumsettings, wdfusb/WdfUsbInterfaceGetNumSettings
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.5
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfUsbInterfaceGetNumSettings
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfUsbInterfaceGetNumSettings function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbInterfaceGetNumSettings</b> method returns the number of alternate settings that a specified USB interface supports.

## Syntax

````
BYTE WdfUsbInterfaceGetNumSettings(
  _In_ WDFUSBINTERFACE UsbInterface
);
````

## Parameters

`UsbInterface`

A handle to a USB interface object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>.


## Return Value

<b>WdfUsbInterfaceGetNumSettings</b> returns the number of alternate settings that the specified USB interface supports.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Your driver can call <b>WdfUsbInterfaceGetNumSettings</b> after it has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.

For more information about the <b>WdfUsbInterfaceGetNumSettings</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example obtains the number of alternate settings that are available for a specified USB interface.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BYTE altSettings;

altSettings = WdfUsbInterfaceGetNumSettings(UsbInterface);</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.5 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2 |

## See Also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a>