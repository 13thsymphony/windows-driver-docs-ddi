---
UID: NS:ks._KSFILTERFACTORY
title: "_KSFILTERFACTORY"
author: windows-driver-content
description: The KSFILTERFACTORY structure represents a filter factory.
old-location: stream\ksfilterfactory.htm
old-project: stream
ms.assetid: c40e25f8-e6e5-43bc-895d-a6b247d07470
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "*PKSFILTERFACTORY, PKSFILTERFACTORY structure pointer [Streaming Media Devices], stream.ksfilterfactory, KSFILTERFACTORY, ks/PKSFILTERFACTORY, ks/KSFILTERFACTORY, PKSFILTERFACTORY, _KSFILTERFACTORY, KSFILTERFACTORY structure [Streaming Media Devices], avstruct_def7ad6b-4cda-4677-abbc-3f8a458fbc87.xml"
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
-	KSFILTERFACTORY
product: Windows
targetos: Windows
req.typenames: KSFILTERFACTORY, *PKSFILTERFACTORY
---

# _KSFILTERFACTORY structure
The KSFILTERFACTORY structure represents a filter factory.

## Syntax
````
typedef struct _KSFILTERFACTORY {
  const KSFILTER_DESCRIPTOR *FilterDescriptor;
  KSOBJECT_BAG              Bag;
  PVOID                     Context;
} KSFILTERFACTORY, *PKSFILTERFACTORY;
````

## Members


## Remarks
A filter factory explicitly represents a device's ability to instantiate a given type of filter as described by a filter descriptor.

Drivers for hardware typically use this structure to manage a particular function of the hardware that is exposed as a type of filter. Software filters generally do not need to manage the device at this level.

Filter factory objects are created in two ways. They can be created during the AddDevice processing as indicated by the device descriptor's list of filter descriptors. They can also be created explicitly by the client in a call to <a href="..\ks\nf-ks-kscreatefilterfactory.md">KsCreateFilterFactory</a>. The client may create filter factories at any time, but this is typically done during the processing of the PnP start IRP when an evaluation of assigned resources indicates what types of filters must be exposed by the device.

For the purposes of synchronization, the lifetime of filter factories created implicitly is defined as the interval starting when the client's device create dispatch function is (or would be) called and ending after the client's device PnP remove dispatch function is (or would be) called. The lifetime of filter factories created explicitly by calling <a href="..\ks\nf-ks-kscreatefilterfactory.md">KsCreateFilterFactory</a> starts immediately after that call returns.

Also see <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions. Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions. |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\nf-ks-kscreatefilterfactory.md">KsCreateFilterFactory</a>

<a href="..\ks\ns-ks-_ksfilter_descriptor.md">KSFILTER_DESCRIPTOR</a>

<a href="..\ks\nf-ks-ksadditemtoobjectbag.md">KsAddItemToObjectBag</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSFILTERFACTORY structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>