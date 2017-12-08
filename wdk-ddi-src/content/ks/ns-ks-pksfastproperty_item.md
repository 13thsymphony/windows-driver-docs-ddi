---
UID: NS.KS.PKSFASTPROPERTY_ITEM
title: PKSFASTPROPERTY_ITEM
author: windows-driver-content
description: The KSFASTPROPERTY_ITEM structure is used with items for fast I/O dispatching.
old-location: stream\ksfastproperty_item.htm
old-project: stream
ms.assetid: 8a39b7cb-cd05-4fb8-9e50-7425e689a36f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSFASTPROPERTY_ITEM, KSFASTPROPERTY_ITEM, *PKSFASTPROPERTY_ITEM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSFASTPROPERTY_ITEM
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

# PKSFASTPROPERTY_ITEM structure



## -description
The KSFASTPROPERTY_ITEM structure is used with items for fast I/O dispatching.


## -syntax

````
typedef struct {
  ULONG PropertyId;
  union {
    PFNKSFASTHANDLER GetPropertyHandler;
    BOOLEAN          GetSupported;
  };
  union {
    PFNKSFASTHANDLER SetPropertyHandler;
    BOOLEAN          SetSupported;
  };
  ULONG Reserved;
} KSFASTPROPERTY_ITEM, *PKSFASTPROPERTY_ITEM;
````


## -struct-fields

### -field PropertyId

Specifies the identifier of the specific property within the set.

### -field GetPropertyHandler

Points to a driver-supplied <a href="stream.kstrfasthandler">KStrFastHandler</a> routine that specifies the fast handler for retrieving the property. If this is <b>NULL</b>, the property cannot be read with a fast handler.

### -field GetSupported

A boolean value that indicates if the driver has supplied a get property handler.

### -field SetPropertyHandler

Points to a driver-supplied <a href="stream.kstrfasthandler">KStrFastHandler</a> routine that specifies the fast handler for setting the property. If this is <b>NULL</b>, the property cannot be set with a fast handler.

### -field SetSupported

A boolean value that indicates if the driver has supplied a set property handler.

### -field Reserved

Reserved and set to zero.

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
<a href="stream.kstrfasthandler">KStrFastHandler</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSFASTPROPERTY_ITEM structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
