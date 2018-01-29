---
UID : NF:ntddk.RtlRunOnceExecuteOnce
title : RtlRunOnceExecuteOnce function
author : windows-driver-content
description : The RtlRunOnceExecuteOnce performs a one-time initialization.
old-location : kernel\rtlrunonceexecuteonce.htm
old-project : kernel
ms.assetid : 2769eb2c-33e2-4e3f-a1bf-1ebc9213b224
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlRunOnceExecuteOnce, kernel.rtlrunonceexecuteonce, k109_c1729bff-038f-4714-b422-1b97dd5a9c19.xml, ntddk/RtlRunOnceExecuteOnce, RtlRunOnceExecuteOnce function [Kernel-Mode Driver Architecture]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : Ntddk.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows Vista.
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
req.irql : <= APC_LEVEL (See Remarks section.)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---


# RtlRunOnceExecuteOnce function
The <b>RtlRunOnceExecuteOnce</b> performs a one-time initialization.

## Syntax

````
NTSTATUS RtlRunOnceExecuteOnce(
  _Inout_ PRTL_RUN_ONCE         RunOnce,
  _In_    PRTL_RUN_ONCE_INIT_FN InitFn,
  _Inout_ PVOID                 Parameter,
  _Out_   PVOID                 *Context
);
````

## Parameters

`RunOnce`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563626">RTL_RUN_ONCE</a> one-time initialization structure.

`InitFn`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563635">RunOnceInitialization</a> routine.

`Context`

A pointer to a PVOID variable that receives the initialized data.

`Parameter`

The value to pass as the <i>Parameter</i> parameter to the <i>RunOnceInitialization</i> routine.


## Return Value

<b>RtlRunOnceExecuteOnce</b> returns STATUS_SUCCESS if the operation succeeds, or the appropriate NTSTATUS error code if the operation fails.

## Remarks

For the first call to <b>RtlRunOnceExecuteOnce</b> for a particular <a href="https://msdn.microsoft.com/library/windows/hardware/ff563626">RTL_RUN_ONCE</a> structure, <b>RtlRunOnceExecuteOnce</b> calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563635">RunOnceInitialization</a> routine to initialize the data. Every subsequent call to <b>RtlRunOnceExecuteOnce</b> for that structure supplies the same initialized data. The <i>RunOnceInitialization</i> routine will not be called twice for the same <b>RTL_RUN_ONCE</b> structure.

<b>RtlRunOnceExecuteOnce</b> runs with normal kernel APCs disabled. The routine should not be called within a special kernel APC unless all calls occur at APC_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL (See Remarks section.) |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563635">RunOnceInitialization</a>

<a href="..\ntddk\nf-ntddk-rtlrunoncecomplete.md">RtlRunOnceComplete</a>

<a href="..\ntddk\nf-ntddk-rtlrunonceinitialize.md">RtlRunOnceInitialize</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563626">RTL_RUN_ONCE</a>

<a href="..\ntddk\nf-ntddk-rtlrunoncebegininitialize.md">RtlRunOnceBeginInitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlRunOnceExecuteOnce function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>