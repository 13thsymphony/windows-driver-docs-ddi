---
UID : NF:ntifs.FsRtlInsertExtraCreateParameter
title : FsRtlInsertExtraCreateParameter function
author : windows-driver-content
description : The FsRtlInsertExtraCreateParameter routine inserts an extra create parameter (ECP) context structure into an ECP list.
old-location : ifsk\fsrtlinsertextracreateparameter.htm
old-project : ifsk
ms.assetid : 77ac37eb-9750-4c56-8e1c-41b8a1f50a61
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FsRtlInsertExtraCreateParameter
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : The FltInsertExtraCreateParameter routine is available starting with Windows Vista.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FsRtlInsertExtraCreateParameter
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : <= APC_LEVEL
req.typenames : TOKEN_TYPE
---


# FsRtlInsertExtraCreateParameter function
The <b>FsRtlInsertExtraCreateParameter</b> routine inserts an extra create parameter (ECP) context structure into an ECP list.

## Syntax

````
NTSTATUS FsRtlInsertExtraCreateParameter(
  _Inout_ PECP_LIST EcpList,
  _Inout_ PVOID     EcpContext
);
````

## Parameters

`EcpList`

Pointer to the ECP list structure to which the ECP context structure, pointed to by the <i>EcpContext</i> parameter, should be added.

`EcpContext`

Pointer to the ECP context structure to be added to the ECP list, pointed to by the <i>EcpList</i> parameter.


## Return Value

<b>FsRtlInsertExtraCreateParameter</b> returns one of the following NTSTATUS values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The given ECP context structure was successfully inserted into the given ECP list.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The given ECP context structure already exists in the given ECP list.  In the context of ECP list insertion, two ECP context structures are considered to be identical if they contain equal GUID values.

## Remarks

The <b>FsRtlInsertExtraCreateParameter</b> routine assumes that the given ECP context structure to be inserted into the given ECP list was previously allocated by the <a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a> routine.

Each ECP context structure inserted into the ECP list must have a unique GUID value. This unique value is set when the ECP context structure is allocated by the <a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlInsertExtraCreateParameter routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>