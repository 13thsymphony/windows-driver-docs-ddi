---
UID: NC:pepfx.PEPCALLBACKNOTIFYPPM
title: PEPCALLBACKNOTIFYPPM
author: windows-driver-content
description: An AcceptProcessorNotification event callback routine handles processor power management (PPM) notifications from the Windows power management framework (PoFx).
old-location: kernel\acceptprocessornotification.htm
old-project: kernel
ms.assetid: 06A8ED06-107E-495F-8664-01477C9CF843
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: AcceptProcessorNotification, AcceptProcessorNotification routine [Kernel-Mode Driver Architecture], PEPCALLBACKNOTIFYPPM, kernel.acceptprocessornotification, pepfx/AcceptProcessorNotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	pepfx.h
api_name:
-	AcceptProcessorNotification
product: Windows
targetos: Windows
req.typenames: VPCI_PNP_ID, *PVPCI_PNP_ID
---


# PEPCALLBACKNOTIFYPPM callback function
An <i>AcceptProcessorNotification</i> event callback routine handles processor power management (PPM) notifications from the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).

## Syntax

```
PEPCALLBACKNOTIFYPPM Pepcallbacknotifyppm;

BOOLEAN Pepcallbacknotifyppm(
  PEPHANDLE Handle,
  ULONG Notification,
  PVOID Data
)
{...}
```

## Parameters

`Handle`

The device handle for the PEP for the target processor. If <b>NULL</b>,  the notification does not target a specific processor.

`Notification`

The PPM notification ID. This parameter specifies the type of PPM notification that PoFx is sending. For a list of PPM notification IDs, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt186881">Processor power management (PPM) notifications</a>.

`Data`

A pointer to a PoFx-allocated structure that contains the input and/or output data for this notification. The type of this structure depends on the notification ID specified by <i>Notification</i>. For a list of the structure types that are defined for the various PPM notification IDs, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt186881">Processor power management (PPM) notifications</a>.


## Return Value

The <i>AcceptProcessorNotification</i> routine must return TRUE if it handles the notification, or FALSE if it does not.

## Remarks

This routine is implemented by the platform extension plug-in (PEP) for a processor. The <b>AcceptProcessorNotification</b> member of the <a href="..\pepfx\ns-pepfx-_pep_information.md">PEP_INFORMATION</a> structure is a pointer to an <i>AcceptProcessorNotification</i> routine. The PEP calls the <a href="..\pepfx\nf-pepfx-pofxregisterplugin.md">PoFxRegisterPlugin</a> or <a href="..\pepfx\nf-pepfx-pofxregisterpluginex.md">PoFxRegisterPluginEx</a> routine to register the PEP's <i>AcceptProcessorNotification</i> routine with PoFx.

The IRQL at which the PEP's <i>AcceptProcessorNotification</i> routine is called varies according to the type of notification that is being sent. The context in which this interface is called ranges from PASSIVE_LEVEL to HIGH_LEVEL with interrupts disabled. For more information about the IRQL at which each notification type is sent, see the individual reference pages under <a href="https://msdn.microsoft.com/library/windows/hardware/mt186881">Processor power management (PPM) notifications</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10.  |
| **Target Platform** | Windows |
| **Header** | pepfx.h (include Pep_x.h) |
| **IRQL** | PASSIVE_LEVEL to HIGH_LEVEL |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_information.md">PEP_INFORMATION</a>



<a href="..\pepfx\nf-pepfx-pofxregisterplugin.md">PoFxRegisterPlugin</a>



<a href="..\pepfx\nf-pepfx-pofxregisterpluginex.md">PoFxRegisterPluginEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20AcceptProcessorNotification routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>