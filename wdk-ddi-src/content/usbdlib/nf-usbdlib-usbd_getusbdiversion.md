---
UID : NF:usbdlib.USBD_GetUSBDIVersion
title : USBD_GetUSBDIVersion function
author : windows-driver-content
description : The USBD_GetUSBDIVersion routine returns version information about the host controller driver (HCD) that controls the client's USB device.Note  USBD_IsInterfaceVersionSupported replaces the USBD_GetUSBDIVersion routine
old-location : buses\usbd_getusbdiversion.htm
old-project : usbref
ms.assetid : 47e6da4a-fa81-40ee-9bf5-80526dc0b865
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : USBD_GetUSBDIVersion routine [Buses], usbdlib/USBD_GetUSBDIVersion, USBD_GetUSBDIVersion, buses.usbd_getusbdiversion, usbfunc_567ca75b-8d65-412c-aa28-284a01cff650.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : usbdlib.h
req.include-header : Usbdlib.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Usbd.lib
req.dll : 
req.irql : "<=DISPATCH_LEVEL (See Remarks)"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PUSBCAMD_DEVICE_DATA2, USBCAMD_DEVICE_DATA2"
req.product : Windows 10 or later.
---


# USBD_GetUSBDIVersion function
The <b>USBD_GetUSBDIVersion</b> routine returns version information about the host controller driver (HCD) that controls the client's USB device.
<div class="alert"><b>Note</b>  <a href="..\usbdlib\nf-usbdlib-usbd_isinterfaceversionsupported.md">USBD_IsInterfaceVersionSupported</a> replaces the <b>USBD_GetUSBDIVersion</b>  routine</div><div> </div>

## Syntax

````
void USBD_GetUSBDIVersion(
  _Out_ PUSBD_VERSION_INFORMATION VersionInformation
);
````

## Parameters

`VersionInformation`

Pointer to caller-allocated memory for a <a href="..\usb\ns-usb-_usbd_version_information.md">USBD_VERSION_INFORMATION</a> structure that on return from the routine, contains version information about the HCD.


## Return Value

This routine does not return a value.

## Remarks

Callers of this routine can be running at IRQL &lt;= DISPATCH_LEVEL if the memory for <i>VersionInformation</i> is allocated from nonpaged pool. Otherwise, callers must be running at IRQL &lt; DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbdlib.h (include Usbdlib.h) |
| **Library** |  |
| **IRQL** | "<=DISPATCH_LEVEL (See Remarks)" |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>

<a href="..\usbdlib\nf-usbdlib-usbd_isinterfaceversionsupported.md">USBD_IsInterfaceVersionSupported</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_GetUSBDIVersion routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>