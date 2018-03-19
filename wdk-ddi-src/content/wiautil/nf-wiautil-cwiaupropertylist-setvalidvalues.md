---
UID: NF:wiautil.CWiauPropertyList.SetValidValues
title: CWiauPropertyList::SetValidValues method
author: windows-driver-content
description: The CWiauPropertyList::SetValidValues(BSTR, list) method sets the type, as well as default, current, and valid values for a BSTR property associated with a list of values.
old-location: image\cwiaupropertylist_setvalidvalues_bstr__list_.htm
old-project: image
ms.assetid: b806e310-4e6d-4258-8dd5-0c9aa35a35f4
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: CWiauPropertyList, CWiauPropertyList interface [Imaging Devices], SetValidValues method, CWiauPropertyList::SetValidValues, SetValidValues method [Imaging Devices], SetValidValues method [Imaging Devices], CWiauPropertyList interface, SetValidValues,CWiauPropertyList.SetValidValues, image.cwiaupropertylist_setvalidvalues_bstr__list_, wiauFncs_7653406d-852f-452e-94c3-187be530f684.xml, wiautil/CWiauPropertyList::SetValidValues
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
req.lib: 
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
-	CWiauPropertyList.SetValidValues
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# SetValidValues method
The <b>CWiauPropertyList::SetValidValues(BSTR, list)</b> method sets the type, as well as default, current, and valid values for a <b>BSTR</b> property associated with a list of values. The method also sets the property type to VT_BSTR and subtype to WIA_PROP_LIST (defined in the Microsoft Windows SDK documentation).

## Syntax

````
void SetValidValues(
   INT    index,
   BSTR   defaultValue,
   BSTR   currentValue,
   INT    numValues,
   BSTR   *pValues
);
````

## Parameters

`index`

Specifies the property index. Set this parameter to the value in *<i>pIdx</i> when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a> method returns.

`defaultValue`

Specifies the default setting of the property on the device.

`currentValue`

Specifies the current setting of the property on the device.

`validFlags`




## Return Value

This method does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h, Wiamindr.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540403">CWiauPropertyList::SendToWia</a>



<a href="..\wiautil\nl-wiautil-cwiaupropertylist.md">CWiauPropertyList</a>