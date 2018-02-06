---
UID: NS:ks._KSFILTER_DISPATCH
title: "_KSFILTER_DISPATCH"
author: windows-driver-content
description: The KSFILTER_DISPATCH structure describes the client callbacks that are made to notify the client of certain events on a given filter type.
old-location: stream\ksfilter_dispatch.htm
old-project: stream
ms.assetid: 3b84c06f-774e-45e1-9a64-711749bb3a88
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/PKSFILTER_DISPATCH, stream.ksfilter_dispatch, avstruct_cfadb813-12c3-4960-89d7-72a75db1684a.xml, _KSFILTER_DISPATCH, PKSFILTER_DISPATCH structure pointer [Streaming Media Devices], ks/KSFILTER_DISPATCH, PKSFILTER_DISPATCH, KSFILTER_DISPATCH, *PKSFILTER_DISPATCH, KSFILTER_DISPATCH structure [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
-	ks.h
apiname:
-	KSFILTER_DISPATCH
product: Windows
targetos: Windows
req.typenames: KSFILTER_DISPATCH, *PKSFILTER_DISPATCH
---

# _KSFILTER_DISPATCH structure
The KSFILTER_DISPATCH structure describes the client callbacks that are made to notify the client of certain events on a given filter type.

## Syntax
````
typedef struct _KSFILTER_DISPATCH {
  PFNKSFILTERIRP     Create;
  PFNKSFILTERIRP     Close;
  PFNKSFILTERPROCESS Process;
  PFNKSFILTERVOID    Reset;
} KSFILTER_DISPATCH, *PKSFILTER_DISPATCH;
````

## Members


## Remarks
Any of the callback pointers may be <b>NULL</b>, indicating that the driver does not wish to receive notification of a given event.

Also see <a href="https://msdn.microsoft.com/f60d4dbd-61e6-4ae2-aa43-9edc8f36c3ff">Restarting Processing in AVStream</a> and 


<a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions. Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions. |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-_ksprocesspin_indexentry.md">KSPROCESSPIN_INDEXENTRY</a>

<a href="..\ks\ns-ks-_ksprocesspin.md">KSPROCESSPIN</a>

<a href="..\ks\nf-ks-kscompletependingrequest.md">KsCompletePendingRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSFILTER_DISPATCH structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>