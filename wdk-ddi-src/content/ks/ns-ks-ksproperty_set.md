---
UID: NS:ks.KSPROPERTY_SET
title: KSPROPERTY_SET
author: windows-driver-content
description: A kernel streaming driver or pin may use the KSPROPERTY_SET structure to describe how it supports a property set.
old-location: stream\ksproperty_set.htm
old-project: stream
ms.assetid: 18eda28d-f1dc-4b49-8c1a-07e11ea4b288
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_SET, KSPROPERTY_SET, *PKSPROPERTY_SET
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
req.alt-api: KSPROPERTY_SET
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
req.typenames: KSPROPERTY_SET, *PKSPROPERTY_SET
---

# KSPROPERTY_SET structure



## -description
A kernel streaming driver or pin may use the KSPROPERTY_SET structure to describe how it supports a property set.



## -syntax

````
typedef struct {
  const GUID                *Set;
  ULONG                     PropertiesCount;
  const KSPROPERTY_ITEM     *PropertyItem;
  ULONG                     FastIoCount;
  const KSFASTPROPERTY_ITEM *FastIoTable;
} KSPROPERTY_SET, *PKSPROPERTY_SET;
````


## -struct-fields

### -field Set

Specifies the GUID that identifies the property set.


### -field PropertiesCount

Specifies the size of the array pointed to by the <b>PropertyItem</b> member.


### -field PropertyItem

Points to the beginning of an array of <a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a> structures that describe how the driver or pin supports each property in the set.


### -field FastIoCount

Reserved for system use.


### -field FastIoTable

A pointer to a <a href="..\ks\ns-ks-ksfastproperty_item.md">KSFASTPROPERTY_ITEM</a> structure. This member is reserved for system use.


## -remarks
For more information, see <a href="https://msdn.microsoft.com/a385929e-1934-4d88-aaf9-ff1ddbfd30f7">KS Properties</a>.


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
<a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_SET structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

