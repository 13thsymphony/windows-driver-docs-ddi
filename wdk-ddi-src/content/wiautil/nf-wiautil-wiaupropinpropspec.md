---
UID: NF:wiautil.wiauPropInPropSpec
title: wiauPropInPropSpec function
author: windows-driver-content
description: The wiauPropInPropSpec function determines whether a specified property specification ID is contained in an array of such values. The function optionally gets the index at which the property specification ID was found.
old-location: image\wiaupropinpropspec.htm
old-project: image
ms.assetid: 5ab82378-ff12-46cc-814b-dc533db15a37
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiaupropinpropspec, wiauFncs_8f694518-d3a5-4636-aae5-046ae519ce0e.xml, wiauPropInPropSpec, wiauPropInPropSpec function [Imaging Devices], wiautil/wiauPropInPropSpec
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
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
-	HeaderDef
api_location:
-	wiautil.h
api_name:
-	wiauPropInPropSpec
product:
- Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauPropInPropSpec function
The <b>wiauPropInPropSpec</b> function determines whether a specified property specification ID is contained in an array of such values. The function optionally gets the index at which the property specification ID was found.

## Syntax

```
BOOL wiauPropInPropSpec(
  LONG           NumPropSpecs,
  const PROPSPEC *pPropSpecs,
  PROPID         PropId,
  int            *pIdx
);
```

## Parameters

`NumPropSpecs`

Specifies the number of property specification IDs in the array pointed to by <i>pPropSpecs</i>.

`pPropSpecs`

Points to the first element of the property specification ID array.

`PropId`

Specifies the property specification ID to search for in the array pointed to by <i>pPropSpecs</i>.

`pIdx`

TBD


## Return Value

This function returns <b>TRUE</b> if it found the property specification ID in the property specification ID array. Otherwise it returns <b>FALSE</b>.

## Remarks

The <b>wiauPropInPropSpec</b> function finds a single property specification ID within an array of property specification IDs. A related function, <a href="https://msdn.microsoft.com/library/windows/hardware/ff550173">wiauPropsInPropSpec</a> can be used to determine whether any of a specified list of property specification IDs is found in another array of property specification IDs.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550173">wiauPropsInPropSpec</a>