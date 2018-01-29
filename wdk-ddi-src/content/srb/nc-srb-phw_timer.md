---
UID : NC:srb.PHW_TIMER
title : PHW_TIMER
author : windows-driver-content
description : The PHW_TIMER routine prototype declares a SCSI miniport driver's timer routine.
old-location : storage\phw_timer.htm
old-project : storage
ms.assetid : 8f537ddb-ba94-4423-95a8-6497710d234f
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.phw_timer, (*PHW_TIMER) callback function [Storage Devices], (*PHW_TIMER), srb/(*PHW_TIMER), ide_minikr_55cc9012-04fa-434c-b2b9-d24bbd1d1404.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : srb.h
req.include-header : Storport.h, Srb.h, Storport.h
req.target-type : Desktop
req.target-min-winverclnt : 
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG"
req.product : Windows 10 or later.
---


# PHW_TIMER callback function
The PHW_TIMER routine prototype declares a SCSI miniport driver's timer routine.

## Syntax

```
PHW_TIMER PhwTimer;

void PhwTimer(
  PVOID DeviceExtension
)
{...}
```

## Parameters

`DeviceExtension`

Pointer to the miniport driver's per-HBA storage area.


## Return Value

None

## Remarks

The SCSI miniport driver's timer routine, <a href="https://msdn.microsoft.com/library/windows/hardware/ff557327">HwScsiTimer</a>, is called after the interval specified when the miniport driver called <b>ScsiPortNotification</b> with the <b>RequestTimerCall</b><i>NotificationType</i> value.

Miniport drivers that work with the StorPort driver do not use this timer routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | srb.h (include Storport.h, Srb.h, Storport.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557327">HwScsiTimer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PHW_TIMER callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>