---
UID: NF:ks.KsGetFilterFromFileObject
title: KsGetFilterFromFileObject function
author: windows-driver-content
description: The KsGetFilterFromFileObject function returns the AVStream filter object associated with FileObject.
old-location: stream\ksgetfilterfromfileobject.htm
old-project: stream
ms.assetid: eb4ca943-43cb-4eac-8a73-484a7b8acafe
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: avfunc_4c336bce-3064-471e-bd79-daa1888e14b8.xml, ks/KsGetFilterFromFileObject, stream.ksgetfilterfromfileobject, KsGetFilterFromFileObject function [Streaming Media Devices], KsGetFilterFromFileObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KsGetFilterFromFileObject
product: Windows
targetos: Windows
req.typenames: 
---


# KsGetFilterFromFileObject function
The<b> KsGetFilterFromFileObject </b>function returns the AVStream filter object associated with <i>FileObject</i>.

## Syntax

````
PKSFILTER __inline KsGetFilterFromFileObject(
  _In_ PFILE_OBJECT FileObject
);
````

## Parameters

`FileObject`

A pointer to the <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> for which to return the associated AVStream filter object.


## Return Value

<b>KsGetFilterFromFileObject</b> returns a pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure associated with <i>FileObject</i>.

## Remarks

It is the responsibility of the minidriver to verify that <i>FileObject</i> is a file object associated with an AVStream filter. Do this by calling <a href="..\ks\nf-ks-ksgetobjecttypefromfileobject.md">KsGetObjectTypeFromFileObject</a> before calling <b>KsGetFilterFromFileObject</b>.

<b>KsGetFilterFromFileObject</b> is an inline call to <a href="..\ks\nf-ks-ksgetobjectfromfileobject.md">KsGetObjectFromFileObject</a>. The difference is that <b>KsGetFilterFromFileObject</b> typecasts the return as type pointer to a <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions. Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions. |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\ks\nf-ks-ksgetdevicefordeviceobject.md">KsGetDeviceForDeviceObject</a>



<a href="..\ks\nf-ks-ksgetobjecttypefromfileobject.md">KsGetObjectTypeFromFileObject</a>



<a href="..\ks\nf-ks-ksgetobjectfromfileobject.md">KsGetObjectFromFileObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetFilterFromFileObject function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>