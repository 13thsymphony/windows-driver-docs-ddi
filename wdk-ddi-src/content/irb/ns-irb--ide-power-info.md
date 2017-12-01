---
UID: NS.irb._IDE_POWER_INFO
title: IDE_POWER_INFO
author: windows-driver-content
description: The POWER_CHANGE_INFO structure is used in conjunction with the IDE_REQUEST_BLOCK to request a power state change.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\power_change_info.htm
old-project: storage
ms.assetid: 10f6c449-f0f8-4261-825e-127c477c06eb
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: IDE_POWER_INFO, IDE_POWER_INFO, *PIDE_POWER_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: irb.h
req.include-header: Irb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDE_POWER_INFO
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

# IDE_POWER_INFO structure



## -description
<p>The POWER_CHANGE_INFO structure is used in conjunction with the <a href="..\irb\ns-irb--ide-request-block.md">IDE_REQUEST_BLOCK</a> to request a power state change.</p>


## -syntax

````
typedef struct _IDE_POWER_INFO {
  IDE_POWER_STATE CurrentPowerState;
  IDE_POWER_STATE DesiredPowerState;
} IDE_POWER_INFO, *PIDE_POWER_INFO;
````


## -struct-fields
<dl>

### -field <b>CurrentPowerState</b>

<dd>
<p>Contains an enumeration value of type <a href="..\irb\ne-irb-ide-power-state.md">IDE_POWER_STATE</a> that indicates the current power state of the device.</p>
</dd>

### -field <b>DesiredPowerState</b>

<dd>
<p>Contains an enumeration value of type IDE_POWER_STATE that indicates the power state to which the device will be changed.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
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
<a href="..\irb\ns-irb--ide-request-block.md">IDE_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="..\irb\ne-irb-ide-power-state.md">IDE_POWER_STATE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20POWER_CHANGE_INFO structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
