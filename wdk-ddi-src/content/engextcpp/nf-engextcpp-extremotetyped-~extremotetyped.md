---
UID: NF:engextcpp.ExtRemoteTyped.~ExtRemoteTyped
title: ExtRemoteTyped::~ExtRemoteTyped method
author: windows-driver-content
description: The ExtRemoteTyped class provides the ability to manipulate typed data on the target.
old-location: debugger\extremotetyped.htm
old-project: debugger
ms.assetid: 1f5d71a5-fa60-4819-9838-2b035ef21374
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ExtRemoteTyped, ExtRemoteTyped::~ExtRemoteTyped, ~ExtRemoteTyped
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExtRemoteTyped
req.alt-loc: engextcpp.hpp
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
req.typenames: *PDRMRIGHTS, DRMRIGHTS
---

# ExtRemoteTyped::~ExtRemoteTyped method



## -description
The <b>ExtRemoteTyped</b> class provides the ability to manipulate typed data on the target.  An instance of this class represents a small region of memory on the target. This region is interpreted as a specific type.  This class provides methods for manipulating the memory according to the type and for accessing the object hierarchy on the target.

<b>ExtRemoteTyped</b> is a subclass of <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>.

The <b>ExtRemoteTyped</b> class includes the following constructors, operators, and methods:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a>



<a href="..\engextcpp\nf-engextcpp-extbuffer-operator=.md">operator=</a>



<a href="..\engextcpp\nf-engextcpp-extbuffer-operator=.md">operator=</a>



<a href="..\engextcpp\nf-engextcpp-extbuffer-copy.md">Copy(Debug Typed Data)</a>



<a href="..\engextcpp\nf-engextcpp-extbuffer-copy.md">Copy(ExtRemoteTyped)</a>



<a href="..\engextcpp\nf-engextcpp-extbuffer-set.md">Set(bool)</a>



<a href="..\engextcpp\nf-engextcpp-extbuffer-set.md">Set(pcstr)</a>



<a href="..\engextcpp\nf-engextcpp-extbuffer-set.md">Set(pcstr ulong64)</a>



<a href="..\engextcpp\nf-engextcpp-extbuffer-set.md">Set(pcstr ulong64 bool)</a>



<a href="https://msdn.microsoft.com/ae478779-8ec1-4a50-a37c-3017aca2c912">SetPrint</a>



<a href="https://msdn.microsoft.com/c206d8e7-1a90-4866-868b-20275a52e2dd">HasField</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549457">GetTypeSize</a>


<b>GetFieldSize</b>


<a href="https://msdn.microsoft.com/library/windows/hardware/ff546758">GetFieldOffset</a>



<a href="https://msdn.microsoft.com/be662551-c4d3-4979-8a9b-c913fb6bd336">Field</a>



<a href="https://msdn.microsoft.com/abe43441-3e00-4d85-ae84-dd738303ab1b">ArrayElement</a>



<a href="https://msdn.microsoft.com/27a90926-95f4-43cd-b8d1-1b60ad23d737">Dereference</a>



<a href="https://msdn.microsoft.com/1f237e8a-c0d3-4812-a96d-4cdc6f8e31df">GetPointerTo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439396">Eval</a>



<a href="https://msdn.microsoft.com/f7a63a6a-24fa-4c93-ac2e-c44f7984a2c8">operator*</a>



<a href="..\engextcpp\nf-engextcpp-extremotetyped-operator[].md">operator[]</a>



<a href="..\engextcpp\nf-engextcpp-extremotetyped-operator[].md">operator[]</a>



<a href="..\engextcpp\nf-engextcpp-extremotetyped-operator[].md">operator[]</a>



<a href="..\engextcpp\nf-engextcpp-extremotetyped-operator[].md">operator[]</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549408">GetTypeName</a>



<a href="https://msdn.microsoft.com/fda88a3d-4cdf-4be1-87a7-29e312453686">OutTypeName</a>



<a href="https://msdn.microsoft.com/e9c11c07-bd4a-4d49-a820-4617be691c80">OutSimpleValue</a>



<a href="https://msdn.microsoft.com/8f5b3e8b-1b01-4a14-b472-cb5de82e869a">OutFullValue</a>



<a href="https://msdn.microsoft.com/f7d24a3b-b5a8-4924-85d9-8bf7983b95fa">OutTypeDefinition</a>



<a href="https://msdn.microsoft.com/041f585a-bc1f-4413-9d68-ae18969e4d75">Release</a>



<a href="https://msdn.microsoft.com/5f966bf0-2dc3-4422-bfec-09d1b136f9f0">GetTypeFieldOffset</a>




The <a href="..\wdbgexts\ns-wdbgexts-_debug_typed_data.md">DEBUG_TYPED_DATA</a> structure that describes the typed data represented by this instance of <b>ExtRemoteTyped</b>.

Indicates whether or not the destructor for this instance of <b>ExtRemoteTyped</b> needs to release the <a href="..\wdbgexts\ns-wdbgexts-_debug_typed_data.md">DEBUG_TYPED_DATA</a> structure that is specified in <b>m_Typed</b>.



## -parameters


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wdbgexts\ns-wdbgexts-_debug_typed_data.md">DEBUG_TYPED_DATA</a>
</dt>
<dt>
<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteTyped class%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

