---
UID: NE:pmi.PMI_EVENT_TYPE
title: PMI_EVENT_TYPE
author: windows-driver-content
description: The PMI_EVENT_TYPE enumeration defines the type of PMI power meter event that is returned through the successful completion of an IOCTL_PMI_REGISTER_EVENT_NOTIFY request.
old-location: powermeter\pmi_event_type.htm
old-project: powermeter
ms.assetid: c2a8422d-15f0-45df-bc54-946fb3d11a22
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PmiBudgetEvent, pmi/PmiBudgetEvent, pmi/PmiThresholdEvent, PmiCapabilitiesChangedEvent, PmiEventMax, PmiThresholdEvent, PowerMeterRef_86ff4160-2977-4b72-a37f-72779df2d5dc.xml, PMI_EVENT_TYPE enumeration [Power Metering and Budgeting Devices], pmi/PmiCapabilitiesChangedEvent, pmi/PMI_EVENT_TYPE, PmiConfigurationChangedEvent, pmi/PmiAveragingIntervalChangedEvent, PMI_EVENT_TYPE, PmiAveragingIntervalChangedEvent, pmi/PmiEventMax, pmi/PmiConfigurationChangedEvent, powermeter.pmi_event_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pmi.h
req.include-header: Pmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pmi.h
apiname:
-	PMI_EVENT_TYPE
product: Windows
targetos: Windows
req.typenames: PMI_EVENT_TYPE
---

# PMI_EVENT_TYPE Enumeration
The PMI_EVENT_TYPE enumeration defines the type of PMI power meter event that is returned through the successful completion of an <a href="..\pmi\ni-pmi-ioctl_pmi_register_event_notify.md">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a> request.

## Syntax
````
typedef enum  { 
  PmiCapabilitiesChangedEvent,
  PmiThresholdEvent,
  PmiConfigurationChangedEvent,
  PmiBudgetEvent,
  PmiAveragingIntervalChangedEvent,
  PmiEventMax
} PMI_EVENT_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>PmiAveragingIntervalChangedEvent</td>
                    <td>The event was caused because the interval, during which the power meter averages power measurement data, was changed.</td>
                </tr>
            
                <tr>
                    <td>PmiBudgetEvent</td>
                    <td>The event was caused because the power budget exceeded or fell below the configured budget of the power meter.</td>
                </tr>
            
                <tr>
                    <td>PmiCapabilitiesChangedEvent</td>
                    <td>The event was caused by a change in the PMI capabilities of the power meter.</td>
                </tr>
            
                <tr>
                    <td>PmiConfigurationChangedEvent</td>
                    <td>The event was caused by a change in the PMI configuration of the power meter.</td>
                </tr>
            
                <tr>
                    <td>PmiEventMax</td>
                    <td>The maximum number of PMI event types.</td>
                </tr>
            
                <tr>
                    <td>PmiThresholdEvent</td>
                    <td>The event was caused because the power level exceeded a configured threshold of the power meter.</td>
                </tr>
</table>

## Remarks

The <b>EventType</b> member of the <a href="..\pmi\ns-pmi-_pmi_event.md">PMI_EVENT</a> structure contains information about the type of PMI event data that is referenced by the <b>Event</b> member of that structure. This structure is returned through a successful completion of an <a href="..\pmi\ni-pmi-ioctl_pmi_register_event_notify.md">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a> request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems. Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems. |
| **Header** | pmi.h (include Pmi.h) |

## See Also

<a href="..\pmi\ns-pmi-_pmi_event.md">PMI_EVENT</a>



<a href="..\pmi\ni-pmi-ioctl_pmi_register_event_notify.md">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_EVENT_TYPE enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>