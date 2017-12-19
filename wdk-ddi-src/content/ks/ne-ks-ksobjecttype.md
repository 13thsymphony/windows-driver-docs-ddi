---
UID: NE.ks.KSOBJECTTYPE
title: KSOBJECTTYPE
author: windows-driver-content
description: The KSOBJECTTYPE enumeration lists different types of kernel streaming objects.
old-location: stream\ksobjecttype.htm
old-project: stream
ms.assetid: ab30d24f-4f14-4a84-a6e1-1a2506b4ba87
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KSOBJECTTYPE, KSOBJECTTYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSOBJECTTYPE
req.alt-loc: ks.h
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

# KSOBJECTTYPE enumeration



## -description
The KSOBJECTTYPE enumeration lists different types of kernel streaming objects.



## -syntax

````
typedef enum  { 
  KsObjectTypeDevice         = 0,
  KsObjectTypeFilterFactory  = 1,
  KsObjectTypeFilter         = 2,
  KsObjectTypePin            = 3
} KSOBJECTTYPE;
````


## -enum-fields

### -field KsObjectTypeDevice

Specifies that the object is a device.


### -field KsObjectTypeFilterFactory

Specifies that the object is a filter factory.


### -field KsObjectTypeFilter

Specifies that the object is a filter.


### -field KsObjectTypePin

Specifies that the object is a pin.


## -remarks


## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksgetobjecttypefromfileobject">KsGetObjectTypeFromFileObject</a>
</dt>
<dt>
<a href="stream.ksgetobjectfromfileobject">KsGetObjectFromFileObject</a>
</dt>
<dt>
<a href="stream.ksgetfilterfromfileobject">KsGetFilterFromFileObject</a>
</dt>
<dt>
<a href="stream.ksgetpinfromfileobject">KsGetPinFromFileObject</a>
</dt>
<dt>
<a href="stream.kspingetconnectedpinfileobject">KsPinGetConnectedPinFileObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSOBJECTTYPE enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

