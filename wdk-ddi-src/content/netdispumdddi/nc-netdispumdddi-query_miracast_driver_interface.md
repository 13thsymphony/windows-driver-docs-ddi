---
UID: NC:netdispumdddi.QUERY_MIRACAST_DRIVER_INTERFACE
title: QUERY_MIRACAST_DRIVER_INTERFACE
author: windows-driver-content
description: Called by the operating system to query the Miracast user-mode driver interface, MIRACAST_DRIVER_INTERFACE.
old-location: display\querymiracastdriverinterface.htm
old-project: display
ms.assetid: a8833f8c-7e3f-422c-922e-e75476358ee9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: QUERY_MIRACAST_DRIVER_INTERFACE, QueryMiracastDriverInterface, QueryMiracastDriverInterface callback function [Display Devices], display.query_miracast_driver_interface, display.querymiracastdriverinterface, netdispumdddi/QueryMiracastDriverInterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Netdispumdddi.h
api_name:
-	QueryMiracastDriverInterface
product: Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---


# QUERY_MIRACAST_DRIVER_INTERFACE callback function
Called by the operating system to query the Miracast user-mode driver interface, <a href="..\netdispumdddi\ns-netdispumdddi-_miracast_driver_interface.md">MIRACAST_DRIVER_INTERFACE</a>.

## Syntax

```
QUERY_MIRACAST_DRIVER_INTERFACE QueryMiracastDriverInterface;

NTSTATUS QueryMiracastDriverInterface(
  UINT MiracastDriverInterfaceVersion,
  UINT MiracastDriverInterfaceSize,
  VOID *pMiracastDriverInterface
)
{...}
```

## Parameters

`MiracastDriverInterfaceVersion`

The version of the Miracast display interface, supplied by the operating system. 

This version is defined in Netdispumdddi.h as a <b>MIRACAST_DRIVER_INTERFACE_VERSION_XXX</b> value. For Windows 8.1, the value is <b>MIRACAST_DRIVER_INTERFACE_VERSION_1</b>.

`MiracastDriverInterfaceSize`

The size, supplied by the operating system, of the buffer pointed to by <i>pMiracastDriverInterface</i>.

`*pMiracastDriverInterface`

A pointer to a buffer, supplied by the operating system, that holds the returned Miracast display driver interface, which is a structure of type <a href="..\netdispumdddi\ns-netdispumdddi-_miracast_driver_interface.md">MIRACAST_DRIVER_INTERFACE</a>.


## Return Value

On success, this function returns <b>STATUS_SUCCESS</b>. Otherwise, the function returns an error code defined in the Ntstatus.h header.

## Remarks

When the Miracast user-mode driver is loaded, the operating system calls the <a href="https://msdn.microsoft.com/a0d7fc09-f888-4f46-a571-d3719a627597">GetProcAddress</a> function with "QueryMiracastDriverInterface" entered as the function name in the <i>lpProcName</i> parameter.

<div class="alert"><b>Note</b>  If the Miracast user-mode driver doesn't supply a function with this name, the operating system fails the Miracast display device.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | netdispumdddi.h (include Netdispumdddi.h) |

## See Also

<a href="..\netdispumdddi\ns-netdispumdddi-_miracast_driver_interface.md">MIRACAST_DRIVER_INTERFACE</a>



<a href="https://msdn.microsoft.com/a0d7fc09-f888-4f46-a571-d3719a627597">GetProcAddress</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20QUERY_MIRACAST_DRIVER_INTERFACE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>