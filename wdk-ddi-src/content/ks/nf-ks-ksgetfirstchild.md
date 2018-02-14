---
UID: NF:ks.KsGetFirstChild
title: KsGetFirstChild function
author: windows-driver-content
description: The KsGetFirstChild function returns the first AVStream child object of Object.
old-location: stream\ksgetfirstchild.htm
old-project: stream
ms.assetid: f7ff16ac-fe20-4998-a8b3-d1d02c418938
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: avfunc_cfdde7e3-bc8b-46df-abf4-fe43ac9b0bfc.xml, stream.ksgetfirstchild, KsGetFirstChild function [Streaming Media Devices], ks/KsGetFirstChild, KsGetFirstChild
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsGetFirstChild
product: Windows
targetos: Windows
req.typenames: 
---


# KsGetFirstChild function
The<b> KsGetFirstChild</b> function returns the first AVStream child object of <i>Object</i>.

## Syntax

````
PVOID KsGetFirstChild(
  _In_ PVOID Object
);
````

## Parameters

`Object`

The object for which to find the first AVStream child object.


## Return Value

<b>KsGetFirstChild</b> returns the first AVStream child object of <i>Object</i>. If no such child object exists, it returns <b>NULL</b>.

## Remarks

To see the hierarchical organization of AVStream objects, see <a href="https://msdn.microsoft.com/b7d6f06d-6c97-414e-a453-d375e2d7ccf5">AVStream Object Hierarchy</a>.

Minidrivers rarely call this function directly. Those that do must manually perform typecasts to and from PVOID. There are a number of functions that are inline calls to <b>KsGetFirstChild</b> and perform typecasts for you: <a href="..\ks\nf-ks-ksdevicegetfirstchildfilterfactory.md">KsDeviceGetFirstChildFilterFactory</a> and <a href="..\ks\nf-ks-ksfilterfactorygetfirstchildfilter.md">KsFilterFactoryGetFirstChildFilter</a>. Note that the object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions. Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions. |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\nf-ks-ksfiltergetfirstchildpin.md">KsFilterGetFirstChildPin</a>



<a href="..\ks\nf-ks-ksgetparent.md">KsGetParent</a>



<a href="..\ks\nf-ks-ksdevicegetfirstchildfilterfactory.md">KsDeviceGetFirstChildFilterFactory</a>



<a href="..\ks\nf-ks-ksfilterfactorygetfirstchildfilter.md">KsFilterFactoryGetFirstChildFilter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetFirstChild function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>