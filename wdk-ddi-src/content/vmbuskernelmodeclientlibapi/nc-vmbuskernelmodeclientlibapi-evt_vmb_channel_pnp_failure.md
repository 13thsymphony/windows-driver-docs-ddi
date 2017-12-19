---
UID: NC.vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_PNP_FAILURE
title: EVT_VMB_CHANNEL_PNP_FAILURE
author: windows-driver-content
description: The EvtChannelPnpFailure callback function is invoked if the client endpoint in the guest virtual machine asynchronously fails to connect even though a PnP device was located.
old-location: netvista\evt_vmb_channel_pnp_failure.htm
old-project: NetVista
ms.assetid: 3331C043-CFB2-434C-8475-2F5F094F2460
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _VIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES, PVIDEO_PORT_AGP_SERVICES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFN_VMB_CHANNEL_PNP_FAILURE
req.alt-loc: VmbusKernelModeClientLibApi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# EVT_VMB_CHANNEL_PNP_FAILURE callback



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtChannelPnpFailure</i> callback function is invoked if the client endpoint in the
guest virtual machine asynchronously fails to connect even though a
PnP device was located.



## -prototype

````
EVT_VMB_CHANNEL_PNP_FAILURE EvtChannelPnpFailure;

VOID EvtChannelPnpFailure(
  _In_ VMBCHANNEL Channel,
  _In_ NTSTATUS   FailureStatus
)
{ ... }

typedef EVT_VMB_CHANNEL_PNP_FAILURE PFN_VMB_CHANNEL_PNP_FAILURE;
````


## -parameters

### -param Channel [in]

The channel of the client endpoint.


### -param FailureStatus [in]

A failure code.


## -returns
This callback function does not return a value.


## -remarks
The <a href="netvista.vmbclientchannelinitsettargetpnp">VmbClientChannelInitSetTargetPnp</a> function registers <i>EvtChannelPnpFailure</i> code to run in the event  of this kind of failure. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>VmbusKernelModeClientLibApi.h (include VmbusKernelModeClientLibApi.h)</dt>
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
<a href="netvista.vmbclientchannelinitsettargetpnp">VmbClientChannelInitSetTargetPnp</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20EVT_VMB_CHANNEL_PNP_FAILURE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

