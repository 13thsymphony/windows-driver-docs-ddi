---
UID: NS.ISCSIOP._SETGROUPPRESHAREDKEY_IN
title: _SetGroupPresharedKey_IN
author: windows-driver-content
description: The SetGroupPresharedKey_IN structure holds the input data for the SetGroupPresharedKey method.
old-location: storage\setgrouppresharedkey_in.htm
old-project: storage
ms.assetid: fe5e1f75-ebd0-4856-bb77-14efb52fbce0
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _SetGroupPresharedKey_IN, SetGroupPresharedKey_IN, *PSetGroupPresharedKey_IN
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
req.alt-api: SetGroupPresharedKey_IN
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

# _SetGroupPresharedKey_IN structure



## -description
The SetGroupPresharedKey_IN structure holds the input data for the <a href="storage.setgrouppresharedkey">SetGroupPresharedKey</a> method.


## -syntax

````
typedef struct _SetGroupPresharedKey_IN {
  ULONG KeySize;
  UCHAR Key[1];
} SetGroupPresharedKey_IN, *PSetGroupPresharedKey_IN;
````


## -struct-fields

### -field KeySize

The size, in bytes, of the key in <b>Key</b><i>.</i>

### -field Key

The preshared group key<i>.</i>

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
<a href="storage.setgrouppresharedkey">SetGroupPresharedKey</a>
</dt>
<dt>
<a href="storage.setgrouppresharedkey_out">SetGroupPresharedKey_OUT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetGroupPresharedKey_IN structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
