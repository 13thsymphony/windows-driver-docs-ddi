---
UID: NS.ISCSIOP._REMOVECONNECTIONFROMSESSION_IN
title: _RemoveConnectionFromSession_IN
author: windows-driver-content
description: The RemoveConnectionFromSession_IN structure holds the input data for the RemoveConnectionFromSession method, which is used to remove a connection from a session.
old-location: storage\removeconnectionfromsession_in.htm
old-project: storage
ms.assetid: dd5fd1f2-7040-40ee-bf9c-42e77c9738da
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _RemoveConnectionFromSession_IN, PRemoveConnectionFromSession_IN, RemoveConnectionFromSession_IN, *PRemoveConnectionFromSession_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RemoveConnectionFromSession_IN
req.alt-loc: iscsiop.h
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

# _RemoveConnectionFromSession_IN structure



## -description
The RemoveConnectionFromSession_IN structure holds the input data for the <a href="storage.removeconnectionfromsession">RemoveConnectionFromSession</a> method, which is used to remove a connection from a session.



## -syntax

````
typedef struct _RemoveConnectionFromSession_IN {
  ULONGLONG UniqueSessionId;
  ULONGLONG UniqueConnectionId;
} RemoveConnectionFromSession_IN, *PRemoveConnectionFromSession_IN;
````


## -struct-fields

### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="storage.logintotarget">LoginToTarget</a> and <a href="storage.addconnectiontosession">AddConnectionToSession</a> methods both return this value in their <i>UniqueSessionId</i> parameter. Do not confuse this value with the values in the ISID and TSID members.


### -field UniqueConnectionId

A 64-bit integer that uniquely identifies the connection. Do not confuse this value with the connection ID (CID).


## -remarks
You must implement this class.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iscsiop.h (include Iscsiop.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.addconnectiontosession">AddConnectionToSession</a>
</dt>
<dt>
<a href="storage.logintotarget">LoginToTarget</a>
</dt>
<dt>
<a href="storage.removeconnectionfromsession">RemoveConnectionFromSession</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemoveConnectionFromSession_IN structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

