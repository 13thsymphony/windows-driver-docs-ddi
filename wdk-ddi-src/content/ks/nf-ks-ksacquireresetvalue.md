---
UID: NF:ks.KsAcquireResetValue
title: KsAcquireResetValue function
author: windows-driver-content
description: The KsAcquireResetValue function retrieves the current reset state from an IOCTL_KS_RESET_STATE IRP.
old-location: stream\ksacquireresetvalue.htm
old-project: stream
ms.assetid: 80a990e3-3637-4837-8800-42d5848e01cf
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsAcquireResetValue
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
req.alt-api: KsAcquireResetValue
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
req.typenames: 
---

# KsAcquireResetValue function



## -description
The <b>KsAcquireResetValue </b>function retrieves the current reset state from an IOCTL_KS_RESET_STATE IRP.



## -syntax

````
NTSTATUS KsAcquireResetValue(
  _In_  PIRP    Irp,
  _Out_ KSRESET *ResetValue
);
````


## -parameters

### -param Irp [in]

Points to the IRP from which to retrieve the reset state.


### -param ResetValue [out]

Points to a caller-allocated buffer, that on successful completion contains the reset value (KSRESET_BEGIN, KSRESET_END) associated with the IRP.


## -returns
The <b>KsAcquireResetValue </b>function returns STATUS_SUCCESS if the reset value was obtained.


## -remarks


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