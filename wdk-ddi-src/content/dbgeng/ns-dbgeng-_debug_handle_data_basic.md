---
UID: NS:dbgeng._DEBUG_HANDLE_DATA_BASIC
title: "_DEBUG_HANDLE_DATA_BASIC"
author: windows-driver-content
description: The DEBUG_HANDLE_DATA_BASIC structure contains handle-related information about a system object.
old-location: debugger\debug_handle_data_basic.htm
old-project: debugger
ms.assetid: c1ad22b9-9733-417a-96ae-bc5920462f4f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PDEBUG_HANDLE_DATA_BASIC, DEBUG_HANDLE_DATA_BASIC, DEBUG_HANDLE_DATA_BASIC structure [Windows Debugging], PDEBUG_HANDLE_DATA_BASIC, PDEBUG_HANDLE_DATA_BASIC structure pointer [Windows Debugging], Structures_e4fb66c0-8e88-4f35-a103-0cc0f7cc1bfd.xml, _DEBUG_HANDLE_DATA_BASIC, dbgeng/DEBUG_HANDLE_DATA_BASIC, dbgeng/PDEBUG_HANDLE_DATA_BASIC, debugger.debug_handle_data_basic"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	DbgEng.h
api_name:
-	DEBUG_HANDLE_DATA_BASIC
product: Windows
targetos: Windows
req.typenames: DEBUG_HANDLE_DATA_BASIC, *PDEBUG_HANDLE_DATA_BASIC
---

# _DEBUG_HANDLE_DATA_BASIC structure
The DEBUG_HANDLE_DATA_BASIC structure contains handle-related information about a system object.

## Syntax
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

## Members


`Attributes`

A bit-set that contains the handle's attributes.  For possible values, see "Handle" in the Windows Driver Kit (WDK).

`GrantedAccess`

A bit-set that specifies the access mask for the object that is represented by the handle.  For details, see ACCESS_MASK in the Platform SDK documentation.

`HandleCount`

The number of handle references for the object.

`ObjectNameSize`

The size, in characters, of the object's name.

`PointerCount`

The number of pointer references for the object.

`TypeNameSize`

The size, in characters, of the object-type name.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | dbgeng.h (include DbgEng.h) |