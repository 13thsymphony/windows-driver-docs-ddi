---
UID: NF.wiautil.CWiauPropertyList.CWiauPropertyList
title: CWiauPropertyList::CWiauPropertyList method
author: windows-driver-content
description: The CWiauPropertyList::CWiauPropertyList method is the constructor for the CWiauPropertyList class.
old-location: image\cwiaupropertylist_cwiaupropertylist.htm
old-project: Image
ms.assetid: 5e493d3c-81b6-4db5-a550-c86eadf5a723
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: CWiauPropertyList, CWiauPropertyList::CWiauPropertyList, CWiauPropertyList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CWiauPropertyList.CWiauPropertyList
req.alt-loc: Wiautil.h
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

# CWiauPropertyList::CWiauPropertyList method



## -description
The <b>CWiauPropertyList::CWiauPropertyList</b> method is the constructor for the <b>CWiauPropertyList</b> class.



## -syntax

````
void CWiauPropertyList();
````


## -parameters


## -returns
This method does not return a value.

This method does not return a value.

This method does not return a value.


## -remarks
The <b>CWiauPropertyList</b> constructor initializes all data members of a property list object to either <b>NULL</b> or zero. Use the <a href="image.cwiaupropertylist_init">CWiauPropertyList::Init</a> method to reserve memory for properties. Use the <a href="image.cwiaupropertylist_defineproperty">CWiauPropertyList::DefineProperty</a> method once per property to add it to the property list object.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows XP and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wiautil.h (include Wiautil.h or Wiamindr.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="image.cwiaupropertylist__cwiaupropertylist">CWiauPropertyList::~CWiauPropertyList</a>
</dt>
<dt>
<a href="image.cwiaupropertylist_init">CWiauPropertyList::Init</a>
</dt>
<dt>
<a href="image.cwiaupropertylist_defineproperty">CWiauPropertyList::DefineProperty</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20CWiauPropertyList::CWiauPropertyList method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

