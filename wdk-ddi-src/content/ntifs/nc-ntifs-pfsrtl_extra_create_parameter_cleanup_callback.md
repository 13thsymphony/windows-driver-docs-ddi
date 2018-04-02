---
UID: NC:ntifs.PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK
title: PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK
author: windows-driver-content
description: A file system filter driver (legacy filter) or a minifilter driver can register a PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK-typed routine as the filter driver's CleanupCallback callback routine for an extra create parameter (ECP) context structure.
old-location: ifsk\pfsrtl_extra_create_parameter_cleanup_callback.htm
old-project: ifsk
ms.assetid: 76dc75fa-90ee-4fe7-b8f2-45e1a08a061f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FilterCallbacks_afe97c84-8818-4577-ad94-8f8fdf044570.xml, PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK, PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK function pointer [Installable File System Drivers], ifsk.pfsrtl_extra_create_parameter_cleanup_callback, ntifs/PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of all Windows operating systems.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ntifs.h
api_name:
-	PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK
product: Windows
targetos: Windows
req.typenames: VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
---


# PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK callback function
A file system filter driver (legacy filter) or a minifilter driver can register a PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK-typed routine as the filter driver's <i>CleanupCallback</i> callback routine for an extra create parameter (ECP) context structure.

## Syntax

```
PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK PfsrtlExtraCreateParameterCleanupCallback;

void PfsrtlExtraCreateParameterCleanupCallback(
  PVOID EcpContext,
  LPCGUID EcpType
)
{...}
```

## Parameters

`EcpContext`

An ECP context pointer that was returned by the routine that allocated the ECP context structure.

`EcpType`

A pointer to a GUID that was passed to the routine that allocated the ECP context structure, that indicates the extra create parameter type.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a>.


## Return Value

None

## Remarks

When a file system filter driver (legacy filter) or a minifilter driver allocates an ECP context structure, it can optionally specify a PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK-typed routine as the filter driver's <i>CleanupCallback</i> callback routine.  If the filter driver specifies a <i>CleanupCallback</i> callback routine, the operating system will invoke the <i>CleanupCallback</i> routine (regardless of IRQ level).  This <i>CleanupCallback</i> routine performs any necessary ECP context-related cleanup processing when the ECP context structure is deleted.

To specify a callback routine, a filter driver passes a pointer to the callback routine by using the <i>CleanupCallback</i> parameter of the routine that originally allocated the ECP context structure.  If a callback routine is not needed, a <b>NULL</b> value must be passed to the <i>CleanupCallback</i> parameter. 

The following routines support the PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK-typed callback routine:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541728">FltAllocateExtraCreateParameter</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541734">FltAllocateExtraCreateParameterFromLookasideList</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545609">FsRtlAllocateExtraCreateParameter</a>


</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of all Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | ntifs.h (include Ntifs.h, FltKernel.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541728">FltAllocateExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541734">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541741">FltAllocateExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542957">FltFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542964">FltFreeExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>