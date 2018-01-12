---
UID: NF:ndis.NdisGetSystemUpTimeEx
title: NdisGetSystemUpTimeEx function
author: windows-driver-content
description: The NdisGetSystemUpTimeEx function returns the number of milliseconds that have elapsed since the computer was restarted.
old-location: netvista\ndisgetsystemuptimeex.htm
old-project: netvista
ms.assetid: a52087b5-81de-4945-9d1e-bea67915ced4
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisGetSystemUpTimeEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisGetSystemUpTimeEx
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisGetSystemUpTimeEx function



## -description
The 
  <b>NdisGetSystemUpTimeEx</b> function returns the number of milliseconds that have elapsed since the
  computer was restarted.



## -syntax

````
VOID NdisGetSystemUpTimeEx(
  _Out_ PLARGE_INTEGER pSystemUpTime
);
````


## -parameters

### -param pSystemUpTime [out]

A pointer to a caller-supplied LARGE_INTEGER variable in which this function returns the time, in
     milliseconds, since the computer was last restarted.


## -returns
None


## -remarks
NDIS drivers should call the 
    <b>NdisGetSystemUpTimeEx</b> function instead of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552110">NdisGetSystemUpTime</a> function.


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
Version

</th>
<td width="70%">
Supported in NDIS 6.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552110">NdisGetSystemUpTime</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetSystemUpTimeEx function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

