---
UID: NC.pepfx.PEPCALLBACKNOTIFYPPM
title: PEPCALLBACKNOTIFYPPM
author: windows-driver-content
description: An AcceptProcessorNotification event callback routine handles processor power management (PPM) notifications from the Windows power management framework (PoFx).
old-location: kernel\acceptprocessornotification.htm
old-project: kernel
ms.assetid: 06A8ED06-107E-495F-8664-01477C9CF843
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _VPCI_PNP_ID, *PVPCI_PNP_ID, VPCI_PNP_ID
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
req.alt-api: AcceptProcessorNotification
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
req.irql: PASSIVE_LEVEL to HIGH_LEVEL
---

# PEPCALLBACKNOTIFYPPM callback



## -description
An <i>AcceptProcessorNotification</i> event callback routine handles processor power management (PPM) notifications from the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx).


## -prototype

````
PEPCALLBACKNOTIFYPPM AcceptProcessorNotification;

BOOLEAN AcceptProcessorNotification(
  _In_        PEPHANDLE Handle,
  _In_        ULONG     Notification,
  _Inout_opt_ PVOID     Data
)
{ ... }
````


## -parameters

### -param Handle [in]

The device handle for the PEP for the target processor. If <b>NULL</b>,  the notification does not target a specific processor.

### -param Notification [in]

The PPM notification ID. This parameter specifies the type of PPM notification that PoFx is sending. For a list of PPM notification IDs, see <a href="kernel.processor_power_management__ppm__notifications">Processor power management (PPM) notifications</a>.

### -param Data [in, out, optional]

A pointer to a PoFx-allocated structure that contains the input and/or output data for this notification. The type of this structure depends on the notification ID specified by <i>Notification</i>. For a list of the structure types that are defined for the various PPM notification IDs, see <a href="kernel.processor_power_management__ppm__notifications">Processor power management (PPM) notifications</a>.

## -returns
The <i>AcceptProcessorNotification</i> routine must return TRUE if it handles the notification, or FALSE if it does not.

## -remarks
This routine is implemented by the platform extension plug-in (PEP) for a processor. The <b>AcceptProcessorNotification</b> member of the <a href="kernel.pep_information">PEP_INFORMATION</a> structure is a pointer to an <i>AcceptProcessorNotification</i> routine. The PEP calls the <a href="kernel.pofxregisterplugin">PoFxRegisterPlugin</a> or <a href="kernel.pofxregisterpluginex">PoFxRegisterPluginEx</a> routine to register the PEP's <i>AcceptProcessorNotification</i> routine with PoFx.

The IRQL at which the PEP's <i>AcceptProcessorNotification</i> routine is called varies according to the type of notification that is being sent. The context in which this interface is called ranges from PASSIVE_LEVEL to HIGH_LEVEL with interrupts disabled. For more information about the IRQL at which each notification type is sent, see the individual reference pages under <a href="kernel.processor_power_management__ppm__notifications">Processor power management (PPM) notifications</a>.

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
PASSIVE_LEVEL to HIGH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.pofxregisterplugin">PoFxRegisterPlugin</a>
</dt>
<dt>
<a href="kernel.pofxregisterpluginex">PoFxRegisterPluginEx</a>
</dt>
<dt>
<a href="kernel.pep_information">PEP_INFORMATION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20AcceptProcessorNotification routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
