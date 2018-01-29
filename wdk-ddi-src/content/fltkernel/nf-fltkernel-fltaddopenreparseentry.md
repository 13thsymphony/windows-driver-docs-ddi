---
UID : NF:fltkernel.FltAddOpenReparseEntry
title : FltAddOpenReparseEntry function
author : windows-driver-content
description : This routine adds a caller allocated open reparse structure, OPEN_REPARSE_LIST_ENTRY, into a create operation.
old-location : ifsk\fltaddopenreparseentry.htm
old-project : ifsk
ms.assetid : D58AB46A-0D87-45B5-8C58-E99ED0F906D2
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : fltkernel/FltAddOpenReparseEntry, FltAddOpenReparseEntry, ifsk.fltaddopenreparseentry, FltAddOpenReparseEntry routine [Installable File System Drivers]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fltkernel.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1607
req.target-min-winversvr : Windows Server 2016
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
req.irql : _IRQL_requires_max_(APC_LEVEL)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : EXpsFontRestriction
---


# FltAddOpenReparseEntry function
This routine adds a caller allocated open reparse structure, <a href="..\ntifs\ns-ntifs-_open_reparse_list_entry.md">OPEN_REPARSE_LIST_ENTRY</a>,  into a create operation.

## Syntax

````
NTSTATUS FltAddOpenReparseEntry(
  _In_ PFLT_FILTER              Filter,
  _In_ PFLT_CALLBACK_DATA       Data,
  _In_ POPEN_REPARSE_LIST_ENTRY OpenReparseEntry
);
````

## Parameters

`Filter`

The filter to reference.

`Data`

The create operation to attach open reparse information to.

`OpenReparseEntry`

The open reparse information to add, of type <a href="..\ntifs\ns-ntifs-_open_reparse_list_entry.md">OPEN_REPARSE_LIST_ENTRY</a>.


## Return Value

The following NT status codes are returned.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
Status code if <i>Data</i> is not a create operation. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
</table>

## Remarks

This routine adds an ECP list and/or ECP as needed.  <i>Filter</i> is referenced
    for the lifetime of the open reparse entry structure, not the ECP itself,
    which is conceptually independent of any specific filter.

Use <a href="..\fltkernel\nf-fltkernel-fltremoveopenreparseentry.md">FltRemoveOpenReparseEntry</a> to remove the open reparse structure from the create operation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fltkernel.h |
| **Library** |  |
| **IRQL** | _IRQL_requires_max_(APC_LEVEL) |
| **DDI compliance rules** |  |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltremoveopenreparseentry.md">FltRemoveOpenReparseEntry</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAddOpenReparseEntry routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>