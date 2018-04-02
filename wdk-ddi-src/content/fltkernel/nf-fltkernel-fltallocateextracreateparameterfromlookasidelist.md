---
UID: NF:fltkernel.FltAllocateExtraCreateParameterFromLookasideList
title: FltAllocateExtraCreateParameterFromLookasideList function
author: windows-driver-content
description: The FltAllocateExtraCreateParameterFromLookasideList routine allocates memory pool from a given lookaside list for an extra create parameter (ECP) context structure and generates a pointer to that structure.
old-location: ifsk\fltallocateextracreateparameterfromlookasidelist.htm
old-project: ifsk
ms.assetid: 33ab7ff3-d9b0-43ad-9971-62735f3240df
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltAllocateExtraCreateParameterFromLookasideList, FltAllocateExtraCreateParameterFromLookasideList routine [Installable File System Drivers], FltApiRef_a_to_d_27580c4f-61c2-46b1-be1c-8895c918a05e.xml, fltkernel/FltAllocateExtraCreateParameterFromLookasideList, ifsk.fltallocateextracreateparameterfromlookasidelist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltAllocateExtraCreateParameterFromLookasideList
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltAllocateExtraCreateParameterFromLookasideList function
The <b>FltAllocateExtraCreateParameterFromLookasideList </b>routine allocates memory pool from a given lookaside list for an extra create parameter (ECP) context structure and generates a pointer to that structure.

## Syntax

```
NTSTATUS FLTAPI FltAllocateExtraCreateParameterFromLookasideList(
  PFLT_FILTER                                    Filter,
  LPCGUID                                        EcpType,
  ULONG                                          SizeOfContext,
  FSRTL_ALLOCATE_ECP_FLAGS                       Flags,
  PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK CleanupCallback,
  PVOID                                          LookasideList,
  PVOID                                          *EcpContext
);
```

## Parameters

`Filter`

Opaque filter pointer to the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

`EcpType`

Pointer to a GUID that indicates the type of the ECP context structure.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a> for more information.

`SizeOfContext`

The size, in bytes, of the ECP context structure.

`Flags`

Defines pool allocation options.  If the value of the <i>SizeOfContext</i> parameter is larger than the size, in bytes, of the given lookaside list, the ECP context structure will be allocated from system pool instead of the lookaside list.  In this case, if the <i>Flags</i> parameter contains the FSRTL_ALLOCATE_ECP_FLAG_CHARGE_QUOTA bit flag value, system pool allocated by the routine will be charged against the current process' memory quota. See the <i>Flags</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff541728">FltAllocateExtraCreateParameter</a> for more information.  In the more typical case when memory for the ECP context structure is allocated from the lookaside list, the FSRTL_ALLOCATE_ECP_FLAG_CHARGE_QUOTA bit flag is not used by the routine.

`CleanupCallback`

Optional pointer to a minifilter-defined cleanup callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551124">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>.  The cleanup callback routine is called when the ECP context structure is deleted.  Set this parameter to <b>NULL</b> if a cleanup callback routine is not applicable.

`LookasideList`

Pointer to an initialized lookaside list in which to attempt to allocate pool from (for the ECP context structure).  To initialize the lookaside list, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543261">FltInitExtraCreateParameterLookasideList</a> routine.

`EcpContext`

Receives a pointer to the allocated ECP context structure.  If the routine failed to allocate sufficient pool for the ECP context structure, <i>EcpContext </i>will be <b>NULL</b> and the routine will return status code STATUS_INSUFFICIENT_RESOURCES.


## Return Value

The <b>FltAllocateExtraCreateParameterFromLookasideList</b> routine can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The <b>FltAllocateExtraCreateParameterFromLookasideList</b> routine was unable to allocate sufficient memory for an ECP context structure.  In this case, <i>EcpContext</i> will be <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The ECP context structure was successfully allocated.  In this case, a pointer to the allocated structure is returned by the <i>EcpContext </i>parameter.

</td>
</tr>
</table>

## Remarks

This routine is available starting with Windows Vista. 

The <b>FltAllocateExtraCreateParameterFromLookasideList</b> routine allocates memory pool for an ECP context structure from the given initialized paged or non-paged lookaside list.  However, if the size of the ECP context structure (as defined by the <i>SizeOfContext</i>  parameter) is larger than the lookaside list, the routine analogously allocates memory from paged or non-paged system pool.

Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543261">FltInitExtraCreateParameterLookasideList</a> routine to initialize a paged or non-paged pool lookaside list. Use the <b>FltAllocateExtraCreateParameterFromLookasideList</b> routine to allocate an ECP context structure from the lookaside list, and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542957">FltFreeExtraCreateParameter</a> routine to deallocate the ECP context structure.

Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541973">FltDeleteExtraCreateParameterLookasideList</a> routine to free a lookaside list.

Drivers must free all ECP context structures and lookaside lists they create before unloading.

For more information on using lookaside lists with drivers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541728">FltAllocateExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541741">FltAllocateExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541973">FltDeleteExtraCreateParameterLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542957">FltFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542964">FltFreeExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543261">FltInitExtraCreateParameterLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543305">FltInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551124">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>