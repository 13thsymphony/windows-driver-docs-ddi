---
UID: NC.irb.IDE_CHANNEL_ENABLED
title: IDE_CHANNEL_ENABLED
author: windows-driver-content
description: The AtaControllerChannelEnabled miniport driver routine indicates whether the specified channel is enabled.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\atacontrollerchannelenabled.htm
old-project: storage
ms.assetid: 67713537-6a5b-4108-8af9-fb5d16844b03
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: WdmlibIoGetAffinityInterrupt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: irb.h
req.include-header: Irb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AtaControllerChannelEnabled
req.alt-loc: irb.h
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
---

# IDE_CHANNEL_ENABLED callback



## -description
The <b><i>AtaControllerChannelEnabled</i></b> miniport driver routine indicates whether the specified channel is enabled.


## -prototype

````
IDE_CHANNEL_ENABLED AtaControllerChannelEnabled;

ATA_CHANNEL_STATE AtaControllerChannelEnabled(
  _In_ PVOID ControllerExtension,
  _In_ ULONG ChannelNumber
)
{ ... }
````


## -parameters

### -param ControllerExtension [in]

A pointer to the controller extension.

### -param ChannelNumber [in]

Specifies the channel number whose state will be determined. 

## -returns
<b><i>AtaControllerChannelEnabled</i></b> returns an enumerator value of type <a href="..\irb\ne-irb-ata_channel_state.md">ATA_CHANNEL_STATE</a>, which can have any of the following values:
<dl>
<dt><b>ChannelStateEnabled</b></dt>
</dl>Indicates that the specified channel is enabled. 
<dl>
<dt><b>ChannelStateDisabled</b></dt>
</dl>Indicates that the specified channel is disabled.
<dl>
<dt><b>ChannelStateUnKnown</b></dt>
</dl>Indicates that the state of the channel could not be determined.

 

## -remarks
The following sequence describes how the miniport driver and the port driver interact to determine which controller channels are enabled:

The port driver calls the miniport driver's <b><i>AtaAdapterControl</i></b> routine with control action <b>IdeStart</b>. 

While the miniport driver processes the <b><i>AtaAdapterControl</i></b> routine with control action <b>IdeStart</b>, it initializes the <b>NumberOfChannels</b> member of <a href="storage.ide_controller_configuration">IDE_CONTROLLER_CONFIGURATION</a> to indicate the number of channels that are enabled. 

After the <b><i>AtaAdapterControl</i></b> routine returns, the port driver calls <b>AtaControllerChannelEnabled</b> one time for every NumberOfChannels specified in the ControllerConfiguration structure that are returned by <b><i>AtaAdapterControl</i></b>.

This routine should not have steps that are critical to the operation of the controller. There are situations, such as during a crashdump operation, where this function will not be called at all.  Additionally, this function is not called when a channel is restarted, only when PCIIDEx responds to a QueryDeviceRelations IRP.

<b>AtaControllerChannelEnabled</b> is an optional routine. If the miniport driver does not implement this routine, the port driver will load a default handler. If the port driver loads a default handler, all channels that are specified by NumberOfChannels in the ControllerConfiguration structure that is returned by <a href="storage.ataadaptercontrol">AtaAdapterControl</a> when handling an IdeStart action are assumed to be enabled. This routine enables PCIIDEx to load the ATA port driver for only the channels enabled. Doing this allows for sparse channel support (for example, channel 0, channel 1, channel 3, channel 4, and channel 6, but not channel 2 and channel 5).

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Irb.h (include Irb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.ide_controller_configuration">IDE_CONTROLLER_CONFIGURATION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaControllerChannelEnabled routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
