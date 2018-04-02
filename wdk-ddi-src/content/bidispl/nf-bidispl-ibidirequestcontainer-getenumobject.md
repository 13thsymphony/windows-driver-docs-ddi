---
UID: NF:bidispl.IBidiRequestContainer.GetEnumObject
title: IBidiRequestContainer::GetEnumObject method
author: windows-driver-content
description: The GetEnumObject method enumerates the bidi requests in a list.
old-location: print\ibidirequestcontainer_ibidirequestcontainer__getenumobject.htm
old-project: print
ms.assetid: 1aa7b934-c56b-4bfb-800e-950e1dbd5ba3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetEnumObject method [Print Devices], GetEnumObject method [Print Devices], IBidiRequestContainer interface, GetEnumObject,IBidiRequestContainer.GetEnumObject, IBidiRequestContainer, IBidiRequestContainer interface [Print Devices], GetEnumObject method, IBidiRequestContainer::GetEnumObject, _win32_IBidiRequestContainer_GetEnumObject, bidispl/IBidiRequestContainer::GetEnumObject, gdi.ibidirequestcontainer_ibidirequestcontainer__getenumobject, print.ibidirequestcontainer_ibidirequestcontainer__getenumobject
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
-	IBidiRequestContainer.GetEnumObject
product: Windows
targetos: Windows
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---


# IBidiRequestContainer::GetEnumObject method
The <b>GetEnumObject</b> method enumerates the bidi requests in a list.

## Syntax

```
HRESULT GetEnumObject(
  IEnumUnknown **ppenum
);
```

## Parameters

`ppenum`

Pointer to the variable that receives a pointer to the <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/ms683764">IEnumUnknown</a> interface that enumerates the bidi requests in the container.


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

## Remarks

An application can call <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/ms693367">IEnumUnknown::Next</a> to retrieve one or more <a href="https://msdn.microsoft.com/library/windows/hardware/dd144969">IBidiRequest</a> interfaces.

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



<a href="https://msdn.microsoft.com/library/windows/hardware/dd144970">IBidiRequestContainer</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/desktop/ms683764">IEnumUnknown</a>