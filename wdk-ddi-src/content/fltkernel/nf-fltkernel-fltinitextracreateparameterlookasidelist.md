---
UID: NF:fltkernel.FltInitExtraCreateParameterLookasideList
title: FltInitExtraCreateParameterLookasideList function
author: windows-driver-content
description: The FltInitExtraCreateParameterLookasideList routine initializes a paged or non-paged pool lookaside list used for the allocation of one or more extra create parameter context structures (ECPs) of fixed size.
old-location: ifsk\fltinitextracreateparameterlookasidelist.htm
old-project: ifsk
ms.assetid: bec492df-86ac-4e1b-8623-5656aa20c4c5
ms.author: windowsdriverdev
ms.date: 2/16/2018
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

````
VOID FltInitExtraCreateParameterLookasideList(
  _In_    PFLT_FILTER               Filter,
  _Inout_ PVOID                     Lookaside,
  _In_    FSRTL_ECP_LOOKASIDE_FLAGS Flags,
  _In_    SIZE_T                    Size,
  _In_    ULONG                     Tag
);
````

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

Specifies the pool tag to use when allocating lookaside list ECP entries. For more information about pool tags, see the <i>Tag</i> parameter of <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>.


## Return Value

None

## Remarks

Use this routine to initialize a paged or non-paged pool lookaside list. Use the <a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a> routine to allocate an ECP from the lookaside list, and the <a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a> routine to return an ECP buffer to the lookaside list for recycling.

Use the <a href="..\fltkernel\nf-fltkernel-fltdeleteextracreateparameterlookasidelist.md">FltDeleteExtraCreateParameterLookasideList</a> routine to free the lookaside list itself.

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

<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>



<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a>



<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>



<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a>



<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>



<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltdeleteextracreateparameterlookasidelist.md">FltDeleteExtraCreateParameterLookasideList</a>



<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>



<a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltInitExtraCreateParameterLookasideList routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>