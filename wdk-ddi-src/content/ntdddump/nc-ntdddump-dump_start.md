---
UID: NC.ntdddump.DUMP_START
title: DUMP_START
author: windows-driver-content
description: The Dump_Start callback routine is called after initializing the dump driver and just before starting the dump write process.
old-location: storage\dump_start.htm
old-project: storage
ms.assetid: a315f51f-069a-4c3d-bedc-2378b0996022
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _VERIFY_INFORMATION, *PVERIFY_INFORMATION, VERIFY_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntdddump.h
req.include-header: Ntdddump.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Vista and Windows Server 2008.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dump_Start
req.alt-loc: ntdddump.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# DUMP_START callback



## -description
The <i>Dump_Start</i> callback routine is called after initializing the dump driver and just before starting the dump write process.



## -prototype

````
PDUMP_START Dump_Start;

NTSTATUS Dump_Start(
  _In_ PFILTER_EXTENSION FilterExtension
)
{ ... }
````


## -parameters

### -param FilterExtension [in]

A pointer to a <a href="storage.filter_extension">FILTER_EXTENSION</a> structure.


## -returns
If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values that are defined in <i>Ntstatus.h</i>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows Vista and Windows Server 2008.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntdddump.h (include Ntdddump.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.filter_extension">FILTER_EXTENSION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20Dump_Start routine%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

