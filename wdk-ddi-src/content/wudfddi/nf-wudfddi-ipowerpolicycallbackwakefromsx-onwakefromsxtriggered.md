---
UID: NF:wudfddi.IPowerPolicyCallbackWakeFromSx.OnWakeFromSxTriggered
title: IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered method
author: windows-driver-content
description: A driver's OnWakeFromSxTriggered event callback function informs the driver that its device, which had previously entered a low-power device state because system power was reduced, might have triggered a wake signal.
old-location: wdf\ipowerpolicycallbackwakefromsx_onwakefromsxtriggered.htm
old-project: wdf
ms.assetid: b2379f2d-61a0-4741-a375-c17b95b0faf6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IPowerPolicyCallbackWakeFromSx, IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered, OnWakeFromSxTriggered
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IPowerPolicyCallbackWakeFromSx.OnWakeFromSxTriggered
req.alt-loc: Wudfddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnWakeFromSxTriggered</b> event callback function informs the driver that its device, which had previously entered a low-power device state because system power was reduced, might have triggered a wake signal.



## -syntax

````
void OnWakeFromSxTriggered(
  [in] IWDFDevice *pWdfDevice
);
````


## -parameters

### -param pWdfDevice [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface of the device object that represents one of the driver's devices.


## -returns
None.


## -remarks
Your driver must provide an <b>OnWakeFromSxTriggered</b> callback function if the driver supports the <a href="..\wudfddi\nn-wudfddi-ipowerpolicycallbackwakefromsx.md">IPowerPolicyCallbackWakeFromSx</a> interface. 

If the driver has registered this callback, the framework calls it after calling the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556799">IPnpCallback::OnD0Entry</a> callback function and before calling the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556828">IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx</a> callback function.

System hardware (BIOSes, motherboards, bus adapters) can sometimes drop a wake signal before the bus driver detects it, even though the signal wakes up the system. In such cases, the driver's <b>OnWakeFromSxTriggered</b> callback function will not be called even though the driver's device triggered a wake signal.

For more information about this callback function, see <a href="wdf.supporting_system_wake_up_in_umdf_drivers">Supporting System Wake-Up in UMDF-based Drivers</a>.


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
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.9

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-ipowerpolicycallbackwakefromsx.md">IPowerPolicyCallbackWakeFromSx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556826">IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556828">IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

