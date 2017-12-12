---
UID: NF.ursdevice.UrsDeviceInitInitialize
title: UrsDeviceInitInitialize function
author: windows-driver-content
description: Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
old-location: buses\ursdeviceinitinitialize.htm
old-project: usbref
ms.assetid: EFA83238-77DF-474D-8F8F-2400C9B23A00
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UrsDeviceInitInitialize
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
req.alt-api: UrsDeviceInitInitialize
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

# UrsDeviceInitInitialize function



## -description
Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.



## -syntax

````
FORCEINLINE NTSTATUS UrsDeviceInitInitialize(
   PWDFDEVICE_INIT DeviceInit
);
````


## -parameters

### -param DeviceInit 

A pointer to a framework-allocated <a href="wdf.wdfdevice_init">WDFDEVICE_INIT</a> structure. 


## -returns
The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 


## -remarks
The client driver for the dual-role controller calls this method in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> implementation before it calls <a href="wdf.wdfdevicecreate">WdfDeviceCreate</a> and <a href="buses.ursdeviceinitialize">UrsDeviceInitialize</a>. For code example, see <b>UrsDeviceInitialize</b>.


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
<a href="wdf.wdfdevicecreate">WdfDeviceCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UrsDeviceInitInitialize method%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

