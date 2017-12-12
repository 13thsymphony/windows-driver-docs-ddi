---
UID: NE.storport._STOR_EVENT_ASSOCIATION_ENUM
title: _STOR_EVENT_ASSOCIATION_ENUM
author: windows-driver-content
description: The STOR_EVENT_ASSOCIATION_ENUM enumerator specifies the type of device that is associated with an event.
old-location: storage\stor_event_association_enum.htm
old-project: storage
ms.assetid: 2e0672b6-e692-43c8-8a20-7947c854c4c9
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _STOR_EVENT_ASSOCIATION_ENUM, STOR_EVENT_ASSOCIATION_ENUM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STOR_EVENT_ASSOCIATION_ENUM
req.alt-loc: storport.h
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

# _STOR_EVENT_ASSOCIATION_ENUM enumeration



## -description
The STOR_EVENT_ASSOCIATION_ENUM enumerator specifies the type of device that is associated with an event.



## -syntax

````
typedef enum _STOR_EVENT_ASSOCIATION_ENUM { 
  StorEventAdapterAssociation  = 0,
  StorEventLunAssociation      = 1,
  StorEventTargetAssociation   = 2,
  StorEventInvalidAssociation  = 3
} STOR_EVENT_ASSOCIATION_ENUM;
````


## -enum-fields

### -field StorEventAdapterAssociation

The event is associated with the adapter.


### -field StorEventLunAssociation

The event is associated with the LUN.


### -field StorEventTargetAssociation

The event is associated with the target.


### -field StorEventInvalidAssociation

Marks end of valid enumeration range


## -remarks


## -requirements
<table>
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
</table>