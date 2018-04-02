---
UID: NF:fltkernel.FltInitExtraCreateParameterLookasideList
title: FltInitExtraCreateParameterLookasideList function
author: windows-driver-content
description: The FltInitExtraCreateParameterLookasideList routine initializes a paged or non-paged pool lookaside list used for the allocation of one or more extra create parameter context structures (ECPs) of fixed size.
old-location: ifsk\fltinitextracreateparameterlookasidelist.htm
old-project: ifsk
ms.assetid: bec492df-86ac-4e1b-8623-5656aa20c4c5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_b9cff240-0f03-4756-86d0-a44612df8e58.xml, FltInitExtraCreateParameterLookasideList, FltInitExtraCreateParameterLookasideList routine [Installable File System Drivers], fltkernel/FltInitExtraCreateParameterLookasideList, ifsk.fltinitextracreateparameterlookasidelist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltInitExtraCreateParameterLookasideList routine is available starting with Windows Vista.
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
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltInitExtraCreateParameterLookasideList
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltInitExtraCreateParameterLookasideList function
The <b>FltInitExtraCreateParameterLookasideList </b>routine initializes a paged or non-paged pool lookaside list used for the allocation of one or more extra create parameter context structures (ECPs) of fixed size.

## Syntax

```
VOID FLTAPI FltInitExtraCreateParameterLookasideList(
  PFLT_FILTER               Filter,
  PVOID                     Lookaside,
  FSRTL_ECP_LOOKASIDE_FLAGS Flags,
  SIZE_T                    Size,
  ULONG                     Tag
);
```

## Parameters

`Filter`

Opaque filter pointer to the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

`Lookaside`

Pointer to an opaque <a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a> lookaside list-head structure.  For a paged or non-paged lookaside list, the list-head structure must be allocated from non-paged pool.

`Flags`

Defines pool allocation options.  If the <i>Flags</i> parameter contains the FSRTL_ECP_LOOKASIDE_FLAG_NONPAGED_POOL bit flag value, the routine initializes a lookaside list for non-paged ECP entries of the specified size.  Otherwise, the routine initializes a lookaside list for paged ECP entries of the specified size.

`Size`

Specifies the size, in bytes, for all ECP entries in the lookaside list.

`Tag`

Specifies the pool tag to use when allocating lookaside list ECP entries. For more information about pool tags, see the <i>Tag</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>.


## Return Value

None

## Remarks

Use this routine to initialize a paged or non-paged pool lookaside list. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541734">FltAllocateExtraCreateParameterFromLookasideList</a> routine to allocate an ECP from the lookaside list, and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542957">FltFreeExtraCreateParameter</a> routine to return an ECP buffer to the lookaside list for recycling.

Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541973">FltDeleteExtraCreateParameterLookasideList</a> routine to free the lookaside list itself.

Drivers must free all ECPs and lookaside lists that they created before unloading.

For more information on using lookaside lists with drivers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The FltInitExtraCreateParameterLookasideList routine is available starting with Windows Vista.  |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541728">FltAllocateExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541734">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541741">FltAllocateExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541973">FltDeleteExtraCreateParameterLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542957">FltFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542964">FltFreeExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543305">FltInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551124">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>