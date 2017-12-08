---
UID: NS.mpiodisk._MPIO_DSM_Path
title: MPIO_DSM_Path
author: windows-driver-content
description: The MPIO_DSM_Path structure is used to represent the DSM's definition of a path.
old-location: storage\mpio_dsm_path.htm
old-project: storage
ms.assetid: 17338526-d682-4d11-89b9-730b1a275870
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: MPIO_DSM_Path, MPIO_DSM_Path, *PMPIO_DSM_Path
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiodisk.h
req.include-header: Mpiowmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MPIO_DSM_Path
req.alt-loc: mpiodisk.h
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

# MPIO_DSM_Path structure



## -description
<p>The MPIO_DSM_Path structure is used to represent the DSM's definition of a path.</p>


## -syntax

````
typedef struct _MPIO_DSM_Path {
  ULONGLONG DsmPathId;
  ULONGLONG Reserved;
  ULONG     PathWeight;
  ULONG     PrimaryPath;
} MPIO_DSM_Path, *PMPIO_DSM_Path;
````


## -struct-fields
<dl>

### -field DsmPathId

<dd>
<p>An unsigned 64-bitfield that is used as a unique identifier to distinguish paths that are known to the DSM.</p>
</dd>

### -field Reserved

<dd>
<p>Should be zero.</p>
</dd>

### -field PathWeight

<dd>
<p>An unsigned 32-bitfield that holds the weight associated with the given path. The assigned value determines the order in which the DSM will pick the paths if the load balance policy is set to Weighted Path. This means that a user can assign weights to each path that is available for a device and if the Load Balance Policy for the device is set as "Weighted Path," MPIO uses this PathWeight value to determine which path to use.</p>
</dd>

### -field PrimaryPath

<dd>
<p>An unsigned 32-bitfield that is used as a flag to indicate the path state when accessing a particular LUN.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Mpiodisk.h (include Mpiowmi.h)</dt>
</dl>
</td>
</tr>
</table>