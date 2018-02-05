---
UID : NF:ntifs.FsRtlFreeExtraCreateParameter
title : FsRtlFreeExtraCreateParameter function
author : windows-driver-content
description : The FsRtlFreeExtraCreateParameter routine frees the memory for an ECP context structure.
old-location : ifsk\fsrtlfreeextracreateparameter.htm
old-project : ifsk
ms.assetid : c46cdfd3-36c4-420d-9dbf-d6f0bede460e
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : fsrtlref_bbee8298-87e1-4487-bf56-b2dd76913d47.xml, FsRtlFreeExtraCreateParameter, ifsk.fsrtlfreeextracreateparameter, FsRtlFreeExtraCreateParameter routine [Installable File System Drivers], ntifs/FsRtlFreeExtraCreateParameter
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : The FsRtlFreeExtraCreateParameter routine is available starting with Windows Vista.
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
req.irql : "<= APC_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# FsRtlFreeExtraCreateParameter function
The <b>FsRtlFreeExtraCreateParameter</b> routine frees the memory for an ECP context structure.

## Syntax

````
VOID FsRtlFreeExtraCreateParameter(
  _In_ PVOID EcpContext
);
````

## Parameters

`EcpContext`

Pointer to the extra create parameter (ECP) context structure to be freed.


## Return Value

None

## Remarks

If the ECP context structure to be freed is still attached to an ECP list, it must first be detached from the list by the <a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a> routine before the <b>FsRtlFreeExtraCreateParameter</b> routine can free it.

If a cleanup callback routine of type <a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a> was defined for the given ECP context structure, this callback routine is invoked upon deletion of the ECP context structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The FsRtlFreeExtraCreateParameter routine is available starting with Windows Vista. The FsRtlFreeExtraCreateParameter routine is available starting with Windows Vista. |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>

<a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>

<b>FltAllocateExtraCreateParameterFromLookasideList</b>

<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>

<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>

<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>

<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlFreeExtraCreateParameter routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>