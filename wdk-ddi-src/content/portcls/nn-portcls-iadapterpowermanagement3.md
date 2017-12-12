---
UID: NN.portcls.IAdapterPowerManagement3
title: IAdapterPowerManagement3
author: windows-driver-content
description: The IAdapterPowerManagement3 interface inherits from IUnknown, and it is used for receiving power management messages.
old-location: audio\iadapterpowermanagement3.htm
old-project: audio
ms.assetid: 5F0729DB-C991-4745-9550-9D25D6836A1F
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PcUnregisterIoTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IAdapterPowerManagement3
req.alt-loc: Portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# IAdapterPowerManagement3 interface



## -description
The IAdapterPowerManagement3 interface inherits from <b>IUnknown</b>, and it is used for receiving power management messages.

To register this interface with PortCls, the adapter driver must call  <a href="audio.pcregisteradapterpowermanagement">PcRegisterAdapterPowerManagement</a>.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IAdapterPowerManagement3</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IAdapterPowerManagement3</b> also has these types of members:

The <b>IAdapterPowerManagement3</b> interface has these methods.

PortCls calls the D3ExitLatencyChanged method while the device is in sleep (D3) power state, to provide a new exit latency value.

PortCls calls the PowerChangeState3 method to request a change to the new power state. This request is passed on to the adapter driver.

 


## -members
The <b>IAdapterPowerManagement3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="audio.iadapterpowermanagement3_d3exitlatencychanged">D3ExitLatencyChanged</a>
</td>
<td align="left" width="63%">
PortCls calls the D3ExitLatencyChanged method while the device is in sleep (D3) power state, to provide a new exit latency value.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="audio.iadapterpowermanagement3_powerchangestate3">PowerChangeState3</a>
</td>
<td align="left" width="63%">
PortCls calls the PowerChangeState3 method to request a change to the new power state. This request is passed on to the adapter driver.

</td>
</tr>
</table>PortCls calls the D3ExitLatencyChanged method while the device is in sleep (D3) power state, to provide a new exit latency value.

PortCls calls the PowerChangeState3 method to request a change to the new power state. This request is passed on to the adapter driver.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iadapterpowermanagement2.md">IAdapterPowerManagement2</a>
</dt>
<dt>
<a href="audio.pcregisteradapterpowermanagement">PcRegisterAdapterPowerManagement</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IAdapterPowerManagement3 interface%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

