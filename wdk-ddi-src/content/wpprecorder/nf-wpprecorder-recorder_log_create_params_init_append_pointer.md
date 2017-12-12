---
UID: NF.wpprecorder.RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER
title: RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER function
author: windows-driver-content
description: The RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER method initializes the RECORDER_LOG_CREATE_PARAMS with the pointer to link logs.
old-location: devtest\recorder_log_create_params_init_append_pointer.htm
old-project: devtest
ms.assetid: EC94E27C-C863-49F0-B13C-B661E96991B7
ms.author: windowsdriverdev
ms.date: 11/21/2017
ms.keywords: RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wpprecorder.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER
req.alt-loc: wpprecorder.h
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

# RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER function



## -description
The <b>RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER</b> method initializes the <a href="devtest.recorder_log_create_params">RECORDER_LOG_CREATE_PARAMS</a> with the pointer to link logs.



## -syntax

````
FORCEINLINE void RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER(
  _Out_    PRECORDER_LOG_CREATE_PARAMS Params,
  _In_opt_ PSTR                        LogIdentifier,
  _In_     PVOID                       LogIdentifierAppendPointer
);
````


## -parameters

### -param Params [out]

A pointer to a <a href="devtest.recorder_log_create_params">RECORDER_LOG_CREATE_PARAMS</a> structure.


### -param LogIdentifier [in, optional]

String identifier for the log.


### -param LogIdentifierAppendPointer [in]

A pointer from each debug message to its IFR’s metadata structure.


## -returns
This function does not return a value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wpprecorder.h</dt>
</dl>
</td>
</tr>
</table>