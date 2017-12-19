---
UID: NF.printoem.OEMIcmDeleteColorTransform
title: OEMIcmDeleteColorTransform function
author: windows-driver-content
description: The OEMIcmDeleteColorTransform function deletes the specified color transform.
old-location: print\oemicmdeletecolortransform.htm
old-project: print
ms.assetid: 820d9e28-fe06-4aa7-91d8-a90340affb94
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: OEMIcmDeleteColorTransform
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OEMIcmDeleteColorTransform
req.alt-loc: printoem.h
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

# OEMIcmDeleteColorTransform function



## -description
The <code>OEMIcmDeleteColorTransform</code> function deletes the specified color transform.



## -syntax

````
BOOL APIENTRY OEMIcmDeleteColorTransform(
   DHPDEV dhpdev,
   HANDLE hcmXform
);
````


## -parameters

### -param dhpdev 


### -param hcmXform 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Printoem.h (include Printoem.h)</dt>
</dl>
</td>
</tr>
</table>