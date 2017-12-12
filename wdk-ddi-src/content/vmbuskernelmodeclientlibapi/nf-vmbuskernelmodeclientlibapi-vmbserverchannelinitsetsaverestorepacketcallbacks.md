---
UID: NF.vmbuskernelmodeclientlibapi.VmbServerChannelInitSetSaveRestorePacketCallbacks
title: VmbServerChannelInitSetSaveRestorePacketCallbacks function
author: windows-driver-content
description: The VmbServerChannelInitSetSaveRestorePacketCallbacks function sets the save and restore callback functions that are called for each packet when the driver calls a save function, such as VmbChannelSaveBegin, VmbChannelSaveContinue, and VmbChannelSaveEnd, or the VmbChannelRestoreFromBuffer function.
old-location: netvista\vmbserverchannelinitsetsaverestorepacketcallbacks.htm
old-project: netvista
ms.assetid: 2E704BF1-21E2-498E-82C2-2B55BF44D044
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: VmbServerChannelInitSetSaveRestorePacketCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.alt-api: VmbServerChannelInitSetSaveRestorePacketCallbacks
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
req.irql: 
req.product: Windows 10 or later.
---

# VmbServerChannelInitSetSaveRestorePacketCallbacks function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbServerChannelInitSetSaveRestorePacketCallbacks</b> function sets the save and restore callback functions that are called for each packet when the
driver calls a save function, such as <a href="netvista.vmbchannelsavebegin">VmbChannelSaveBegin</a>, <a href="netvista.vmbchannelsavecontinue">VmbChannelSaveContinue</a>, and <a href="netvista.vmbchannelsaveend">VmbChannelSaveEnd</a>, or the <a href="netvista.vmbchannelrestorefrombuffer">VmbChannelRestoreFromBuffer</a> function.



## -syntax

````
NTSTATUS
 VmbServerChannelInitSetSaveRestorePacketCallbacks(
  _In_ VMBCHANNEL                     Channel,
  _In_ PFN_VMB_CHANNEL_SAVE_PACKET    SavePacketCallback,
  _In_ PFN_VMB_CHANNEL_RESTORE_PACKET RestorePacketCallback
);
````


## -parameters

### -param Channel [in]

 A handle for a channel.  


### -param SavePacketCallback [in]

A callback function to call during channel
save. 


### -param RestorePacketCallback [in]

A callback function to call during channel     restore.


## -returns
<b>VmbServerChannelInitSetSaveRestorePacketCallbacks</b> returns the following status values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.13

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
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
</table>

## -see-also
<dl>
<dt>
<a href="netvista.vmbchannelrestorefrombuffer">VmbChannelRestoreFromBuffer</a>
</dt>
<dt>
<a href="netvista.vmbchannelsavebegin">VmbChannelSaveBegin</a>
</dt>
<dt>
<a href="netvista.vmbchannelsavecontinue">VmbChannelSaveContinue</a>
</dt>
<dt>
<a href="netvista.vmbchannelsaveend">VmbChannelSaveEnd</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbServerChannelInitSetSaveRestorePacketCallbacks function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

