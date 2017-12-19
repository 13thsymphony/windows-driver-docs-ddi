---
UID: NF.ucmmanager.UcmConnectorDataDirectionChanged
title: UcmConnectorDataDirectionChanged function
author: windows-driver-content
description: Notifies the USB connector manager framework extension (UcmCx) with the new data role of a change in data role.
old-location: buses\ucmconnectordatadirectionchanged.htm
old-project: UsbRef
ms.assetid: 62ED07DF-2DDC-42FD-80C3-75AB3DE839AD
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: UcmConnectorDataDirectionChanged
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
req.alt-api: UcmConnectorDataDirectionChanged
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

# UcmConnectorDataDirectionChanged function



## -description
Notifies the USB connector manager framework extension (UcmCx) with the new data role  of a change in data role.



## -syntax

````
NTSTATUS UcmConnectorDataDirectionChanged(
  [in] UCMCONNECTOR       Connector,
  [in] BOOLEAN            Success,
  [in] UCM_TYPEC_PARTNER  CurrentDataRole
);
````


## -parameters

### -param  Connector [in]

Handle to the connector object that the client driver received in the previous call to <a href="buses.ucmconnectorcreate">UcmConnectorCreate</a>.


### -param  Success [in]

Used to indicate failure of a data-role swap that was initiated by UcmCx using <a href="..\ucmmanager\nc-ucmmanager-evt_ucm_connector_set_data_role.md">EVT_UCM_CONNECTOR_SET_DATA_ROLE</a>. 

If TRUE, the operation was successful. FALSE, otherwise.


### -param  CurrentDataRole [in]

A <a href="buses.ucm_type_c_port_state">UCM_TYPEC_PARTNER</a> value that indicates the new data role. 


## -returns
<b>UcmConnectorDataDirectionChanged</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value. 


## -remarks
If the connector partner is attached, UcmCx updates the data role of the partner depending on the <i>CurrentDataRole</i> value. For example, if the client driver changes the data role to <b>UcmTypeCPortStateUfp</b>, UcmCx updates the role of the connector partner to <b>UcmTypeCPortStateDfp</b>.

UcmCx can change the data role of a connector, and invokes <a href="..\ucmmanager\nc-ucmmanager-evt_ucm_connector_set_data_role.md">EVT_UCM_CONNECTOR_SET_DATA_ROLE</a>. In response to that call, the client should perform the DR_Swap operation, and indicate success/failure of the operation by calling  <b>UcmConnectorDataDirectionChanged</b>.

Alternatively, the client driver might choose to perform a role-swap autonomously, or the partner might perform a role-swap. In either case, when the role-swap has completed, the driver must report the new role to UcmCx using <b>UcmConnectorDataDirectionChanged</b>.



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
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UcmConnectorDataDirectionChanged method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

