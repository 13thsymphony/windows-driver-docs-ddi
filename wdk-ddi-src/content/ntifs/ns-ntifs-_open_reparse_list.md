---
UID: NS:ntifs._OPEN_REPARSE_LIST
title: "_OPEN_REPARSE_LIST"
author: windows-driver-content
description: Points to a list of OPEN_REPARSE_LIST_ENTRY structures that specify the tag and possibly GUID that should be opened directly without returning STATUS_REPARSE.
old-location: ifsk\open_reparse_list.htm
old-project: ifsk
ms.assetid: 2477F904-A470-4FB0-83D8-0264A4838C12
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: OPEN_REPARSE_LIST, POPEN_REPARSE_LIST structure pointer [Installable File System Drivers], _OPEN_REPARSE_LIST, *POPEN_REPARSE_LIST, POPEN_REPARSE_LIST, OPEN_REPARSE_LIST structure [Installable File System Drivers], ntifs/POPEN_REPARSE_LIST, ifsk.open_reparse_list, ntifs/OPEN_REPARSE_LIST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	OPEN_REPARSE_LIST
product: Windows
targetos: Windows
req.typenames: OPEN_REPARSE_LIST, *POPEN_REPARSE_LIST
---

# _OPEN_REPARSE_LIST structure
Points to a list of <b>OPEN_REPARSE_LIST_ENTRY</b>
  structures that specify the tag and possibly GUID that should be  opened directly without returning <b>STATUS_REPARSE</b>.

## Syntax
````
typedef struct _OPEN_REPARSE_LIST {
  LIST_ENTRY OpenReparseList;
} OPEN_REPARSE_LIST, *POPEN_REPARSE_LIST;
````

## Members


`OpenReparseList`

A pointer to a list of <b>OPEN_REPARSE_LIST_ENTRY</b>
  structures that specify the tag and possibly GUID that should be  opened directly without returning <b>STATUS_REPARSE</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows 10, version 1607 |
| **Header** | ntifs.h |