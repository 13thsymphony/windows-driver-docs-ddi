---
UID: NF:engextcpp.ExtCheckedPointer.Set
title: ExtCheckedPointer::Set method
author: windows-driver-content
description: The Set method sets the typed data represented by the ExtRemoteTyped object.
old-location: debugger\extremotetyped_set_bool.htm
old-project: debugger
ms.assetid: e75c17d2-fdf7-4dba-9892-74c764956924
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ExtCheckedPointer, ExtCheckedPointer::Set, Set
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
req.alt-api: ExtRemoteTyped.Set
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

# ExtCheckedPointer::Set method



## -description
The <b>Set</b> method sets the typed data represented by the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> object.



## -syntax

````
void Set(
  [in] bool    PtrTo,
  [in] ULONG64 TypeModBase,
  [in] ULONG   TypeId,
  [in] ULONG64 Offset
);
````


## -parameters

### -param PtrTo [in]

Specifies whether or not to set the <b>ExtRemoteTyped</b> instance to the specified typed data, or to a pointer to the specified typed data.  If <i>PtrTo</i> is <code>true</code>, the <b>ExtRemoteTyped</b> instance will be a pointer to the typed data.


### -param TypeModBase [in]

The base address of the module to which the type belongs.


### -param TypeId [in]

The type ID of the type.


### -param Offset [in]

Specifies the location of the data in the target's memory.


## -returns
This method does not return a value.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>
</dt>
<dt>
<a href="..\engextcpp\nf-engextcpp-extbuffer-set.md">ExtRemoteTyped::Set (PCSTR)</a>
</dt>
<dt>
<a href="..\engextcpp\nf-engextcpp-extbuffer-set.md">ExtRemoteTyped::Set (PCSTR, ULONG64)</a>
</dt>
<dt>
<a href="..\engextcpp\nf-engextcpp-extbuffer-set.md">ExtRemoteTyped::Set (PCSTR, ULONG64, bool)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544384">ExtRemoteTyped::SetPrint</a>
</dt>
<dt>
<a href="..\engextcpp\nl-engextcpp-extremotetypedlist.md">ExtRemoteTypedList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteTyped.Set method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

