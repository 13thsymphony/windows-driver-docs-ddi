---
UID: NS:minitape._TAPE_INIT_DATA
title: "_TAPE_INIT_DATA"
author: windows-driver-content
description: TAPE_INIT_DATA is used only by legacy tape miniclass drivers. Use TAPE_INIT_DATA_EX instead.
old-location: storage\tape_init_data.htm
old-project: storage
ms.assetid: 11f5201b-ddd3-43ad-9746-a1a9885c99b1
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: TAPE_INIT_DATA structure [Storage Devices], TAPE_INIT_DATA, *PTAPE_INIT_DATA, minitape/TAPE_INIT_DATA, _TAPE_INIT_DATA, storage.tape_init_data, structs-tape_53b2f7ff-8718-4ac7-9a02-9c2f066b6884.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Minitape.h
apiname:
-	TAPE_INIT_DATA
product: Windows
targetos: Windows
req.typenames: TAPE_INIT_DATA, *PTAPE_INIT_DATA
---

# _TAPE_INIT_DATA structure
TAPE_INIT_DATA is used only by legacy tape miniclass drivers. Use <a href="..\minitape\ns-minitape-_tape_init_data_ex.md">TAPE_INIT_DATA_EX</a> instead.

## Syntax


## Members


## Remarks
TAPE_INIT_DATA is defined as follows.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _TAPE_INIT_DATA { 
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
} TAPE_INIT_DATA, *PTAPE_INIT_DATA;</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | minitape.h (include Minitape.h) |