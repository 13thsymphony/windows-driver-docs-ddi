---
UID: NE:wdbgexts._EXT_TDOP
title: "_EXT_TDOP"
author: windows-driver-content
description: The EXT_TDOP enumeration is used in the Operation member of the EXT_TYPED_DATA structure to specify which suboperation the DEBUG_REQUEST_EXT_TYPED_DATA_ANSI Request operation will perform.
old-location: debugger\ext_tdop.htm
old-project: Debugger
ms.assetid: 1793aaff-b0ac-4858-8a15-56eace87a09a
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: wdbgexts/EXT_TDOP_GET_TYPE_NAME, wdbgexts/EXT_TDOP_RELEASE, wdbgexts/EXT_TDOP_COPY, wdbgexts/EXT_TDOP_EVALUATE, wdbgexts/EXT_TDOP_HAS_FIELD, EXT_TDOP_GET_TYPE_NAME, EXT_TDOP, wdbgexts/EXT_TDOP_GET_POINTER_TO, wdbgexts/EXT_TDOP_SET_FROM_TYPE_ID_AND_U64, EXT_TDOP_OUTPUT_FULL_VALUE, wdbgexts/EXT_TDOP_OUTPUT_SIMPLE_VALUE, wdbgexts/EXT_TDOP_GET_ARRAY_ELEMENT, wdbgexts/EXT_TDOP_OUTPUT_TYPE_NAME, wdbgexts/EXT_TDOP_GET_FIELD_OFFSET, EXT_TDOP_SET_FROM_EXPR, wdbgexts/EXT_TDOP_OUTPUT_TYPE_DEFINITION, EXT_TDOP_SET_PTR_FROM_TYPE_ID_AND_U64, EXT_TDOP_GET_TYPE_SIZE, EXT_TDOP_COPY, wdbgexts/EXT_TDOP_GET_FIELD, wdbgexts/EXT_TDOP_SET_FROM_EXPR, debugger.ext_tdop, wdbgexts/EXT_TDOP, EXT_TDOP_GET_ARRAY_ELEMENT, wdbgexts/EXT_TDOP_GET_TYPE_SIZE, wdbgexts/EXT_TDOP_SET_PTR_FROM_TYPE_ID_AND_U64, EXT_TDOP_OUTPUT_SIMPLE_VALUE, EXT_TDOP enumeration [Windows Debugging], EXT_TDOP_GET_FIELD, EXT_TDOP_HAS_FIELD, Structures_77246150-309c-4646-82b2-ba9c75d9a2d4.xml, wdbgexts/EXT_TDOP_COUNT, wdbgexts/EXT_TDOP_GET_DEREFERENCE, EXT_TDOP_SET_FROM_U64_EXPR, EXT_TDOP_OUTPUT_TYPE_NAME, _EXT_TDOP, EXT_TDOP_RELEASE, EXT_TDOP_EVALUATE, EXT_TDOP_GET_FIELD_OFFSET, EXT_TDOP_GET_POINTER_TO, wdbgexts/ EXT_TDOP_SET_FROM_U64_EXPR, EXT_TDOP_OUTPUT_TYPE_DEFINITION, EXT_TDOP_GET_DEREFERENCE, EXT_TDOP_COUNT, wdbgexts/EXT_TDOP_OUTPUT_FULL_VALUE, EXT_TDOP_SET_FROM_TYPE_ID_AND_U64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdbgexts.h
req.include-header: WdbgExts.h, DbgEng.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	WdbgExts.h
apiname:
-	EXT_TDOP
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# _EXT_TDOP Enumeration
The EXT_TDOP enumeration is used in the <b>Operation</b> member of the <a href="..\wdbgexts\ns-wdbgexts-_ext_typed_data.md">EXT_TYPED_DATA</a> structure to specify which suboperation the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541547">DEBUG_REQUEST_EXT_TYPED_DATA_ANSI</a>
<a href="https://msdn.microsoft.com/efb3c93c-5405-418b-a063-afa8e5e9e59a"> Request</a> operation will perform.

## Syntax
````
typedef enum _EXT_TDOP { 
  EXT_TDOP_COPY,
  EXT_TDOP_RELEASE,
  EXT_TDOP_SET_FROM_EXPR,
   EXT_TDOP_SET_FROM_U64_EXPR,
  EXT_TDOP_GET_FIELD,
  EXT_TDOP_EVALUATE,
  EXT_TDOP_GET_TYPE_NAME,
  EXT_TDOP_OUTPUT_TYPE_NAME,
  EXT_TDOP_OUTPUT_SIMPLE_VALUE,
  EXT_TDOP_OUTPUT_FULL_VALUE,
  EXT_TDOP_HAS_FIELD,
  EXT_TDOP_GET_FIELD_OFFSET,
  EXT_TDOP_GET_ARRAY_ELEMENT,
  EXT_TDOP_GET_DEREFERENCE,
  EXT_TDOP_GET_TYPE_SIZE,
  EXT_TDOP_OUTPUT_TYPE_DEFINITION,
  EXT_TDOP_GET_POINTER_TO,
  EXT_TDOP_SET_FROM_TYPE_ID_AND_U64,
  EXT_TDOP_SET_PTR_FROM_TYPE_ID_AND_U64,
  EXT_TDOP_COUNT
} EXT_TDOP;
````

## Constants

<table>
            
                <tr>
                    <td>EXT_TDOP_COPY</td>
                    <td>Makes a copy of a typed data description.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_COUNT</td>
                    <td>Does not specify an operation. Instead, it represents the number of suboperations defined in the EXT_TDOP enumeration.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_EVALUATE</td>
                    <td>Returns the value of an expression. An optional value can be provided as a parameter to the expression.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_GET_ARRAY_ELEMENT</td>
                    <td>Returns an element from an array.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_GET_DEREFERENCE</td>
                    <td>Dereferences a pointer, returning the value it points to.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_GET_FIELD</td>
                    <td>Returns a member of a structure.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_GET_FIELD_OFFSET</td>
                    <td>Returns the offset of a member within a structure.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_GET_POINTER_TO</td>
                    <td>Returns a new typed data description that represents a pointer to specified typed data.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_GET_TYPE_NAME</td>
                    <td>Returns the type name for typed data.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_GET_TYPE_SIZE</td>
                    <td>Returns the size of the specified typed data.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_HAS_FIELD</td>
                    <td>Determines whether a structure contains a specified member.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_OUTPUT_FULL_VALUE</td>
                    <td>Prints the type and value for typed data.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_OUTPUT_SIMPLE_VALUE</td>
                    <td>Prints the value of typed data.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_OUTPUT_TYPE_DEFINITION</td>
                    <td>Prints the definition of the type for the specified typed data.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_OUTPUT_TYPE_NAME</td>
                    <td>Prints the type name for typed data.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_RELEASE</td>
                    <td>Releases a typed data description.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_SET_FROM_EXPR</td>
                    <td>Returns the value of an expression.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_SET_FROM_TYPE_ID_AND_U64</td>
                    <td>Creates a typed data description from a type and memory location.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_SET_FROM_U64_EXPR</td>
                    <td>Returns the value of an expression. An optional address can be provided as a parameter to the expression.</td>
                </tr>
            
                <tr>
                    <td>EXT_TDOP_SET_PTR_FROM_TYPE_ID_AND_U64</td>
                    <td>Creates a typed data description representing a pointer to a specified memory location with specified type.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdbgexts.h (include WdbgExts.h, DbgEng.h) |

## See Also

<a href="..\wdbgexts\ns-wdbgexts-_ext_typed_data.md">EXT_TYPED_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554564">Request</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541547">DEBUG_REQUEST_EXT_TYPED_DATA_ANSI</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20EXT_TDOP enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>