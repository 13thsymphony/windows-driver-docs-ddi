---
UID: NF.ucmtcpciportcontroller.UcmTcpciPortControllerCreate
title: UcmTcpciPortControllerCreate function
author: windows-driver-content
description: Creates a port controller object to register with UcmTcpciCx.
old-location: buses\ucmtcpciportcontrollercreate.htm
old-project: usbref
ms.assetid: 29862d9b-c004-445b-b90b-6990e5e01966
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UcmTcpciPortControllerCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmtcpciportcontroller.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UcmTcpciPortControllerCreate
req.alt-loc: ucmtcpcicxstub.lib,ucmtcpcicxstub.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ucmtcpcicxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# UcmTcpciPortControllerCreate function



## -description
Creates a port controller object to register with UcmTcpciCx. 


## -syntax

````
NTSTATUS UcmTcpciPortControllerCreate(
   WDFDEVICE                        WdfDevice,
   PUCMTCPCI_PORT_CONTROLLER_CONFIG Config,
   PWDF_OBJECT_ATTRIBUTES           Attributes,
   UCMTCPCIPORTCONTROLLER*          PortControllerObject
);
````


## -parameters

### -param WdfDevice 

A handle to a framework device object that the client driver received in the previous call to <a href="wdf.wdfdevicecreate">WdfDeviceCreate</a>. 

### -param Config 

A pointer to the <a href="buses.ucmtcpci_port_controller_config">UCMTCPCI_PORT_CONTROLLER_CONFIG</a> that is initialized by calling <b>UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT</b>. This value cannot be NULL.

### -param Attributes 

A pointer to a <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new object. This parameter is optional and can be <b>WDF_NO_OBJECT_ATTRIBUTES</b>.

### -param PortControllerObject 

A pointer to a location that receives a handle to the new port controller object. 

## -returns

(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The handle to a framework device object is invalid.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>Invalid size for the structure pointed to by <i>Config</i> or <i> Config-&gt;Capabilities</i>. Must be size of <a href="buses.ucmtcpci_port_controller_config">UCMTCPCI_PORT_CONTROLLER_CONFIG</a> or <a href="buses.ucmtcpci_port_controller_capabilities">UCMTCPCI_PORT_CONTROLLER_CAPABILITIES</a>, respectively. 

 

## -remarks


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
Header
</th>
<td width="70%">
<dl>
<dt>Ucmtcpciportcontroller.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ucmtcpcicxstub.lib</dt>
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
<dt>
<a href="buses.ucmtcpci_port_controller_config">UCMTCPCI_PORT_CONTROLLER_CONFIG</a>
</dt>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EVT_WDF_DRIVER_DEVICE_ADD</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcmTcpciPortControllerCreate method%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
