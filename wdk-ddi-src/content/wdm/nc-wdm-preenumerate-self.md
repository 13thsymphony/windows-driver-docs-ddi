---
UID: NC.wdm.PREENUMERATE_SELF
title: PREENUMERATE_SELF
author: windows-driver-content
description: A ReenumerateSelf routine requests that a bus driver reenumerate a child device.
old-location: kernel\reenumerateself.htm
old-project: kernel
ms.assetid: ee669f35-87a5-4c5e-9936-b9135a1459e1
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ReenumerateSelf
req.alt-loc: wdm.h
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
req.iface: 
req.product: Windows 10 or later.
---

# PREENUMERATE_SELF callback



## -description
<p>A <i>ReenumerateSelf</i> routine requests that a bus driver reenumerate a child device.</p>


## -prototype

````
PREENUMERATE_SELF ReenumerateSelf;

VOID ReenumerateSelf(
  _In_ PVOID Context
)
{ ... }
````


## -parameters
<dl>

### -param Context [in]

<dd>
<p>A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="..\wdm\ns-wdm--reenumerate-self-interface-standard.md">REENUMERATE_SELF_INTERFACE_STANDARD</a> structure.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The <a href="..\wdm\ns-wdm--reenumerate-self-interface-standard.md">REENUMERATE_SELF_INTERFACE_STANDARD</a> interface structure supplies a pointer to the <i>ReenumerateSelf</i> routine.</p>

<p>If the bus driver can process the request at the time of the routine call, the bus driver asynchronously reports the device as missing in a subsequent <a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a> BusRelations query. This report causes the current device instance to receive <a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> requests. After the surprise removal has been processed, a new instance of the device is enumerated and the driver's <a href="kernel.adddevice">AddDevice</a> routine is called to rebuild the device stack.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h or Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--reenumerate-self-interface-standard.md">REENUMERATE_SELF_INTERFACE_STANDARD</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ReenumerateSelf routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
