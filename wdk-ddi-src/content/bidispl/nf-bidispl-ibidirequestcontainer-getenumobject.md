---
UID : NF:bidispl.IBidiRequestContainer.GetEnumObject
title : IBidiRequestContainer::GetEnumObject method
author : windows-driver-content
description : The IBidiRequestContainer::GetEnumObject method enumerates the bidi requests in a list.
old-location : print\ibidirequestcontainer_ibidirequestcontainer__getenumobject.htm
old-project : print
ms.assetid : 1aa7b934-c56b-4bfb-800e-950e1dbd5ba3
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : IBidiRequestContainer::IBidiRequestContainer::GetEnumObject, IBidiRequestContainer::GetEnumObject method [Print Devices], IBidiRequestContainer interface [Print Devices], IBidiRequestContainer::GetEnumObject method, _win32_IBidiRequestContainer_GetEnumObject, IBidiRequestContainer::GetEnumObject method [Print Devices], IBidiRequestContainer interface, GetEnumObject, bidispl/IBidiRequestContainer::IBidiRequestContainer::GetEnumObject, gdi.ibidirequestcontainer_ibidirequestcontainer__getenumobject, IBidiRequestContainer::GetEnumObject, IBidiRequestContainer, print.ibidirequestcontainer_ibidirequestcontainer__getenumobject
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : bidispl.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Windows XP
req.target-min-winversvr : Windows Server 2003
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : bidispl.h
req.dll : Bidispl.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
-	IBidiRequestContainer.IBidiRequestContainer::GetEnumObject
product : Windows
targetos : Windows
req.typenames : "*PMPEG2_TRANSPORT_STRIDE, MPEG2_TRANSPORT_STRIDE"
---


# GetEnumObject method
The <b>IBidiRequestContainer::GetEnumObject</b> method enumerates the bidi requests in a list.

## Syntax

````
HRESULT IBidiRequestContainer::GetEnumObject(
  [out] IEnumUnknown **ppenum
);
````

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

An application can call <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/ms693367">IEnumUnknown::Next</a> to retrieve one or more <a href="..\bidispl\nn-bidispl-ibidirequest.md">IBidiRequest</a> interfaces.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Windows XP |
| **Target Platform** | Desktop |
| **Header** | bidispl.h |
| **Library** | bidispl.h |
| **DLL** | Bidispl.dll |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/desktop/ms683764">IEnumUnknown</a>

<a href="..\bidispl\nn-bidispl-ibidirequestcontainer.md">IBidiRequestContainer</a>

<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiRequestContainer::IBidiRequestContainer::GetEnumObject method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>