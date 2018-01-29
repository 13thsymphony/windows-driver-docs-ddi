---
UID : NF:rxcontx.RxCreateRxContext
title : RxCreateRxContext function
author : windows-driver-content
description : RxCreateRxContext allocates a new RX_CONTEXT structure and initializes the data structure.
old-location : ifsk\rxcreaterxcontext.htm
old-project : ifsk
ms.assetid : ff39aebb-03c0-4ba4-844a-417579ed2bbf
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : rxcontx/RxCreateRxContext, RxCreateRxContext, rxref_ceb498ca-e985-4100-a104-8333abb41fdf.xml, ifsk.rxcreaterxcontext, RxCreateRxContext function [Installable File System Drivers]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : rxcontx.h
req.include-header : Rxprocs.h  rxcontx.h
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : "<= APC_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*LPRILWRITEPHONEBOOKENTRYPARAMS, RILWRITEPHONEBOOKENTRYPARAMS"
req.product : Windows 10 or later.
---


# RxCreateRxContext function
<b>RxCreateRxContext</b> allocates a new RX_CONTEXT structure and initializes the data structure.

## Syntax

````
PRX_CONTEXT RxCreateRxContext(
  _In_opt_ PIRP                 Irp,
  _In_     PRDBSS_DEVICE_OBJECT RxDeviceObject,
  _In_     ULONG                InitialContextFlags
);
````

## Parameters

`Irp`

A pointer to the IRP to be encapsulated by this RX_CONTEXT structure.

`RxDeviceObject`

A pointer to the device object to which this RX_CONTEXT and IRP apply.

`InitialContextFlags`

The set of initial values for the <b>Flags</b> member of the RX_CONTEXT data structure to be stored in the RX_CONTEXT structure. These initial values can be any combination of the following enumerations:


## Return Value

<b>RxCreateRxContext</b> returns a pointer to an allocated RX_CONTEXT data structure on success or a <b>NULL</b> pointer on failure.

## Remarks

<b>RxCreateRxContext</b> calls <a href="..\rxcontx\nf-rxcontx-rxinitializecontext.md">RxInitializeContext</a> to initialize the newly created RX_CONTEXT structure before returning. 

<b>RxCreateRxContext</b> allocates non-paged pool memory when creating a new RX_CONTEXT data structure and sets the following value in the Flags member of the RX_CONTEXT:



When this value is set, the RX_CONTEXT structure was allocated from non-paged pool memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rxcontx.h (include Rxprocs.h  rxcontx.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\rxcontx\nf-rxcontx-rxresumeblockedoperations_serially.md">RxResumeBlockedOperations_Serially</a>

<a href="..\rxprocs\nf-rxprocs-rxcompleterequest_real.md">RxCompleteRequest_Real</a>

<a href="..\rxprocs\nf-rxprocs-rxcompleterequest.md">RxCompleteRequest</a>

<a href="..\rxcontx\ns-rxcontx-_rx_context.md">RX_CONTEXT</a>

<a href="..\rxcontx\nf-rxcontx-rxdereferenceanddeleterxcontext_real.md">RxDereferenceAndDeleteRxContext_Real</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557382">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>

<a href="..\rxcontx\nf-rxcontx-__rxsynchronizeblockingoperations.md">__RxSynchronizeBlockingOperations</a>

<a href="..\rxcontx\nf-rxcontx-rxpreparecontextforreuse.md">RxPrepareContextForReuse</a>

<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>

<a href="..\rxcontx\nf-rxcontx-rxinitializecontext.md">RxInitializeContext</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCreateRxContext function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>