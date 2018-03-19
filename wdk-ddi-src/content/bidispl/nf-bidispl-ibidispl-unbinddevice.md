---
UID: NF:bidispl.IBidiSpl.UnbindDevice
title: IBidiSpl::UnbindDevice method
author: windows-driver-content
description: The UnbindDevice method unbinds a printer from a bidi request.
old-location: print\ibidispl_ibidispl__unbinddevice.htm
old-project: print
ms.assetid: 4c294d1d-5a37-4ea4-b50f-447260e885b1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IBidiSpl, IBidiSpl interface [Print Devices], UnbindDevice method, IBidiSpl::UnbindDevice, UnbindDevice method [Print Devices], UnbindDevice method [Print Devices], IBidiSpl interface, UnbindDevice,IBidiSpl.UnbindDevice, _win32_IBidiSpl_UnbindDevice, bidispl/IBidiSpl::UnbindDevice, gdi.ibidispl_ibidispl__unbinddevice, print.ibidispl_ibidispl__unbinddevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: bidispl.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
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
req.dll: Bidispl.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	bidispl.dll
api_name:
-	IBidiSpl.UnbindDevice
product: Windows
targetos: Windows
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---


# UnbindDevice method
The <b>UnbindDevice</b> method unbinds a printer from a bidi request.

## Syntax

````
HRESULT UnbindDevice();
````

## Parameters

This function has no parameters.

## Return Value

The method returns one of the following values. For more information about COM error codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544310">Error Handling</a>.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation was successfully carried out.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The interface handle was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>None of the above</b></dt>
</dl>
</td>
<td width="60%">
The <b>HRESULT</b> contains an error code corresponding to the last error.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Windows Server 2003 |
| **Target Platform** | Desktop |
| **Header** | bidispl.h |
| **DLL** | Bidispl.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>



<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>



<a href="..\bidispl\nn-bidispl-ibidispl.md">IBidiSpl</a>