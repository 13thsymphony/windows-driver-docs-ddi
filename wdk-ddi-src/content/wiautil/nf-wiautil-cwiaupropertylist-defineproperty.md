---
UID: NF:wiautil.CWiauPropertyList.DefineProperty
title: CWiauPropertyList::DefineProperty method
author: windows-driver-content
description: The CWiauPropertyList::DefineProperty method adds a property definition to a property list object.
old-location: image\cwiaupropertylist_defineproperty.htm
old-project: image
ms.assetid: 599c97af-1285-4fb9-af0b-edcd48249692
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: CWiauPropertyList, CWiauPropertyList interface [Imaging Devices], DefineProperty method, CWiauPropertyList::DefineProperty, DefineProperty method [Imaging Devices], DefineProperty method [Imaging Devices], CWiauPropertyList interface, DefineProperty,CWiauPropertyList.DefineProperty, image.cwiaupropertylist_defineproperty, wiauFncs_8be9dc72-0d8c-4894-aab0-47a312d9fae7.xml, wiautil/CWiauPropertyList::DefineProperty
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wiautil.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wiautil.h
api_name:
-	CWiauPropertyList.DefineProperty
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# DefineProperty method
The <b>CWiauPropertyList::DefineProperty</b> method adds a property definition to a property list object.

## Syntax

````
HRESULT DefineProperty(
   int        *pIdx,
   PROPID     PropId,
   LPOLESTR   PropName,
   ULONG      Access,
   ULONG      SubType
);
````

## Parameters

`pIdx`

Pointer to a memory location that receives the index for the newly added property. Many other methods in this class use a property's index in order to identify the property.

`PropId`

Specifies a property ID constant.

`PropName`

Pointer to a name string for the property.

`Access`

Specifies the type of access for the property, usually either WIA_PROP_READ (read-only) or WIA_PROP_RW (read/write).

`SubType`

Specifies the property subtype, one of WIA_PROP_FLAG, WIA_PROP_LIST, WIA_PROP_RANGE, or WIA_PROP_NONE. The first three constants indicate, respectively, that a property is a set of flag values, a list of values, or a range of values. The fourth constant indicates that a property is none of these.


## Return Value

This method returns S_OK if it is able to define a property successfully. If the property list does not have enough room for an additional property, the method returns E_FAIL.

## Remarks

The WIA_PROP_<i>XXX</i> constants are defined in the Microsoft Windows SDK documentation.

Before a property can be added to a property list, the property list must be initialized. Do this by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540396">CWiauPropertyList::Init</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h, Wiamindr.h) |
| **Library** | wiautil.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540396">CWiauPropertyList::Init</a>



<a href="..\wiautil\nl-wiautil-cwiaupropertylist.md">CWiauPropertyList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20CWiauPropertyList::DefineProperty method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>