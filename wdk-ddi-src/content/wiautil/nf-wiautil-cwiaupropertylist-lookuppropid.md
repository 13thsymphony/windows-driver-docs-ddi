---
UID : NF:wiautil.CWiauPropertyList.LookupPropId
title : CWiauPropertyList::LookupPropId method
author : windows-driver-content
description : The CWiauPropertyList::LookupPropId method finds a property's index, given its property ID.
old-location : image\cwiaupropertylist_lookuppropid.htm
old-project : image
ms.assetid : 454e51fc-f81a-49c8-9e07-e32819af2642
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : image.cwiaupropertylist_lookuppropid, LookupPropId method [Imaging Devices], wiautil/CWiauPropertyList::LookupPropId, CWiauPropertyList interface [Imaging Devices], LookupPropId method, LookupPropId, LookupPropId method [Imaging Devices], CWiauPropertyList interface, wiauFncs_087766c2-718f-4d02-be7f-869df198c3a7.xml, CWiauPropertyList, CWiauPropertyList::LookupPropId
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wiautil.h
req.include-header : Wiautil.h, Wiamindr.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows XP and later.
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
req.lib : wiautil.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SKIP_AMOUNT
req.product : Windows 10 or later.
---


# LookupPropId method
The <b>CWiauPropertyList::LookupPropId</b> method finds a property's index, given its property ID.

## Syntax

````
INT LookupPropId(
   PROPID   PropId
);
````

## Parameters

`PropId`

Specifies the property ID for the property.


## Return Value

On success, the method returns the index of the property within the property list. If it is unable to find the property, the method returns -1.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later. Available in Windows XP and later. |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h, Wiamindr.h) |
| **Library** | wiautil.h |

## See Also

<a href="..\wiautil\nl-wiautil-cwiaupropertylist.md">CWiauPropertyList</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540392">CWiauPropertyList::GetPropId</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20CWiauPropertyList::LookupPropId method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>