---
UID: NF.ks.KsDispatchFastReadFailure
title: KsDispatchFastReadFailure function
author: windows-driver-content
description: The KsDispatchFastReadFailure function is used in a KSDISPATCH_TABLE.FastRead entry when fast I/O read is not handled. The function should always return FALSE.
old-location: stream\ksdispatchfastreadfailure.htm
old-project: stream
ms.assetid: 7e0c72ce-0959-4835-ac1a-3f37869cc81f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsDispatchFastReadFailure
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsDispatchFastReadFailure
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
---

# KsDispatchFastReadFailure function



## -description
The <b>KsDispatchFastReadFailure</b> function is used in a KSDISPATCH_TABLE.FastRead entry when fast I/O read is not handled. The function should always return <b>FALSE</b>.


## -syntax

````
BOOLEAN KsDispatchFastReadFailure(
  _In_  PFILE_OBJECT     FileObject,
  _In_  PLARGE_INTEGER   FileOffset,
  _In_  ULONG            Length,
  _In_  BOOLEAN          Wait,
  _In_  ULONG            LockKey,
  _Out_ PVOID            Buffer,
  _Out_ PIO_STATUS_BLOCK IoStatus,
  _In_  PDEVICE_OBJECT   DeviceObject
);
````


## -parameters

### -param FileObject [in]

Not used.

### -param FileOffset [in]

Not used.

### -param Length [in]

Not used.

### -param Wait [in]

Not used.

### -param LockKey [in]

Not used.

### -param Buffer [out]

Not used.

### -param IoStatus [out]

Not used.

### -param DeviceObject [in]

Not used.

## -returns
The <b>KsDispatchFastReadFailure</b> function returns <b>FALSE</b>.

## -remarks
The <b>KsDispatchFastReadFailure</b> function is needed since the dispatch table for a particular opened instance of a device may not handle a specific major function that another opened instance needs to handle. Therefore, the function pointer in the driver object must always point to a function, such as the <b>KsDispatchFastReadFailure</b> function, that calls a dispatch table entry.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>