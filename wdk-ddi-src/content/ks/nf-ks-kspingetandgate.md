---
UID: NF:ks.KsPinGetAndGate
title: KsPinGetAndGate function
author: windows-driver-content
description: The KsPinGetAndGate function returns the processing control gate for Pin.
old-location: stream\kspingetandgate.htm
old-project: stream
ms.assetid: abd4da69-c0c3-442f-af58-e77362c637da
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsPinGetAndGate, KsPinGetAndGate function [Streaming Media Devices], stream.kspingetandgate, avfunc_a4159ef9-1a69-4716-96ce-4fabd1ee6218.xml, KsPinGetAndGate
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsPinGetAndGate
product: Windows
targetos: Windows
req.typenames: 
---


# KsPinGetAndGate function
The<b> KsPinGetAndGate</b> function returns the processing control gate for <i>Pin</i>.

## Syntax

````
PKSGATE KsPinGetAndGate(
  _In_ PKSPIN Pin
);
````

## Parameters

`Pin`

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> for which to return the processing control gate.


## Return Value

Returns a pointer to the <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> representing the processing control gate for <i>Pin</i>.

## Remarks

For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | Any level |

## See Also

<a href="..\ks\nf-ks-ksfiltergetandgate.md">KsFilterGetAndGate</a>



<a href="..\ks\ns-ks-_ksgate.md">KSGATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinGetAndGate function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>