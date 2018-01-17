---
UID: NC:wdfdevice.PFN_WDFDEVICESETDEVICEINTERFACESTATE
title: PFN_WDFDEVICESETDEVICEINTERFACESTATE function
author: windows-driver-content
description: The WdfDeviceSetDeviceInterfaceState method enables or disables a device interface for a specified device.
old-location: wdf\wdfdevicesetdeviceinterfacestate.htm
old-project: wdf
ms.assetid: 345003fc-fdc3-4529-bb15-c9e380e77bba
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFDEVICESETDEVICEINTERFACESTATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfDeviceSetDeviceInterfaceState
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# PFN_WDFDEVICESETDEVICEINTERFACESTATE function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceSetDeviceInterfaceState</b> method enables or disables a device interface for a specified device.



## -syntax

````
VOID WdfDeviceSetDeviceInterfaceState(
  _In_           WDFDEVICE        Device,
  _In_     const GUID             *InterfaceClassGUID,
  _In_opt_       PCUNICODE_STRING ReferenceString,
  _In_           BOOLEAN          IsInterfaceEnabled
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param InterfaceClassGUID [in]

A pointer to a GUID that identifies the device interface class.


### -param ReferenceString [in, optional]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that describes a reference string for the device interface. This parameter is optional and can be <b>NULL</b>. 


### -param IsInterfaceEnabled [in]

A Boolean value that, if <b>TRUE</b>, enables the specified device interface instance or, if <b>FALSE</b>, disables it.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
For more information about device interfaces and the <b>WdfDeviceSetDeviceInterfaceState</b> method, see <a href="https://msdn.microsoft.com/98199220-947e-462e-a50c-85d81ca50108">Using Device Interfaces</a>.

The following code example disables a driver's COM port interface.


## -see-also
<dl>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreatedeviceinterface.md">WdfDeviceCreateDeviceInterface</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceSetDeviceInterfaceState method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

