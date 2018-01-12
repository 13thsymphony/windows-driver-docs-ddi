---
UID: NS:dbgeng._DEBUG_HANDLE_DATA_BASIC
title: _DEBUG_HANDLE_DATA_BASIC
author: windows-driver-content
description: The DEBUG_HANDLE_DATA_BASIC structure contains handle-related information about a system object.
old-location: debugger\debug_handle_data_basic.htm
old-project: debugger
ms.assetid: c1ad22b9-9733-417a-96ae-bc5920462f4f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DEBUG_HANDLE_DATA_BASIC, DEBUG_HANDLE_DATA_BASIC, *PDEBUG_HANDLE_DATA_BASIC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEBUG_HANDLE_DATA_BASIC
req.alt-loc: DbgEng.h
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
req.typenames: DEBUG_HANDLE_DATA_BASIC, *PDEBUG_HANDLE_DATA_BASIC
---

# _DEBUG_HANDLE_DATA_BASIC structure



## -description
The DEBUG_HANDLE_DATA_BASIC structure contains handle-related information about a system object.



## -syntax

````
typedef struct _DEBUG_HANDLE_DATA_BASIC {
  ULONG TypeNameSize;
  ULONG ObjectNameSize;
  ULONG Attributes;
  ULONG GrantedAccess;
  ULONG HandleCount;
  ULONG PointerCount;
} DEBUG_HANDLE_DATA_BASIC, *PDEBUG_HANDLE_DATA_BASIC;
````


## -struct-fields

### -field TypeNameSize

The size, in characters, of the object-type name.


### -field ObjectNameSize

The size, in characters, of the object's name.


### -field Attributes

A bit-set that contains the handle's attributes.  For possible values, see "Handle" in the Windows Driver Kit (WDK).


### -field GrantedAccess

A bit-set that specifies the access mask for the object that is represented by the handle.  For details, see ACCESS_MASK in the Platform SDK documentation.


### -field HandleCount

The number of handle references for the object.


### -field PointerCount

The number of pointer references for the object.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>DbgEng.h (include DbgEng.h)</dt>
</dl>
</td>
</tr>
</table>