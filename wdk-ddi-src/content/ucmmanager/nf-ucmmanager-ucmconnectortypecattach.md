---
UID: NF.ucmmanager.UcmConnectorTypeCAttach
title: UcmConnectorTypeCAttach function
author: windows-driver-content
description: Notifies the USB connector manager framework extension (UcmCx) when a partner connector is attached.
old-location: buses\ucmconnectortypecattach.htm
old-project: usbref
ms.assetid: D778E6B6-B245-41D5-B25B-1CF183146BA9
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UcmConnectorTypeCAttach
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.alt-api: UcmConnectorTypeCAttach
req.alt-loc: UcmCxstub.lib,UcmCxstub.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: UcmCxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# UcmConnectorTypeCAttach function



## -description
Notifies the USB connector manager framework extension (UcmCx) when a partner connector is attached.



## -syntax

````
NTSTATUS UcmConnectorTypeCAttach(
  [in] UCMCONNECTOR                        Connector,
  [in] PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS  Params
);
````


## -parameters

### -param  Connector [in]

Handle to the connector object that the client driver received in the previous call to <a href="buses.ucmconnectorcreate">UcmConnectorCreate</a>.


### -param  Params [in]

A pointer to a driver-allocated <a href="buses.ucm_connector_typec_attach_params">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</a> that has been initialized by  calling <a href="buses.ucm_connector_typec_attach_params_init">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT</a>.


## -returns
<b>UcmConnectorTypeCAttach</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value. 


## -remarks
When a connection to a partner connector is detected, the client driver calls this method to notify UcmCx with information about the partner connector. That information includes the connector role, down stream or upstream facing port, the amount of current connector can draw or deliver, and charging state. UcmCx uses that information to perform certain operations. For example, it may determine the role of the partner connector attached, and configure the USB controller in host or peripheral mode.


Typically, every  <b>UcmConnectorTypeCAttach</b> call has a subsequent <a href="buses.ucmconnectortypecdetach">UcmConnectorTypeCDetach</a> call to notify UcmCx when the partner connector is detached. However, when a powered cable without an upstream port is attached (indicated by <b>Params-&gt;PortPartnerType</b> set to <b>UcmTypeCPortStatePoweredCableNoUfp</b>). The client driver can call <b>UcmConnectorTypeCAttach</b> again when a connection is detected to the  upstream port to the powered cable.


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
Minimum UMDF version

</th>
<td width="70%">
2.15

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ucmmanager.h (include Ucmcx.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>UcmCxstub.lib</dt>
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
<a href="buses.ucmconnectorcreate">UcmConnectorCreate</a>
</dt>
<dt>
<a href="buses.ucm_connector_typec_attach_params">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</a>
</dt>
<dt>
<a href="buses.ucm_connector_typec_attach_params_init">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcmConnectorTypeCAttach method%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

