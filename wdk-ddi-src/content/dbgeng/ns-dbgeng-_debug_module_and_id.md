---
UID : NS:dbgeng._DEBUG_MODULE_AND_ID
title : _DEBUG_MODULE_AND_ID
author : windows-driver-content
description : The DEBUG_MODULE_AND_ID structure describes a symbol within a module.
old-location : debugger\debug_module_and_id.htm
old-project : debugger
ms.assetid : d65ad0fa-1dd8-42b4-866b-cb2522080cde
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : dbgeng/PDEBUG_MODULE_AND_ID, debugger.debug_module_and_id, PDEBUG_MODULE_AND_ID structure pointer [Windows Debugging], DEBUG_MODULE_AND_ID structure [Windows Debugging], DEBUG_MODULE_AND_ID, Structures_d53c2a34-f855-45a0-918b-0a8dfb936828.xml, _DEBUG_MODULE_AND_ID, *PDEBUG_MODULE_AND_ID, PDEBUG_MODULE_AND_ID, dbgeng/DEBUG_MODULE_AND_ID
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dbgeng.h
req.include-header : DbgEng.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PDEBUG_MODULE_AND_ID, DEBUG_MODULE_AND_ID"
---

# _DEBUG_MODULE_AND_ID structure
The DEBUG_MODULE_AND_ID structure describes a symbol within a module.

## Syntax
````
typedef struct _DEBUG_MODULE_AND_ID {
  ULONG64 ModuleBase;
  ULONG64 Id;
}  DEBUG_MODULE_AND_ID, *PDEBUG_MODULE_AND_ID;
````

## Members


`Id`

The symbol ID of the symbol within the module.

`ModuleBase`

The location in the target's virtual address space of the module's base address.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include DbgEng.h) |