---
UID: NF:ks.KsReleaseDevice
title: KsReleaseDevice function
author: windows-driver-content
description: The KsReleaseDevice function releases the device mutex and exits the critical region.
old-location: stream\ksreleasedevice.htm
old-project: stream
ms.assetid: 47692ac1-969a-4f6f-a2e1-008b82ac1429
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.ksreleasedevice, ks/KsReleaseDevice, avfunc_47876dbc-0dea-459f-96f7-81790d245745.xml, KsReleaseDevice function [Streaming Media Devices], KsReleaseDevice
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
-	KsReleaseDevice
product: Windows
targetos: Windows
req.typenames: 
---


# KsReleaseDevice function
The<b> KsReleaseDevice</b> function releases the device mutex and exits the critical region.

## Syntax

````
void KsReleaseDevice(
  _In_ PKSDEVICE Device
);
````

## Parameters

`Device`

A pointer to a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure representing the AVStream device for which to release synchronous control.


## Return Value

None

## Remarks

<b>KsReleaseDevice </b>is used by a client that has finished accessing the device in a synchronous manner following a previous call to <a href="..\ks\nf-ks-ksacquiredevice.md">KsAcquireDevice</a>.

For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\nf-ks-ksacquiredevice.md">KsAcquireDevice</a>



<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsReleaseDevice function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>