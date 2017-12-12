---
UID: NS.PORTCLS.__UNNAMED_STRUCT_0C40_6
title: *PPCAUTOMATION_TABLE
author: windows-driver-content
description: The PCAUTOMATION_TABLE structure contains a miniport driver's master table of properties, methods, and events.
old-location: audio\pcautomation_table.htm
old-project: audio
ms.assetid: 9761a967-063d-4194-8b67-eec476d3372e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: *PPCAUTOMATION_TABLE, *PPCAUTOMATION_TABLE, PCAUTOMATION_TABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCAUTOMATION_TABLE
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# *PPCAUTOMATION_TABLE structure



## -description
The <b>PCAUTOMATION_TABLE</b> structure contains a miniport driver's master table of properties, methods, and events.



## -syntax

````
typedef struct {
  ULONG                 PropertyItemSize;
  ULONG                 PropertyCount;
  const PCPROPERTY_ITEM *Properties;
  ULONG                 MethodItemSize;
  ULONG                 MethodCount;
  const PCMETHOD_ITEM   *Methods;
  ULONG                 EventItemSize;
  ULONG                 EventCount;
  const PCEVENT_ITEM    *Events;
  ULONG                 Reserved;
} PCAUTOMATION_TABLE, *PPCAUTOMATION_TABLE;
````


## -struct-fields

### -field PropertyItemSize

Specifies the size in bytes of the property structure used. Set this member to <b>sizeof</b>(PCPROPERTY_ITEM) or greater. See the following Remarks section.


### -field PropertyCount

Specifies the number of property items in the <i>Properties</i> array.


### -field Properties

Pointer to the filter's array of properties. This is an array of <a href="..\portcls\ns-portcls-__unnamed_struct_0c40_3.md">PCPROPERTY_ITEM</a> structures.


### -field MethodItemSize

Specifies the size in bytes of the methods structure used. Set this member to <b>sizeof</b>(PCMETHOD_ITEM) or greater. See the following Remarks section.


### -field MethodCount

Specifies the number of method items in the <b>Methods</b> array.


### -field Methods

Pointer to the filter's array of methods. This is an array of <a href="audio.pcmethod_item">PCMETHOD_ITEM</a> structures.


### -field EventItemSize

Specifies the size in bytes of the event structure used. Set this member to <b>sizeof</b>(PCEVENT_ITEM) or greater. See the following Remarks section.


### -field EventCount

Specifies the number of event items in the <b>Events</b> array.


### -field Events

Pointer to the filter's array of events. This is an array of <a href="..\portcls\ns-portcls-__unnamed_struct_0c40_5.md">PCEVENT_ITEM</a> structures.


### -field Reserved

Reserved. Initialize to zero.


## -remarks
Any of the structure's item pointers can be <b>NULL</b>, in which case the corresponding counts should be zero. For item tables that are not zero length, the item size should not be smaller than the size of the corresponding item structure that is defined in the header file portcls.h. The minimum size for a property, event, or method item is <b>sizeof</b>(PCPROPERTY_ITEM), <b>sizeof</b>(PCEVENT_ITEM), or <b>sizeof</b>(PCMETHOD_ITEM), respectively. The item size can be larger than this, in which case the item structure is followed by whatever private data the miniport driver appends to it. Item sizes should be a multiple of eight.

The <a href="audio.iminiport_getdescription">IMiniport::GetDescription</a> method outputs a <a href="..\portcls\ns-portcls-__unnamed_struct_0c40_9.md">PCFILTER_DESCRIPTOR</a> structure that points to a PCAUTOMATION_TABLE structure that specifies the miniport driver's automation table.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\ns-portcls-__unnamed_struct_0c40_3.md">PCPROPERTY_ITEM</a>
</dt>
<dt>
<a href="..\portcls\ns-portcls-__unnamed_struct_0c40_5.md">PCEVENT_ITEM</a>
</dt>
<dt>
<a href="audio.pcmethod_item">PCMETHOD_ITEM</a>
</dt>
<dt>
<a href="audio.iminiport_getdescription">IMiniport::GetDescription</a>
</dt>
<dt>
<a href="..\portcls\ns-portcls-__unnamed_struct_0c40_9.md">PCFILTER_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PCAUTOMATION_TABLE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

