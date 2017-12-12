---
UID: NF.fltkernel.FltCopyOpenReparseList
title: FltCopyOpenReparseList function
author: windows-driver-content
description: This routine copies any open reparse information from a previous create into a new ECP list that can be used to issue a second create.
old-location: ifsk\fltcopyopenreparselist.htm
old-project: ifsk
ms.assetid: 07C39363-559A-4B55-850E-052BA78E869D
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltCopyOpenReparseList
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
---

# FltCopyOpenReparseList function



## -description
This routine copies any open reparse information from a previous create into
    a new ECP list that can be used to issue a second create.



## -syntax

````
NTSTATUS FltAddOpenReparseEntry(
  _In_    PFLT_FILTER        Filter,
  _In_    PFLT_CALLBACK_DATA Data,
  _Inout_ PECP_LIST          EcpList
);
````


## -parameters

### -param Filter [in]

The filter to reference.


### -param Data [in]

The create operation from which open reparse
                       information should be copied.


### -param EcpList [in, out]

A new ECP list to copy open reparse information
                       to.


## -returns
The following NT status codes are returned.
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>Status code if <i>Data</i> is not a create operation. This is an error code.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.

 


## -remarks


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
<a href="ifsk.fltfreeopenreparselist">FltFreeOpenReparseList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCopyOpenReparseList routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

