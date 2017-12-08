---
UID: NF.ursdevice.UrsDeviceInitialize
title: UrsDeviceInitialize function
author: windows-driver-content
description: Initializes a framework device object to support operations related to a USB dual-role controller and registers the relevant event callback functions with the USB dual-role controller class extension.
old-location: buses\ursdeviceinitialize.htm
old-project: usbref
ms.assetid: 8A9C76C0-70F5-4F65-A460-CCFCD236A242
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UrsDeviceInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.alt-api: UrsDeviceInitialize
req.alt-loc: Urscxstub.lib,Urscxstub.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Urscxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# UrsDeviceInitialize function



## -description
Initializes a framework device object to support operations related to  a USB dual-role controller and registers the relevant event callback functions with the USB dual-role controller class extension.


## -syntax

````
FORCEINLINE NTSTATUS UrsDeviceInitialize(
  _In_ WDFDEVICE   Device,
  _In_ PURS_CONFIG Config
);
````


## -parameters

### -param Device [in]

A handle to the framework device object that the client driver retrieved in the previous call to <a href="wdf.wdfdevicecreate">WdfDeviceCreate</a>.

### -param Config [in]

 A pointer to a <a href="buses.urs_config">URS_CONFIG</a> structure that the client driver initialized by calling <a href="buses.urs_config_init">URS_CONFIG_INIT</a>.

## -returns
The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 

## -remarks
The client driver for the USB dual-role controller must call this method after the <a href="wdf.wdfdevicecreate">WdfDeviceCreate</a> call. 

The client driver calls this method in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> implementation.

During this call, the client driver-supplied event callback implementations are also registered by setting appropriate members of <a href="buses.urs_config">URS_CONFIG</a>. 

The method creates resource lists for host and function roles and the queues required to handle IOCTL requests that are sent to the controller. With each role switch operation, the current role's child device stack  is torn down and the device stack for the new role is loaded. The  <b>UrsDeviceInitialize</b> method retrieves identifying information that is used to build those device stacks. The method also retrieves information about the device from the underlying bus, such as ACPI.

## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
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
Minimum KMDF version
</th>
<td width="70%">
1.15
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ursdevice.h (include Urscx.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Urscxstub.lib</dt>
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
<dt>
<a href="buses.urs_config">URS_CONFIG</a>
</dt>
<dt>
<a href="buses.urs_config_init">URS_CONFIG_INIT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UrsDeviceInitialize function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
