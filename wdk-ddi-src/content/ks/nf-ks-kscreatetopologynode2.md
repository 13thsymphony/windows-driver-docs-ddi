---
UID: NF:ks.KsCreateTopologyNode2
title: KsCreateTopologyNode2 function
author: windows-driver-content
description: Creates a handle to a topology node instance.
old-location: stream\kscreatetopologynode2.htm
old-project: stream
ms.assetid: 71a45396-0b23-4a20-a4f4-25355a1f6271
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsCreateTopologyNode2 function [Streaming Media Devices], stream.kscreatetopologynode2, KsCreateTopologyNode2, ks/KsCreateTopologyNode2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ks.h
apiname:
-	KsCreateTopologyNode2
product: Windows
targetos: Windows
req.typenames: 
---


# KsCreateTopologyNode2 function
Creates a handle to a topology node instance.

Supported starting in Windows 8.

## Syntax

````
KSDDKAPI HRESULT WINAPI KsCreateTopologyNode2(
  _In_  HANDLE         ParentHandle,
  _In_  PKSNODE_CREATE NodeCreate,
  _In_  ACCESS_MASK    DesiredAccess,
  _Out_ PHANDLE        NodeHandle
);
````

## Parameters

`ParentHandle`

Specifies the handle to the parent on which the node is created.

`NodeCreate`

A <a href="..\ks\ns-ks-ksnode_create.md">KSNODE_CREATE</a> structure that describes the set of information that is used to create the topology node handle.

`DesiredAccess`

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> indicating the desired access to the object. This is typically <b>GENERIC_READ</b> and/or <b>GENERIC_WRITE</b>.

`NodeHandle`

Location for the topology node handle.


## Return Value

Returns <b>NOERROR</b> if successful; otherwise, returns an error code.

## Remarks

This is a new version of the <a href="..\ks\nf-ks-kscreatetopologynode.md">KsCreateTopologyNode</a> function and uses the device broker to create the handle to the kernel streaming object. In addition, the Component Object Model (COM) <a href="https://msdn.microsoft.com/0f171cf4-87b9-43a6-97f2-80ed344fe376">CoInitialize</a> function must be called before this function is called.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\ns-ks-ksnode_create.md">KSNODE_CREATE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>

<a href="https://msdn.microsoft.com/0f171cf4-87b9-43a6-97f2-80ed344fe376">CoInitialize</a>

<a href="..\ks\nf-ks-kscreatetopologynode.md">KsCreateTopologyNode</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsCreateTopologyNode2 function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>