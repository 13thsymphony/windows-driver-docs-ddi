---
UID: NS:mpiowmi._DSM_PARAMETERS
title: _DSM_PARAMETERS
author: windows-driver-content
description: The DSM_PARAMETERS structure holds the DSM version and timer counters information.
old-location: storage\dsm_parameters.htm
old-project: storage
ms.assetid: 948331f1-1398-4e6e-85cb-27bbbd79630e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DSM_PARAMETERS, DSM_PARAMETERS, *PDSM_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DSM_PARAMETERS
req.alt-loc: mpiowmi.h
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
req.typenames: DSM_PARAMETERS, *PDSM_PARAMETERS
---

# _DSM_PARAMETERS structure



## -description
The DSM_PARAMETERS structure holds the DSM version and timer counters information.



## -syntax

````
typedef struct _DSM_PARAMETERS {
  WCHAR        DsmName[63 + 1];
  ULONGLONG    DsmContext;
  DSM_VERSION  DsmVersion;
  DSM_COUNTERS DsmCounters;
} DSM_PARAMETERS, *PDSM_PARAMETERS;
````


## -struct-fields

### -field DsmName

A string field of maximum length 63 characters that returns the friendly name of the DSM.


### -field DsmContext

An unsigned 64-bitfield that represents a unique identifier as used by MPIO to address a particular DSM.


### -field DsmVersion

A field that contains an instance of the DSM_VERSION structure with version information for the DSM.


### -field DsmCounters

A field that contains an instance of the DSM_COUNTERS structure with timer counters information that is specific to the particular DSM.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Mpiowmi.h (include Mpiowmi.h)</dt>
</dl>
</td>
</tr>
</table>