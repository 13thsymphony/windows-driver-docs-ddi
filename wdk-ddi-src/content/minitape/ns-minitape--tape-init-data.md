---
UID: NS.minitape._TAPE_INIT_DATA
title: TAPE_INIT_DATA
author: windows-driver-content
description: TAPE_INIT_DATA is used only by legacy tape miniclass drivers. Use TAPE_INIT_DATA_EX instead.
old-location: storage\tape_init_data.htm
old-project: storage
ms.assetid: 11f5201b-ddd3-43ad-9746-a1a9885c99b1
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: TAPE_INIT_DATA, TAPE_INIT_DATA, *PTAPE_INIT_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: minitape.h
req.include-header: Minitape.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TAPE_INIT_DATA
req.alt-loc: Minitape.h
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
req.iface: 
---

# TAPE_INIT_DATA structure



## -description
<p>TAPE_INIT_DATA is used only by legacy tape miniclass drivers. Use <a href="..\minitape\ns-minitape--tape-init-data-ex.md">TAPE_INIT_DATA_EX</a> instead. </p>


## -syntax

````
typedef struct _TAPE_INIT_DATA { 
  TAPE_VERIFY_INQUIRY_ROUTINE     VerifyInquiry;   
  BOOLEAN                         QueryModeCapabilitiesPage; 
  ULONG                           MinitapeExtensionSize; 
  TAPE_EXTENSION_INIT_ROUTINE     ExtensionInit;          /* OPTIONAL */
  ULONG                           DefaultTimeOutValue;    /* OPTIONAL */
  TAPE_ERROR_ROUTINE              TapeError;              /* OPTIONAL */
  ULONG                           CommandExtensionSize; 
  TAPE_PROCESS_COMMAND_ROUTINE    CreatePartition; 
  TAPE_PROCESS_COMMAND_ROUTINE    Erase; 
  TAPE_PROCESS_COMMAND_ROUTINE    GetDriveParameters; 
  TAPE_PROCESS_COMMAND_ROUTINE    GetMediaParameters; 
  TAPE_PROCESS_COMMAND_ROUTINE    GetPosition; 
  TAPE_PROCESS_COMMAND_ROUTINE    GetStatus; 
  TAPE_PROCESS_COMMAND_ROUTINE    Prepare; 
  TAPE_PROCESS_COMMAND_ROUTINE    SetDriveParameters; 
  TAPE_PROCESS_COMMAND_ROUTINE    SetMediaParameters; 
  TAPE_PROCESS_COMMAND_ROUTINE    SetPosition; 
  TAPE_PROCESS_COMMAND_ROUTINE    WriteMarks; 
  TAPE_PROCESS_COMMAND_ROUTINE    PreProcessReadWrite; 
} TAPE_INIT_DATA, *PTAPE_INIT_DATA;
````


## -struct-fields


## -remarks
<p>TAPE_INIT_DATA is defined as follows.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Minitape.h (include Minitape.h)</dt>
</dl>
</td>
</tr>
</table>