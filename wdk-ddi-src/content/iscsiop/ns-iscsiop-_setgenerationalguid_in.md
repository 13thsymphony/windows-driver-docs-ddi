---
UID: NS.ISCSIOP._SETGENERATIONALGUID_IN
title: _SetGenerationalGuid_IN
author: windows-driver-content
description: The SetGenerationalGuid_IN structure holds the input data for the SetGenerationalGuid method.
old-location: storage\setgenerationalguid_in.htm
old-project: storage
ms.assetid: 24568c37-9641-4e3e-b788-f71db4f3f70f
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _SetGenerationalGuid_IN, SetGenerationalGuid_IN, *PSetGenerationalGuid_IN
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
req.alt-api: SetGenerationalGuid_IN
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

# _SetGenerationalGuid_IN structure



## -description
The SetGenerationalGuid_IN structure holds the input data for the <a href="storage.setgenerationalguid">SetGenerationalGuid</a> method.


## -syntax

````
typedef struct _SetGenerationalGuid_IN {
  UCHAR GenerationalGuid[16];
} SetGenerationalGuid_IN, *PSetGenerationalGuid_IN;
````


## -struct-fields

### -field GenerationalGuid

A 16-byte GUID that identifies the version of the information that is currently in the initiator cache. 

## -remarks
You must implement this method.

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
<a href="storage.setgenerationalguid">SetGenerationalGuid</a>
</dt>
<dt>
<a href="storage.setgenerationalguid_out">SetGenerationalGuid_OUT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetGenerationalGuid_IN structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
