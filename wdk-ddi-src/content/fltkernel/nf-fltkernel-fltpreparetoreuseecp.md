---
UID : NF:fltkernel.FltPrepareToReuseEcp
title : FltPrepareToReuseEcp function
author : windows-driver-content
description : The FltPrepareToReuseEcp routine resets an extra create parameter (ECP) context structure, which prepares it for reuse.
old-location : ifsk\fltpreparetoreuseecp.htm
old-project : ifsk
ms.assetid : E08E2ED1-047B-4190-8A54-79ECC75E860F
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ifsk.fltpreparetoreuseecp, FltPrepareToReuseEcp routine [Installable File System Drivers], fltkernel/FltPrepareToReuseEcp, FltPrepareToReuseEcp
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fltkernel.h
req.include-header : Fltkernel.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 8.
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
req.lib : FltMgr.lib
req.dll : Fltmgr.sys
req.irql : "<= APC_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : EXpsFontRestriction
---


# FltPrepareToReuseEcp function
The <b>FltPrepareToReuseEcp</b> routine resets an extra create parameter (ECP) context structure,  which prepares  it for reuse.

## Syntax

````
VOID FltPrepareToReuseEcp(
  _In_ PFLT_FILTER Filter,
  _In_ PVOID       EcpContext
);
````

## Parameters

`Filter`

An opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

`EcpContext`

A pointer to the ECP to prepare for reuse.


## Return Value

None.

## Remarks

The <b>FltPrepareToReuseEcp</b> allows reuse of an ECP used in a previous create request. This prevents having to initialize a new ECP with the same information.

The target of an ECP uses <a href="..\fltkernel\nf-fltkernel-fltacknowledgeecp.md">FltAcknowledgeEcp</a> to mark the ECP as acknowledged. This indicates that the ECP was discovered and processed.  To reuse a previously acknowledged ECP, such as in processing a reparse, a driver can use <b>FltPrepareToReuseEcp</b> to clear the acknowledged state from the ECP before sending it in another create request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>

<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltlInsertExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>

<a href="..\fltkernel\nf-fltkernel-fltisecpacknowledged.md">FltIsEcpAcknowledged</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>

<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltPrepareToReuseEcp routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>