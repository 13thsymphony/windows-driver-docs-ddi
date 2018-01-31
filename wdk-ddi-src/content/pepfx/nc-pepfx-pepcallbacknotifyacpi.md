---
UID : NC:pepfx.PEPCALLBACKNOTIFYACPI
title : PEPCALLBACKNOTIFYACPI
author : windows-driver-content
description : An AcceptAcpiNotification event callback routine handles ACPI notifications from the Windows power management framework (PoFx).
old-location : kernel\acceptacpinotification.htm
old-project : kernel
ms.assetid : 7BC27FD1-CCD8-4ABC-B973-C2242D6C243B
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.acceptacpinotification, AcceptAcpiNotification routine [Kernel-Mode Driver Architecture], AcceptAcpiNotification, PEPCALLBACKNOTIFYACPI, PEPCALLBACKNOTIFYACPI, pepfx/AcceptAcpiNotification
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : pepfx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 10.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= HIGH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PVPCI_PNP_ID, VPCI_PNP_ID"
---


# PEPCALLBACKNOTIFYACPI function
An <i>AcceptAcpiNotification</i> event callback routine handles ACPI notifications from the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).

## Syntax

```
PEPCALLBACKNOTIFYACPI Pepcallbacknotifyacpi;

BOOLEAN Pepcallbacknotifyacpi(
  ULONG Notification,
  PVOID Data
)
{...}
```

## Parameters

`Notification`

The ACPI notification ID. This parameter specifies the type of ACPI notification that PoFx is sending. For a list of ACPI notification IDs, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt186628">ACPI notifications</a>.

`Data`

A pointer to a PoFx-allocated structure that contains the input and/or output data for this notification. The type of this structure depends on the notification ID specified by <i>Notification</i>. For a list of the structure types that are defined for the various ACPI notification IDs, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt186628">ACPI notifications</a>.


## Return Value

The <i>AcceptAcpiNotification</i> routine must return TRUE if it handles the notification, or FALSE if it does not.

## Remarks

This routine is implemented by the platform extension plug-in (PEP) for a device. The <b>AcceptAcpiNotification</b> member of the <a href="..\pepfx\ns-pepfx-_pep_information.md">PEP_INFORMATION</a> structure is a pointer to an <i>AcceptAcpiNotification</i> routine. The PEP calls the <a href="..\pepfx\nf-pepfx-pofxregisterplugin.md">PoFxRegisterPlugin</a> or <a href="..\pepfx\nf-pepfx-pofxregisterpluginex.md">PoFxRegisterPluginEx</a> routine to register the PEP's <i>AcceptAcpiNotification</i> routine with PoFx.

The IRQL at which the PEP's <i>AcceptAcpiNotification</i> routine is called varies according to the type of notification that is being sent. The notification type is specified by the <i>Notification</i> parameter. For more information about the IRQL at which each notification type is sent, see the individual reference pages under <a href="https://msdn.microsoft.com/library/windows/hardware/mt186628">ACPI notifications</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pepfx.h |
| **Library** |  |
| **IRQL** | "<= HIGH_LEVEL" |
| **DDI compliance rules** |  |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_information.md">PEP_INFORMATION</a>

<a href="..\pepfx\nf-pepfx-pofxregisterplugin.md">PoFxRegisterPlugin</a>

<a href="..\pepfx\nf-pepfx-pofxregisterpluginex.md">PoFxRegisterPluginEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20AcceptAcpiNotification routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>