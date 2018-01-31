---
UID : NF:fltkernel.FltRemoveExtraCreateParameter
title : FltRemoveExtraCreateParameter function
author : windows-driver-content
description : The FltRemoveExtraCreateParameter routine searches an ECP list for an ECP context structure and, if found, detaches it from the ECP list.
old-location : ifsk\fltremoveextracreateparameter.htm
old-project : ifsk
ms.assetid : 924e9108-f0cf-4202-905c-04a27c15dfa3
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FltRemoveExtraCreateParameter routine [Installable File System Drivers], fltkernel/FltRemoveExtraCreateParameter, ifsk.fltremoveextracreateparameter, FltRemoveExtraCreateParameter, FltApiRef_p_to_z_696787f2-1381-451f-aed4-bf307ee58291.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fltkernel.h
req.include-header : Fltkernel.h
req.target-type : Universal
req.target-min-winverclnt : This routine is available starting with Windows Vista.
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


# FltRemoveExtraCreateParameter function
The <b>FltRemoveExtraCreateParameter</b> routine searches an ECP list for an ECP context structure and, if found, detaches it from the ECP list.

## Syntax

````
NTSTATUS FltRemoveExtraCreateParameter(
  _In_      PFLT_FILTER Filter,
  _Inout_   PECP_LIST   EcpList,
  _In_      LPCGUID     EcpType,
  _Out_     PVOID       *EcpContext,
  _Out_opt_ ULONG       *EcpContextSize
);
````

## Parameters

`Filter`

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

`EcpList`

Pointer to the extra create parameter (ECP) list that contains the ECP context structure to be detached from the given list.

`EcpType`

Pointer to a user-defined GUID that uniquely identifies the ECP context structure to be detached from the list.

`EcpContext`

Pointer to the detached ECP context structure.  If the ECP context structure is successfully detached from the given list, this parameter will be set to point to the detached ECP context structure.  If the ECP context structure is not found in the given ECP list, this parameter is set to <b>NULL</b>.

`EcpContextSize`

Optional parameter that receives the size of the detached ECP context structure.  If this parameter is present when the routine is called, the parameter will receive the size, in bytes, of the detached ECP context structure.  If the given ECP context structure was not found in the given ECP list, this parameter is undefined.


## Return Value

<b>FltRemoveExtraCreateParameter</b> returns one of the following NTSTATUS values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The given ECP context structure was successfully detached from the given ECP list.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The given ECP context structure was not found in the given ECP list.

</td>
</tr>
</table>

## Remarks

The <b>FltRemoveExtraCreateParameter</b> routine searches the ECP list given by the <i>EcpList</i> parameter for an ECP context structure given by the <i>EcpType</i> parameter.  If the ECP context structure exists in the list, it is detached from the list, the <i>EcpContext</i> parameter is set to point to it, and the routine returns STATUS_SUCCESS. If the ECP context structure does not exist in the list, the <i>EcpContext</i> parameter is set to <b>NULL</b> and the routine returns STATUS_NOT_FOUND.


<div class="alert"><b>Note</b>  This routine does not free the memory pool for the ECP context structure.  To free the ECP context structure, first call this routine to detach it from the list and then call the <a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a> routine to free the ECP context structure itself.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** |  |
| **IRQL** | "<= APC_LEVEL" |
| **DDI compliance rules** |  |

## See Also

<b>FltAllocateExtraCreateParameterFromLookasideList</b>

<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>

<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>

<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>

<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>

<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltRemoveExtraCreateParameter routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>