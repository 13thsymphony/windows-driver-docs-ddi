---
UID: NF:hbaapi.HBA_GetFcpPersistentBinding
title: HBA_GetFcpPersistentBinding function
author: windows-driver-content
description: The HBA_GetFcpPersistentBinding routine retrieves the persistent bindings that are associated with the logical units that the HBA can enumerate.
old-location: storage\hba_getfcppersistentbinding.htm
old-project: storage
ms.assetid: a17a6dfa-c067-4a85-8787-ffb4fb6cb7ad
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_GetFcpPersistentBinding, HBA_GetFcpPersistentBinding routine [Storage Devices], fibreHBA_rtns_9ab54a28-f020-426e-9ea6-2aba3666884b.xml, hbaapi/HBA_GetFcpPersistentBinding, storage.hba_getfcppersistentbinding
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_GetFcpPersistentBinding
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---


# HBA_GetFcpPersistentBinding function
The <b>HBA_GetFcpPersistentBinding</b> routine retrieves the persistent bindings that are associated with the logical units that the HBA can enumerate.

## Syntax

````
HBA_STATUS HBA_API HBA_GetFcpPersistentBinding(
  _In_    HBA_HANDLE      Handle,
  _Inout_ PHBA_FCPBINDING Binding
);
````

## Parameters

`Handle`

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA to query for the bindings. The HBA returns bindings for the targets that it can enumerate.

`Binding`

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_fcpbinding.md">HBA_FCPBinding</a> that holds an array of elements of type <a href="..\hbaapi\ns-hbaapi-hba_fcpbindingentry.md">HBA_FCPBindingEntry</a>, each of which holds a persistent binding between operating system and fibre channel protocol (FCP) identifiers for a logical unit. On input, the <b>NumberOfEntries</b> member of HBA_FCPBinding should contain the number of bindings that fit in the output buffer. On output, <b>NumberOfEntries</b> holds the number of entries actually returned, which is equal to the number specified on input, or the full set of available bindings, whichever is smaller. The value in <b>NumberOfEntries</b> will contain the number of persistent bindings returned even when an error occurred because of insufficient buffer space.


## Return Value

The <b>HBA_GetFcpPersistentBinding</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetFcpPersistentBinding</b> returns one of the following qualifiers.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the persistent bindings were successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Returned if the adapter referenced by <i>HbaHandle </i>does not support persistent binding. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_MORE_DATA</b></dt>
</dl>
</td>
<td width="60%">
Returned if a larger buffer is required to contain binding information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the retrieval of the persistent bindings. 

</td>
</tr>
</table>

## Remarks

The <b>HBA_GetFcpPersistentBinding</b> routine retrieves a set of bindings between operating system and fibre channel protocol (FCP) identifiers for the logical units that it can enumerate. These bindings persist across reboots of the operating system.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** | Hbaapi.lib |
| **DLL** | Hbaapi.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



<a href="..\hbaapi\ns-hbaapi-hba_fcpbinding.md">HBA_FCPBinding</a>