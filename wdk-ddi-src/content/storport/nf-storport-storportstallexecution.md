---
UID: NF.storport.StorPortStallExecution
title: StorPortStallExecution function
author: windows-driver-content
description: The StorPortStallExecution routine stalls the miniport driver.
old-location: storage\storportstallexecution.htm
old-project: storage
ms.assetid: d635d93b-3e69-4ce5-9dc0-60186417d009
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: StorPortStallExecution
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortStallExecution
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: SpNoWait
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# StorPortStallExecution function



## -description
The <b>StorPortStallExecution</b> routine stalls the miniport driver. 



## -syntax

````
STORPORT_API VOID StorPortStallExecution(
  _In_ ULONG Delay
);
````


## -parameters

### -param Delay [in]

Specifies the delay interval, in microseconds. The given value must be less than a full millisecond. 


## -returns
None 


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
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Storport.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.storport_spnowait">SpNoWait</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.scsiportstallexecution">ScsiPortStallExecution</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortStallExecution routine%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

