---
UID: NF:wexlogtrace.operator=
title: operator= function
author: windows-driver-content
description: The operator= overloaded assignment operator sets the typed data represented by the ExtRemoteTyped object by copying the information from another object.
old-location: debugger\extremotetyped_operatorequals_debug_typed_data.htm
old-project: debugger
ms.assetid: 0dd00f33-1ede-43b7-97b7-55942c3f7a27
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ExtRemoteTyped class [Windows Debugging], operator= method, debugger.extremotetyped_operatorequals_debug_typed_data, operator=, operator= method [Windows Debugging], operator= method [Windows Debugging], ExtRemoteTyped class
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wexlogtrace.h
req.include-header: Engextcpp.hpp, Wexlogtrace.h, Wextestclass.h, Wextestclass.h
req.target-type: Desktop
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
-	COM
api_location:
-	arrayofelements.hpp
api_name:
-	ExtRemoteTyped.operator=
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# operator= function
The <b>operator=</b> overloaded assignment operator sets the typed data represented by the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> object by copying the information from another object.

## Syntax

````
ExtRemoteTyped & operator=(
  [in] const DEBUG_TYPED_DATA *Typed
);
````

## Parameters

This function has no parameters.

## Return Value

<b>operator=</b>  returns the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> object.

## Remarks

The typed data can also be copied using the <a href="..\engextcpp\nf-engextcpp-extbuffer-copy.md">ExtRemoteTyped::Copy(Debug Typed Data)</a> or <a href="..\engextcpp\nf-engextcpp-extbuffer-copy.md">ExtRemoteTyped::Copy(ExtRemoteTyped)</a> methods.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wexlogtrace.h (include Engextcpp.hpp, Wexlogtrace.h, Wextestclass.h, Wextestclass.h) |

## See Also

<a href="..\wdbgexts\ns-wdbgexts-_debug_typed_data.md">DEBUG_TYPED_DATA</a>



<a href="..\wextestclass\nf-wextestclass-fixtureinvokefunctor-operator=.md">ExtRemoteTyped::Operator= (ExtRemoteTyped)</a>



<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteTyped.operator= method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>