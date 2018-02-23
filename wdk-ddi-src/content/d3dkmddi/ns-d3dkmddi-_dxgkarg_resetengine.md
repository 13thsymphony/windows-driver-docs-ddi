---
UID: NS:d3dkmddi._DXGKARG_RESETENGINE
title: "_DXGKARG_RESETENGINE"
author: windows-driver-content
description: Specifies a node within the physical display adapter that can be reset when the display port driver's GPU scheduler calls the DxgkDdiResetEngine function to request a reset operation.
old-location: display\dxgkarg_resetengine.htm
old-project: display
ms.assetid: a19eea7f-ceaf-47e0-b2dd-46511fcae66f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DXGKARG_RESETENGINE, display.dxgkarg_resetengine, DXGKARG_RESETENGINE structure [Display Devices], *INOUT_PDXGKARG_RESETENGINE, d3dkmddi/DXGKARG_RESETENGINE, _DXGKARG_RESETENGINE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmddi.h
apiname:
-	DXGKARG_RESETENGINE
product: Windows
targetos: Windows
req.typenames: DXGKARG_RESETENGINE
---

# _DXGKARG_RESETENGINE structure
Specifies a node within the physical display adapter that can be reset when the display port driver's GPU scheduler calls the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetengine.md">DxgkDdiResetEngine</a> function to request a reset operation.

## Syntax
````
typedef struct _DXGKARG_RESETENGINE {
  UINT NodeOrdinal;
  UINT EngineOrdinal;
  UINT LastAbortedFenceId;
} DXGKARG_RESETENGINE;
````

## Members


`EngineOrdinal`

[in] An index that defines the physical adapter in a linked display adapter (LDA) configuration that the node defined by <b>NodeOrdinal</b> belongs to.

`LastAbortedFenceId`

[out] The fence identifier for the last packet that was aborted in the middle of execution.

`NodeOrdinal`

[in] An index of a node within the physical adapter defined by   the <b>EngineOrdinal</b> member that is being reset in a call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetengine.md">DxgkDdiResetEngine</a>.

## Remarks
For more information, see <a href="https://msdn.microsoft.com/5BC4F94C-2B45-44E2-8BBF-B455BB864A29">TDR changes in Windows 8</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetengine.md">DxgkDdiResetEngine</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_RESETENGINE structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>