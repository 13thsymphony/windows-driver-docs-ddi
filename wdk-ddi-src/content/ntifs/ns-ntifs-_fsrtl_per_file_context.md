---
UID : NS:ntifs._FSRTL_PER_FILE_CONTEXT
title : _FSRTL_PER_FILE_CONTEXT
author : windows-driver-content
description : A legacy file system filter driver can use a FSRTL_PER_FILE_CONTEXT structure to associate driver-specific context information to an open file.
old-location : ifsk\fsrtl_per_file_context.htm
old-project : ifsk
ms.assetid : d20668f0-b076-4edd-bf21-98841cbbdc74
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _FSRTL_PER_FILE_CONTEXT, FSRTL_PER_FILE_CONTEXT, *PFSRTL_PER_FILE_CONTEXT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntifs.h
req.include-header : Fltkernel.h, Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : Available starting withWindows Vista.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FSRTL_PER_FILE_CONTEXT
req.alt-loc : ntifs.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : FSRTL_PER_FILE_CONTEXT, *PFSRTL_PER_FILE_CONTEXT
---

# _FSRTL_PER_FILE_CONTEXT structure
A legacy file system filter driver can use a <b>FSRTL_PER_FILE_CONTEXT</b> structure to associate driver-specific context information to an open file.

## Syntax
````
typedef struct _FSRTL_PER_FILE_CONTEXT {
  LIST_ENTRY     Links;
  PVOID          OwnerId;
  PVOID          InstanceId;
  PFREE_FUNCTION FreeCallback;
} FSRTL_PER_FILE_CONTEXT, *PFSRTL_PER_FILE_CONTEXT;
````

## Members

        
            `FreeCallback`

            A pointer to a <a href="https://msdn.microsoft.com/291b57d9-3bef-4acb-a571-86b67a03cd08">callback routine</a> that frees the per-file context structure. Filter drivers must set this member to a non-<b>NULL</b> value.
        
            `InstanceId`

            A pointer to a filter-driver-allocated buffer that can be used to distinguish among the per-file context structures that are created by the same filter driver. The format of this variable is filter-driver-specific. Filter drivers can set this member to <b>NULL</b>.
        
            `Links`

            A link for this structure in the list of all per-file context structures that are associated with the same file. <a href="..\ntifs\nf-ntifs-fsrtlinsertperfilecontext.md">FsRtlInsertPerFileContext</a> inserts this member into the list of all per-file context structures for a file.
        
            `OwnerId`

            A pointer to a filter-driver-allocated buffer that uniquely identifies the owner of the per-file context structure. The format of this variable is filter-driver-specific.  Filter drivers must set this member to a non-<b>NULL</b> value.

    ## Remarks
        In order to associate context information with a file, a legacy filter driver first allocates a <b>FSRTL_PER_FILE_CONTEXT</b> structure and initializes it using <a href="..\ntifs\nf-ntifs-fsrtlinsertperfilecontext.md">FsRtlInsertPerFileContext</a>. The driver then uses <b>FsRtlInsertPerFileContext</b> to associate that <b>FSRTL_PER_FILE_CONTEXT</b> object with the file. When the system tears down the file context object for a file, it calls <a href="..\ntifs\nf-ntifs-fsrtlteardownperfilecontexts.md">FsRtlTeardownPerFileContexts</a> which calls the <i>FreeCallback</i> routine that is specified in the <b>FSRTL_PER_FILE_CONTEXT</b> object. That callback must free the driver-specific context object.

Filter writers should choose an <b>OwnerID</b> value that is both meaningful and convenient, such as the address of a driver object or device object. 

Filter writers should choose an <b>InstanceID</b> value that is both meaningful and convenient, such as the address of the file context object for the file. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546051">FsRtlGetPerFileContextPointer</a> macro to retrieve that address from a file object.

The <b>FSRTL_PER_FILE_CONTEXT</b> structure can be used as-is, or embedded in a driver-defined, per-file context structure.

The <b>FSRTL_PER_FILE_CONTEXT</b> structure can be allocated from paged or nonpaged pool. 

The <b>FsRtlInitPerFileContext</b> macro initializes a <b>FSRTL_PER_FILE_CONTEXT</b> structure.

Parameters

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Fltkernel.h, Ntifs.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546051">FsRtlGetPerFileContextPointer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546161">FsRtlInitPerFileContext</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlinsertperfilecontext.md">FsRtlInsertPerFileContext</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlteardownperfilecontexts.md">FsRtlTeardownPerFileContexts</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551123">PFREE_FUNCTION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/6be3ff10-47e4-47f5-8f15-88a80a16f451">Tracking Per-File Context in a Legacy File System Filter Driver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FSRTL_PER_FILE_CONTEXT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>