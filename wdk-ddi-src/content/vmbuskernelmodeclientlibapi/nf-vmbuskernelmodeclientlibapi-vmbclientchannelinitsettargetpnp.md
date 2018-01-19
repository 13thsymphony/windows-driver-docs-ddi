---
UID : NF:vmbuskernelmodeclientlibapi.VmbClientChannelInitSetTargetPnp
title : VmbClientChannelInitSetTargetPnp function
author : windows-driver-content
description : The VmbClientChannelInitSetTargetPnp function sets a client channel's target by interface type and instance IDs.
old-location : netvista\vmbclientchannelinitsettargetpnp.htm
old-project : netvista
ms.assetid : 5525FD48-BE65-48CA-B3D5-C96AFD4ECF56
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : VmbClientChannelInitSetTargetPnp
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : vmbuskernelmodeclientlibapi.h
req.include-header : VmbusKernelModeClientLibApi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 1.13
req.umdf-ver : 2.0
req.alt-api : VmbClientChannelInitSetTargetPnp
req.alt-loc : vmbkmcl.lib,vmbkmcl.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Vmbkmcl.lib
req.dll : 
req.irql : 
req.typenames : "*PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES"
req.product : Windows 10 or later.
---


# VmbClientChannelInitSetTargetPnp function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbClientChannelInitSetTargetPnp</b> function sets a client channel's target by interface type and instance IDs. If this
function is called, Kernel Mode Client Library (KMCL) uses PnP to find the VMBus Physical Device Object (PDO) that corresponds to the
provided interface.

## Syntax

````
NTSTATUS VmbClientChannelInitSetTargetPnp(
  _In_     VMBCHANNEL                  Channel,
  _In_     LPCGUID                     InterfaceType,
  _In_opt_ LPCGUID                     InterfaceInstance,
  _In_opt_ PFN_VMB_CHANNEL_PNP_FAILURE PnpFailureCallback
);
````

## Parameters

`Channel`

A pointer to a channel.

`InterfaceType`

A pointer to the interface type GUID.
This GUID identifies the 
type of channel and the protocol that is used with the channel.

`InterfaceInstance`

A pointer to the instance type GUID. This is a 
specific instance of the service. If not
provided, any instance with the provided type is accepted.

`PnpFailureCallback`

A pointer to an event callback to call if the
device asynchronously fails to connect even though the PnP device was
located.


## Return Value

<b>VmbClientChannelInitSetTargetPnp</b> returns the following values: 
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.

## Remarks

If you 
have two paravirtual network interfaces, they will have the 
same <i>InterfaceType</i> but different <i>InterfaceInstance</i> values. </p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |