---
UID: NF:engextcpp.ExtBuffer.Copy
title: ExtBuffer::Copy method
author: windows-driver-content
description: The Copy method sets the typed data represented by the ExtRemoteTyped object by copying the information from another object.
old-location: debugger\extremotetyped_copy_debug_typed_data.htm
old-project: debugger
ms.assetid: bfeafa09-49b7-45b3-84d8-afad5f43b78e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ExtBuffer, ExtBuffer::Copy, Copy
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExtRemoteTyped.Copy
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

# ExtBuffer::Copy method



## -description
The <b>Copy</b> method sets the typed data represented by the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> object by copying the information from another object.



## -syntax

````
void Copy(
  [in] const DEBUG_TYPED_DATA *Typed
);
````


## -parameters

### -param Typed [in]

The typed data description to copy. This becomes the typed data represented by this object.


## -returns
This method does not return a value.


## -remarks
The typed data can also be copied using the <a href="..\engextcpp\nf-engextcpp-extbuffer-copy.md">ExtRemoteTyped::Copy ExtRemoteTyped</a> method.


## -see-also
<dl>
<dt>
<a href="..\wdbgexts\ns-wdbgexts-_debug_typed_data.md">DEBUG_TYPED_DATA</a>
</dt>
<dt>
<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/f7a63a6a-24fa-4c93-ac2e-c44f7984a2c8">ExtRemoteTyped::operator=</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteTyped.Copy method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

