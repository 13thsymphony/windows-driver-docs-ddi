---
UID: NS:engextcpp.ExtKnownStruct
title: ExtKnownStruct
author: windows-driver-content
description: The ExtKnownStruct structure is used to specify how a target's structure can be formatted for output.
old-location: debugger\extknownstruct.htm
old-project: debugger
ms.assetid: 95bf9a47-e121-4432-a28f-5476467f1823
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_b59346d2-06da-4112-9bed-ce64de0f2807.xml, ExtKnownStruct, ExtKnownStruct structure [Windows Debugging], debugger.extknownstruct, engextcpp/ExtKnownStruct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
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
-	Engextcpp.hpp
api_name:
-	ExtKnownStruct
product: Windows
targetos: Windows
req.typenames: 
---

# ExtKnownStruct structure
The <b>ExtKnownStruct</b> structure is used to specify how a target's structure can be formatted for output.

## Syntax
````
struct ExtKnownStruct {
  PCSTR                TypeName;
  ExtKnownStructMethod Method;
  bool                 SuppressesTypeName;
};
````

## Members


`Method`

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff543989">ExtKnownStructMethod</a> callback function that can be called to format an instance of the structure specified in <b>TypeName</b>.

`SuppressesTypeName`

A Boolean flag that specifies whether the formatted output includes the name of the structure's type.  If <b>FALSE</b>, the name is included in the formatted output; otherwise, the name is not included.

`TypeName`

The name of the structure type.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543989">ExtKnownStructMethod</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtKnownStruct structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>