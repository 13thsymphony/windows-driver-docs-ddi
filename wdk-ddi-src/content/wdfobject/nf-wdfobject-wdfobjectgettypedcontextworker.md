---
UID: NF.wdfobject.WdfObjectGetTypedContextWorker
title: WdfObjectGetTypedContextWorker function
author: windows-driver-content
description: The WdfObjectGetTypedContextWorker method is reserved for internal use only. Use the WdfObjectGetTypedContext macro instead.
old-location: wdf\wdfobjectgettypedcontextworker.htm
old-project: wdf
ms.assetid: 1d95084b-16c4-468e-84af-47650292c5a1
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WdfObjectGetTypedContextWorker
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfobject.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WdfObjectGetTypedContextWorker
req.alt-loc: wdfobject.h
req.ddi-compliance: DriverCreate
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

# WdfObjectGetTypedContextWorker function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfObjectGetTypedContextWorker</b> method is reserved for internal use only. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548749">WdfObjectGetTypedContext</a> macro instead.



## -syntax

````
PVOID WdfObjectGetTypedContextWorker(
  _In_ WDFOBJECT                      Handle,
  _In_ PCWDF_OBJECT_CONTEXT_TYPE_INFO TypeInfo
);
````


## -parameters

### -param Handle [in]


### -param TypeInfo [in]


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfobject.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>
</td>
</tr>
</table>