---
UID: NS.1394._SET_LOCAL_HOST_PROPS2
title: _SET_LOCAL_HOST_PROPS2
author: windows-driver-content
description: SET_LOCAL_HOST_PROPS2 sets a lower bound on the value the bus will use for its gap count.
old-location: ieee\set_local_host_props2.htm
old-project: IEEE
ms.assetid: ec4b8630-500d-494a-9a86-2f9cf9f9227b
ms.author: windowsdriverdev
ms.date: 11/29/2017
ms.keywords: _SET_LOCAL_HOST_PROPS2, SET_LOCAL_HOST_PROPS2, *PSET_LOCAL_HOST_PROPS2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SET_LOCAL_HOST_PROPS2
req.alt-loc: 1394.h
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
---

# _SET_LOCAL_HOST_PROPS2 structure



## -description
SET_LOCAL_HOST_PROPS2 sets a lower bound on the value the bus will use for its gap count. 



## -syntax

````
typedef struct _SET_LOCAL_HOST_PROPS2 {
  ULONG GapCountLowerBound;
} SET_LOCAL_HOST_PROPS2, *PSET_LOCAL_HOST_PROPS2;
````


## -struct-fields

### -field GapCountLowerBound

Specifies lower bound of the gap count.


## -remarks
See the <a href="http://go.microsoft.com/fwlink/p/?linkid=8729">IEEE 1394 Trade Association specification</a> website for a description of the gap count. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>1394.h (include 1394.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537663">REQUEST_SET_LOCAL_HOST_PROPERTIES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20SET_LOCAL_HOST_PROPS2 structure%20 RELEASE:%20(11/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

