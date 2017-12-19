---
UID: NS.WINSPLP.BRANCHOFFICEJOBDATAPRINTED
title: BranchOfficeJobDataPrinted
author: windows-driver-content
description: Contains the necessary data for logging a branch office job completed event on a remote server. This is based on standard job-related data available to the spooler.
old-location: print\branchofficejobdataprinted.htm
old-project: print
ms.assetid: 77737A33-9592-43A3-B12A-5BFDCA0209BE
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: BranchOfficeJobDataPrinted, PBranchOfficeJobDataPrinted, BranchOfficeJobDataPrinted, *PBranchOfficeJobDataPrinted
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BranchOfficeJobDataPrinted
req.alt-loc: Winsplp.h
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
req.product: Windows 10 or later.
---

# BranchOfficeJobDataPrinted structure



## -description
Contains the necessary data for logging a branch office job completed event on a remote server. This is based on standard job-related data available to the spooler.



## -syntax

````
typedef struct {
  DWORD    Status;
  LPWSTR   pDocumentName;
  LPWSTR   pUserName;
  LPWSTR   pMachineName;
  LPWSTR   pPrinterName;
  LPWSTR   pPortName;
  LONGLONG Size;
  DWORD    TotalPages;
} BranchOfficeJobDataPrinted, *PBranchOfficeJobDataPrinted;
````


## -struct-fields

### -field Status

Specifies the current status, or the failure code for a JOB_ERROR event.


### -field pDocumentName

Specifies the name of the printed document.


### -field pUserName

Specifies the user who submitted the job.


### -field pMachineName

Specifies the name of the client machine printing the job


### -field pPrinterName

Specifies the name of the print connection.


### -field pPortName

Specifies the name of the port the job printed on.


### -field Size

Specifies the 64-bit size of the job.


### -field TotalPages

Specifies the total number of pages in the job.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Winsplp.h</dt>
</dl>
</td>
</tr>
</table>