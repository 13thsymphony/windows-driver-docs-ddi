---
UID : NF:fltkernel.FltCopyOpenReparseList
title : FltCopyOpenReparseList function
author : windows-driver-content
description : This routine copies any open reparse information from a previous create into a new ECP list that can be used to issue a second create.
old-location : ifsk\fltcopyopenreparselist.htm
old-project : ifsk
ms.assetid : 07C39363-559A-4B55-850E-052BA78E869D
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : fltkernel/FltAddOpenReparseEntry, FltAddOpenReparseEntry, ifsk.fltcopyopenreparselist, FltCopyOpenReparseList, FltAddOpenReparseEntry routine [Installable File System Drivers]
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
req.irql : "_IRQL_requires_max_(APC_LEVEL)"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : EXpsFontRestriction
---


# FltCopyOpenReparseList function
This routine copies any open reparse information from a previous create into
    a new ECP list that can be used to issue a second create.

## Syntax

````
NTSTATUS FltAddOpenReparseEntry(
  _In_    PFLT_FILTER        Filter,
  _In_    PFLT_CALLBACK_DATA Data,
  _Inout_ PECP_LIST          EcpList
);
````

## Parameters

`Filter`

The filter to reference.

`Data`

The create operation from which open reparse
                       information should be copied.

`EcpList`

A new ECP list to copy open reparse information
                       to.


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


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows 10, version 1607 |
| **Target Platform** | Windows |
| **Header** | fltkernel.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | "_IRQL_requires_max_(APC_LEVEL)" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltfreeopenreparselist.md">FltFreeOpenReparseList</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCopyOpenReparseList routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>