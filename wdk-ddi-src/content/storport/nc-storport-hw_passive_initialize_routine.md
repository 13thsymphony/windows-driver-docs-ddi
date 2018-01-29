---
UID : NC:storport.HW_PASSIVE_INITIALIZE_ROUTINE
title : HW_PASSIVE_INITIALIZE_ROUTINE
author : windows-driver-content
description : The HwStorPassiveInitializeRoutine callback routine is called after the HwStorInitialize routine when the current IRQL is at PASSIVE_LEVEL.
old-location : storage\hwstorpassiveinitializeroutine.htm
old-project : storage
ms.assetid : 70f65a4e-0a98-4135-bb38-530c729538a3
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.hwstorpassiveinitializeroutine, HwStorPassiveInitializeRoutine routine [Storage Devices], HwStorPassiveInitializeRoutine, HW_PASSIVE_INITIALIZE_ROUTINE, HW_PASSIVE_INITIALIZE_ROUTINE, storport/HwStorPassiveInitializeRoutine, stormini_e2404f14-1cdc-44d7-bd58-97acfa57bc36.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : storport.h
req.include-header : Storport.h
req.target-type : Universal
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
req.irql : PASSIVE_LEVEL (See Remarks section.)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER"
req.product : Windows 10 or later.
---


# HW_PASSIVE_INITIALIZE_ROUTINE callback function
The <b>HwStorPassiveInitializeRoutine</b> callback routine is called after the <a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a> routine when the current IRQL is at PASSIVE_LEVEL. The <b>HwStorPassiveInitializeRoutine</b> callback is set by calling the <a href="..\storport\nf-storport-storportenablepassiveinitialization.md">StorPortEnablePassiveInitialization</a> routine. Initializing of the miniport's deferred procedure calls (DPCs) occurs in the <b>HwStorPassiveInitializeRoutine</b> callback.

## Syntax

```
HW_PASSIVE_INITIALIZE_ROUTINE HwPassiveInitializeRoutine;

BOOLEAN HwPassiveInitializeRoutine(
  PVOID DeviceExtension
)
{...}
```

## Parameters

`DeviceExtension`




## Return Value

The <b>HwStorPassiveInitializeRoutine</b> routine returns <b>TRUE</b> if the miniport successfully initialized the processing of DPCs, or <b>FALSE</b> if the initialization process failed.

## Remarks

The <b>HwStorPassiveInitializeRoutine</b> routine should initialize any DPCs that the miniport driver will use. The port driver calls <b>HwStorPassiveInitializeRoutine</b> at PASSIVE_LEVEL without any spin locks held. Interrupts are enabled while this routine is called.

The name <b>HwStorPassiveInitializeRoutine</b> is just a placeholder. The actual prototype for this callback routine is defined in <i>storport.h</i>as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
BOOLEAN
(*PHW_PASSIVE_INITIALIZE_ROUTINE) (
  _In_ PVOID DeviceExtension
  );</pre>
</td>
</tr>
</table></span></div>The port driver calls the <b>HwStorPassiveInitializeRoutine</b> routine at PASSIVE IRQL without acquiring any spin locks.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Storport.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL (See Remarks section.) |
| **DDI compliance rules** |  |

## See Also

<a href="..\storport\nf-storport-storportenablepassiveinitialization.md">StorPortEnablePassiveInitialization</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HW_PASSIVE_INITIALIZE_ROUTINE routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>