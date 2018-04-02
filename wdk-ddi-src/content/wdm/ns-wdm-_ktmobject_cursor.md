---
UID: NS:wdm._KTMOBJECT_CURSOR
title: "_KTMOBJECT_CURSOR"
author: windows-driver-content
description: The KTMOBJECT_CURSOR structure receives enumeration information about KTM objects when a component calls ZwEnumerateTransactionObject.
old-location: kernel\ktmobject_cursor.htm
old-project: kernel
ms.assetid: 0cfcd019-0c5b-4635-859f-741a6e4aa91d
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PKTMOBJECT_CURSOR, KTMOBJECT_CURSOR, KTMOBJECT_CURSOR structure [Kernel-Mode Driver Architecture], PKTMOBJECT_CURSOR, PKTMOBJECT_CURSOR structure pointer [Kernel-Mode Driver Architecture], _KTMOBJECT_CURSOR, kernel.ktmobject_cursor, ktm_ref_dab40de2-cd5f-4f13-93e8-5baa3b9cc37f.xml, wdm/KTMOBJECT_CURSOR, wdm/PKTMOBJECT_CURSOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	KTMOBJECT_CURSOR
product: Windows
targetos: Windows
req.typenames: KTMOBJECT_CURSOR, *PKTMOBJECT_CURSOR
req.product: Windows 10 or later.
---

# _KTMOBJECT_CURSOR structure
The <b>KTMOBJECT_CURSOR</b> structure receives enumeration information about KTM objects when a component calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff566450">ZwEnumerateTransactionObject</a>.

## Syntax
```
typedef struct _KTMOBJECT_CURSOR {
  GUID  LastQuery;
  ULONG ObjectIdCount;
  GUID  ObjectIds[1];
} KTMOBJECT_CURSOR, *PKTMOBJECT_CURSOR;
```

## Members


`LastQuery`

After <b>ZwEnumerateTransactionObject</b> returns, this member contains the GUID of the last object that <b>ZwEnumerateTransactionObject</b> enumerated. Before it calls <b>ZwEnumerateTransactionObject</b> the first time, the caller must set this value to zero.

`ObjectIdCount`

After <b>ZwEnumerateTransactionObject</b> returns, this member contains the number of GUIDs that the <b>ObjectIds</b> array contains.

`ObjectIds`

A caller-allocated array of GUID-typed elements. After <b>ZwEnumerateTransactionObject</b> returns, this array contains GUIDs that identify enumerated objects.

## Remarks
The <b>KTMOBJECT_CURSOR</b> structure is used at the beginning of buffers that callers pass to the <b>ZwEnumerateTransactionObject</b> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later operating system versions. Available in Windows Vista and later operating system versions. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566450">ZwEnumerateTransactionObject</a>