---
UID: NF:ntddk.PsGetJobSilo
title: PsGetJobSilo function
author: windows-driver-content
description: This routine returns the first job in the hierarchy that is a Silo. The returned pointer is valid as long as the supplied Job object remains referenced.
old-location: kernel\psgetjobsilo.htm
old-project: kernel
ms.assetid: 1032282B-7CA3-4162-8FC2-1A4A683E9DEF
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/PsGetJobSilo, kernel.psgetjobsilo, PsGetJobSilo, PsGetJobSilo routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PsGetJobSilo
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsGetJobSilo function
This routine returns the first job in the hierarchy that is a <i>Silo</i>.  The returned pointer is valid as long as the supplied <i>Job</i> object remains referenced.


<div class="alert"><b>Note</b>  This returns both app silos and server silos, whichever is first.</div>
<div> </div>

## Syntax

````
NTSTATUS PsGetJobSilo(
  _In_  PEJOB  Job,
  _Out_ PESILO *Silo
);
````

## Parameters

`Job`

A job object.

`Silo`

A pointer that receives the silo for the job.


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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>Job</i> parameter is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_JOB_NO_CONTAINER</b></dt>
</dl>
</td>
<td width="60%">
No silo is present.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
A PESILO is returned successfully.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows 10, version 1607 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |
| **Library** | NtosKrnl.exe |