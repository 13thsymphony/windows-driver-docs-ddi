---
UID: NC.pepfx.PEPCALLBACKNOTIFYDPM
title: PEPCALLBACKNOTIFYDPM
author: windows-driver-content
description: An AcceptDeviceNotification event callback routine handles device power management (DPM) notifications from the Windows power management framework (PoFx).
old-location: kernel\acceptdevicenotification.htm
old-project: kernel
ms.assetid: 56446DA9-EAE9-4EEF-9299-892B7384D506
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _VPCI_PNP_ID, PVPCI_PNP_ID, *PVPCI_PNP_ID, VPCI_PNP_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AcceptDeviceNotification
req.alt-loc: pepfx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# PEPCALLBACKNOTIFYDPM callback



## -description
An <i>AcceptDeviceNotification</i> event callback routine handles device power management (DPM) notifications from the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx).



## -prototype

````
PEPCALLBACKNOTIFYDPM AcceptDeviceNotification;

BOOLEAN AcceptDeviceNotification(
  _In_        ULONG Notification,
  _Inout_opt_ PVOID Data
)
{ ... }
````


## -parameters

### -param Notification [in]

The DPM notification ID. This parameter specifies the type of DPM notification that PoFx is sending. For a list of DPM notification IDs, see <a href="kernel.device_power_management__dpm__notifications">Device power management (DPM) notifications</a>.


### -param Data [in, out, optional]

A pointer to a PoFx-allocated structure that contains the input and/or output data for this notification. The type of this structure depends on the notification ID specified by <i>Notification</i>. For a list of the structure types that are defined for the various DPM notification IDs, see <a href="kernel.device_power_management__dpm__notifications">Device power management (DPM) notifications</a>.


## -returns
The <i>AcceptDeviceNotification</i> routine must return TRUE if it handles the notification, or FALSE if it does not.


## -remarks
This routine is implemented by the platform extension plug-in (PEP) for a device. The <b>AcceptDeviceNotification</b> member of the <a href="kernel.pep_information">PEP_INFORMATION</a> structure is a pointer to an <i>AcceptDeviceNotification</i> routine. The PEP calls the <a href="kernel.pofxregisterplugin">PoFxRegisterPlugin</a> or <a href="kernel.pofxregisterpluginex">PoFxRegisterPluginEx</a> routine to register the PEP's <i>AcceptDeviceNotification</i> routine with PoFx.

PoFx calls this routine to send a DPM notification to the PEP. In this call, the <i>Notification</i> parameter specifies the type of notification, and the <i>Data</i> parameter points to a data structure of the type that is associated with this notification. For a list of DPM notification IDs and their associated structure types, see <a href="kernel.device_power_management__dpm__notifications">Device power management (DPM) notifications</a>.

DPM notifications inform the PEP about various system, device, or componentÂ–-level events, or pass requests from the device driver to the PEP.

The <i>AcceptDeviceNotification</i> routine does not have to accept every request from the  device driver—for example, it can ignore idle residency hints. However, the PEP must understand and accept most device power management notifications even if the PEP chooses not to act on them. The PEP must refuse to handle (by returning FALSE) every notification that it does not recognize.

The <i>AcceptDeviceNotification</i> routine can be called at IRQL &lt;= DISPATCH_LEVEL. The IRQL at which the PEP's <i>AcceptAcpiNotification</i> routine is called varies according to the type of notification that is being sent. The notification type is specified by the <i>Notification</i> parameter. For more information, see the individual reference pages under <a href="kernel.device_power_management__dpm__notifications">Device power management (DPM) notifications</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows 10.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.pep_information">PEP_INFORMATION</a>
</dt>
<dt>
<a href="kernel.pofxregisterplugin">PoFxRegisterPlugin</a>
</dt>
<dt>
<a href="kernel.pofxregisterpluginex">PoFxRegisterPluginEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20AcceptDeviceNotification routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

