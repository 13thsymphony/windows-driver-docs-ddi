---
UID : NE:d3dkmdt._D3DKMDT_GTFCOMPLIANCE
title : _D3DKMDT_GTFCOMPLIANCE
author : windows-driver-content
description : The D3DKMDT_GTFCOMPLIANCE enumeration is reserved for system use. Do not use it in your driver.
old-location : display\d3dkmdt_gtfcompliance.htm
old-project : display
ms.assetid : f66bee69-206d-4e94-aca8-72f59569ab4a
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DKMDT_GTFCOMPLIANCE, D3DKMDT_GTFCOMPLIANCE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3dkmdt.h
req.include-header : D3dkmdt.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DKMDT_GTFCOMPLIANCE
req.alt-loc : d3dkmdt.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : D3DKMDT_GTFCOMPLIANCE
---

# _D3DKMDT_GTFCOMPLIANCE Enumeration
The D3DKMDT_GTFCOMPLIANCE enumeration is reserved for system use. Do not use it in your driver.

## Syntax
````
typedef enum _D3DKMDT_GTFCOMPLIANCE { 
  D3DKMDT_GTF_UNINITIALIZED  = 0,
  D3DKMDT_GTF_COMPLIANT      = 1,
  D3DKMDT_GTF_NOTCOMPLIANT   = 2
} D3DKMDT_GTFCOMPLIANCE;
````

## Constants

<table>

<tr>
<td>D3DKMDT_GTF_COMPLIANT</td>
<td></td>
</tr>

<tr>
<td>D3DKMDT_GTF_NOTCOMPLIANT</td>
<td></td>
</tr>

<tr>
<td>D3DKMDT_GTF_UNINITIALIZED</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |