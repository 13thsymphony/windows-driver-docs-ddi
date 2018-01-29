---
UID : NF:wdm.PoSetSystemState
title : PoSetSystemState function
author : windows-driver-content
description : Drivers call the PoSetSystemState routine to indicate that the system is active.
old-location : kernel\posetsystemstate.htm
old-project : kernel
ms.assetid : b62db582-381a-457f-9755-d8667c7561af
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.posetsystemstate, wdm/PoSetSystemState, portn_f20a5d5b-d863-4ff7-8837-6a7e625271d7.xml, PoSetSystemState routine [Kernel-Mode Driver Architecture], PoSetSystemState
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 2000.
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
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# PoSetSystemState function
Drivers call the <b>PoSetSystemState</b> routine to indicate that the system is active.

## Syntax

````
VOID PoSetSystemState(
  _In_ EXECUTION_STATE Flags
);
````

## Parameters

`Flags`

Indicates the system activity, as specified by a bitwise OR of one or more of the following values:


## Return Value

None

## Remarks

A driver calls <b>PoSetSystemState</b> to set flags indicating that system activity is occurring. Unlike <a href="..\wdm\nf-wdm-poregistersystemstate.md">PoRegisterSystemState</a>, this routine does not allow the driver to set a persistent busy state. 

The <i>Flags</i> parameter specifies the type of activity occurring. Drivers can specify any combination of the flags.

Drivers can set the system busy state to request that the system avoid leaving of the working state while driver activity is occurring. Note, however, that under some circumstances (such as a critically low battery) the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a> may override this request and put the system to sleep anyway.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-poregistersystemstate.md">PoRegisterSystemState</a>

<a href="..\wdm\nf-wdm-pounregistersystemstate.md">PoUnregisterSystemState</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoSetSystemState routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>