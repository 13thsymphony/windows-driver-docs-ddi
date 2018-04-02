---
UID: NS:ks.KSMETHOD_SET
title: KSMETHOD_SET
author: windows-driver-content
description: The KSMETHOD_SET structure describes the methods that comprise a kernel streaming method set.
old-location: stream\ksmethod_set.htm
old-project: stream
ms.assetid: e06bbf6f-f636-4fb1-8195-b74512d4cd13
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSMETHOD_SET, KSMETHOD_SET, KSMETHOD_SET structure [Streaming Media Devices], PKSMETHOD_SET, PKSMETHOD_SET structure pointer [Streaming Media Devices], ks-struct_c3d1123f-8d2a-491b-a748-df8d88c7d9bc.xml, ks/KSMETHOD_SET, ks/PKSMETHOD_SET, stream.ksmethod_set"
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
-	ks.h
api_name:
-	KSMETHOD_SET
product:
- Windows
targetos: Windows
req.typenames: KSMETHOD_SET, *PKSMETHOD_SET
---

# KSMETHOD_SET structure
The KSMETHOD_SET structure describes the methods that comprise a kernel streaming method set.

## Syntax
```
typedef struct KSMETHOD_SET {
  const GUID              *Set;
  ULONG                   MethodsCount;
  const KSMETHOD_ITEM     *MethodItem;
  ULONG                   FastIoCount;
  const KSFASTMETHOD_ITEM *FastIoTable;
}  *PKSMETHOD_SET;
```

## Members


`Set`

Specifies a GUID the identifies the kernel streaming method set. For more information about method set GUIDs, see <b>Remarks</b>.

`MethodsCount`

Specifies the number of methods in this method set.

`MethodItem`

Points to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563420">KSMETHOD_ITEM</a> structures. Each structure describes one method of the method set.

`FastIoCount`

Reserved for system use. Do not use.

`FastIoTable`

Reserved for system use. Do not use.

## Remarks
Microsoft provides several system-defined kernel streaming method set GUIDs. Minidrivers specify one of these GUIDs in the <b>Set</b> member. Kernel streaming method sets typically begin with a <i>KSMETHODSETID</i> prefix. Method set GUIDs are defined in <i>ks.h</i>, <i>ksmedia.h</i>, <i>bdamedia.h</i>, and possibly other header files.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563420">KSMETHOD_ITEM</a>