---
UID: NF.hwnclx.HwNProcessAddDevicePreDeviceCreate
title: HwNProcessAddDevicePreDeviceCreate function
author: windows-driver-content
description: Supplies the device prepare/release and entry/exit callbacks to the Windows Driver Foundation (WDF) for transitioning the device into different states.
old-location: gpiobtn\hwnprocessadddevicepredevicecreate.htm
old-project: gpiobtn
ms.assetid: c7bbba08-e9d0-4f78-93d8-e451e4dc2573
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: HwNProcessAddDevicePreDeviceCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hwnclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HwNProcessAddDevicePreDeviceCreate
req.alt-loc: Mshwnclxstub.lib,Mshwnclxstub.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Mshwnclxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# HwNProcessAddDevicePreDeviceCreate function



## -description
Supplies the device prepare/release and entry/exit callbacks to the Windows Driver Foundation (WDF) for transitioning the device into different states. This function should be called by the client driver when the WDF invokes the driver’s <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EVT_WDF_DRIVER_DEVICE_ADD</a> routine, but before creating the device object.


## -syntax

````
FORCEINLINE NTSTATUS  HwNProcessAddDevicePreDeviceCreate(
  _In_  WDFDRIVER               Driver,
  _In_  PWDFDEVICE_INIT         DeviceInit,
  _Out_ PWDF_OBJECT_ATTRIBUTES  FdoAttributes
);
````


## -parameters

### -param Driver [in]

Handle to the client drivers framework driver object. 

### -param DeviceInit [in]

A pointer to a framework-allocated <a href="wdf.wdfdevice_init">WDFDEVICE_INIT</a> structure. 

### -param FdoAttributes [out]

Pointer to a <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that describes the attributes of the client driver’s device object when it’s created. 

## -returns
Returns STATUS_SUCCESS if function succeeds. Returns STATUS_INVALID_PARAMETER if corresponding client driver can't be found. Otherwise, it returns one of the error status values defined in Ntstatus.h.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10, version 1709
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Hwnclx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Mshwnclxstub.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt><a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn789335">Hardware notifications support</a></dt>
<dt>
<a href="gpiobtn.hardware_notifications_reference">Hardware notifications reference</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [gpiobtn\gpiobtn]:%20HwNProcessAddDevicePreDeviceCreate function%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
