---
UID: NF:fltkernel.FltAddOpenReparseEntry
title: FltAddOpenReparseEntry function
author: windows-driver-content
description: This routine adds a caller allocated open reparse structure, OPEN_REPARSE_LIST_ENTRY, into a create operation.
old-location: ifsk\fltaddopenreparseentry.htm
old-project: ifsk
ms.assetid: D58AB46A-0D87-45B5-8C58-E99ED0F906D2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltAddOpenReparseEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltAddOpenReparseEntry
req.alt-loc: fltKernel.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _IRQL_requires_max_(APC_LEVEL)
req.typenames: EXpsFontRestriction
---

# FltAddOpenReparseEntry function



## -description
This routine adds a caller allocated open reparse structure, <a href="..\ntifs\ns-ntifs-_open_reparse_list_entry.md">OPEN_REPARSE_LIST_ENTRY</a>,  into a create operation.



## -syntax

````
NTSTATUS FltAddOpenReparseEntry(
  _In_ PFLT_FILTER              Filter,
  _In_ PFLT_CALLBACK_DATA       Data,
  _In_ POPEN_REPARSE_LIST_ENTRY OpenReparseEntry
);
````


## -parameters

### -param Filter [in]

The filter to reference.


### -param Data [in]

The create operation to attach open reparse information to.


### -param OpenReparseEntry [in]

The open reparse information to add, of type <a href="..\ntifs\ns-ntifs-_open_reparse_list_entry.md">OPEN_REPARSE_LIST_ENTRY</a>.


## -returns
The following NT status codes are returned.
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>Status code if <i>Data</i> is not a create operation. This is an error code.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.

 


## -remarks
This routine adds an ECP list and/or ECP as needed.  <i>Filter</i> is referenced
    for the lifetime of the open reparse entry structure, not the ECP itself,
    which is conceptually independent of any specific filter.

Use <a href="..\fltkernel\nf-fltkernel-fltremoveopenreparseentry.md">FltRemoveOpenReparseEntry</a> to remove the open reparse structure from the create operation.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1607

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>FltKernel.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
_IRQL_requires_max_(APC_LEVEL)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltremoveopenreparseentry.md">FltRemoveOpenReparseEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAddOpenReparseEntry routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

