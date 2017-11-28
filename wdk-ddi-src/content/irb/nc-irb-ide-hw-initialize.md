---
UID: NC.irb.IDE_HW_INITIALIZE
title: IDE_HW_INITIALIZE
author: windows-driver-content
description: The IdeHwInitialize miniport driver routine configures the indicated device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\idehwinitialize.htm
old-project: storage
ms.assetid: 5665ff0a-3cbf-4ac5-adf7-5b383bac5117
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
req.alt-api: IdeHwInitialize
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
req.iface: 
---

# IDE_HW_INITIALIZE callback



## -description
<p>The <b><i>IdeHwInitialize</i></b> miniport driver routine configures the indicated device.</p>


## -prototype

````
IDE_HW_INITIALIZE IdeHwInitialize;

BOOLEAN IdeHwInitialize(
  _In_    PVOID                  ChannelExtension,
  _Inout_ PIDE_DEVICE_PARAMETERS DeviceParameters,
  _In_    PIDENTIFY_DEVICE_DATA  IdentifyData
)
{ ... }
````


## -parameters
<dl>

### -param <i>ChannelExtension</i> [in]

<dd>
<p>A pointer to the miniport driver per channel device extension.</p>
</dd>

### -param <i>DeviceParameters</i> [in, out]

<dd>
<p>A pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff559090">IDE_DEVICE_PARAMETERS</a> that identifies the device to configure and the device parameters with which to configure the device.</p>
</dd>

### -param <i>IdentifyData</i> [in]

<dd>
<p>A pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff559006">IDENTIFY_DEVICE_DATA</a> that contains the identify data that is returned by the device.</p>
</dd>
</dl>

## -returns
<p><b><i>IdeHwInitialize</i></b> returns <b>TRUE</b> if the operation succeeds. It returns <b>FALSE</b> if the operation fails. </p>

## -remarks
<p>After the miniport driver enumerates the devices on a channel, it calls the <b><i>IdeHwInitialize</i></b> routine one time for each device it enumerates. The <b><i>IdeHwInitialize</i></b> routine must configure each device based on the information that is specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559090">IDE_DEVICE_PARAMETERS</a> structure, pointed to by the <i>DeviceParameters</i> parameter. In exceptional cases, the miniport driver can configure the device by using a set of parameters that differ from those contained in <b>IDE_DEVICE_PARAMETERS</b>. In such cases, the miniport driver must update the information in <b>IDE_DEVICE_PARAMETERS</b> to contain the parameter value that it actually used to configure the device. After the <b><i>IdeHwInitialize</i></b> routine returns, the port driver updates its cached information with the parameter values that are provided by the miniport driver.</p>

<p>After the miniport driver enumerates the devices on a channel, it calls the <b><i>IdeHwInitialize</i></b> routine one time for each device it enumerates. The <b><i>IdeHwInitialize</i></b> routine must configure each device based on the information that is specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559090">IDE_DEVICE_PARAMETERS</a> structure, pointed to by the <i>DeviceParameters</i> parameter. In exceptional cases, the miniport driver can configure the device by using a set of parameters that differ from those contained in <b>IDE_DEVICE_PARAMETERS</b>. In such cases, the miniport driver must update the information in <b>IDE_DEVICE_PARAMETERS</b> to contain the parameter value that it actually used to configure the device. After the <b><i>IdeHwInitialize</i></b> routine returns, the port driver updates its cached information with the parameter values that are provided by the miniport driver.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559090">IDE_DEVICE_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559006">IDENTIFY_DEVICE_DATA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IdeHwInitialize routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
