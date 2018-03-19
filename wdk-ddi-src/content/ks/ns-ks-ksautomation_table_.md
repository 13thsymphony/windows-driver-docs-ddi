---
UID: NS:ks.KSAUTOMATION_TABLE_
title: KSAUTOMATION_TABLE_
author: windows-driver-content
description: The KSAUTOMATION_TABLE structure defines a structure that combines tables for properties, methods, and events.
old-location: stream\ksautomation_table.htm
old-project: stream
ms.assetid: 76ab776d-0921-4fdb-9646-2cb97a582f6e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSAUTOMATION_TABLE, KSAUTOMATION_TABLE, KSAUTOMATION_TABLE structure [Streaming Media Devices], KSAUTOMATION_TABLE_, PKSAUTOMATION_TABLE, PKSAUTOMATION_TABLE structure pointer [Streaming Media Devices], avstruct_7389df5c-d86a-43b2-9daf-d0e1e8a2dfbe.xml, ks/KSAUTOMATION_TABLE, ks/PKSAUTOMATION_TABLE, stream.ksautomation_table"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
-	KSAUTOMATION_TABLE
product: Windows
targetos: Windows
req.typenames: KSAUTOMATION_TABLE, *PKSAUTOMATION_TABLE
---

# KSAUTOMATION_TABLE_ structure
The KSAUTOMATION_TABLE structure defines a structure that combines tables for properties, methods, and events.

## Syntax
````
typedef struct KSAUTOMATION_TABLE_ {
  ULONG                PropertySetsCount;
  ULONG                PropertyItemSize;
  const KSPROPERTY_SET *PropertySets;
  ULONG                MethodSetsCount;
  ULONG                MethodItemSize;
  const KSMETHOD_SET   *MethodSets;
  ULONG                EventSetsCount;
  ULONG                EventItemSize;
  const KSEVENT_SET    *EventSets;
  PVOID                Alignment;
} KSAUTOMATION_TABLE, *PKSAUTOMATION_TABLE;
````

## Members


`PropertySetsCount`

This member specifies the number of property sets in this automation table.

`PropertyItemSize`

This member specifies size in bytes of property items in this table.

`PropertySets`

A pointer to an array of <a href="..\ks\ns-ks-ksproperty_set.md">KSPROPERTY_SET</a> objects (<b>PropertySetsCount</b> in length) defining the property sets in this automation table.  Each set contains a specific number of items of size <b>PropertyItemSize</b>.

`MethodSetsCount`

This member specifies the number of method sets in this automation table.

`MethodItemSize`

This member specifies the size in bytes of method items in this table.

`MethodSets`

An array of <a href="..\ks\ns-ks-ksmethod_set.md">KSMETHOD_SET</a> objects (<b>MethodSetsCount</b> in length) defining the method sets in this automation table.  Each set has a specific number of items in it of size <b>MethodItemSize</b>.

`EventSetsCount`

This member specifies the number of event sets in this automation table.

`EventItemSize`

This member specifies the size in bytes of event items in this table.

`EventSets`

An array of <a href="..\ks\ns-ks-ksevent_set.md">KSEVENT_SET</a> objects (<b>EventSetsCount</b> in length) defining the event sets in this automation table.  Each set has a specific number of items in it of size <b>EventItemSize</b>.

`Alignment`

Reserved for internal use by AVStream. Minidrivers should not manipulate this member.

## Remarks
Note that each object (pin, filter, topology node) should define an automation table. Minidrivers can use macros defined in <i>Ks.h</i> to define automation tables and the arrays they contain:

DEFINE_KSAUTOMATION_TABLE

DEFINE_KSAUTOMATION_PROPERTIES

DEFINE_KSAUTOMATION_METHODS

DEFINE_KSAUTOMATION_EVENTS

To specify an automation table containing an empty property array, event array, or method array:

DEFINE_KSAUTOMATION_PROPERTIES_NULL

DEFINE_KSAUTOMATION_METHODS_NULL

DEFINE_KSAUTOMATION_EVENTS_NULL

For example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DEFINE_KSAUTOMATION_TABLE (MyAutomationTable) {
DEFINE_KSAUTOMATION_PROPERTIES (MyPropertyTable),
DEFINE_KSAUTOMATION_METHODS (MyMethodTable),
DEFINE_KSAUTOMATION_EVENTS (MyEventTable)</pre>
</td>
</tr>
</table></span></div>
};

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions. Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions. |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-ksevent_item.md">KSEVENT_ITEM</a>



<a href="..\ks\ns-ks-ksevent_set.md">KSEVENT_SET</a>



<a href="..\ks\ns-ks-ksproperty_set.md">KSPROPERTY_SET</a>



<a href="..\ks\ns-ks-ksmethod_set.md">KSMETHOD_SET</a>



<a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a>



<a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a>