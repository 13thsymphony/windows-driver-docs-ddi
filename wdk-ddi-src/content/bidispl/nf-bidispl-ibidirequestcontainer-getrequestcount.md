---
UID : NF:bidispl.IBidiRequestContainer.GetRequestCount
title : IBidiRequestContainer::GetRequestCount method
author : windows-driver-content
description : The IBidiRequestContainer::GetRequestCount method gets the number of requests in the request list.
old-location : print\ibidirequestcontainer_ibidirequestcontainer__getrequestcount.htm
old-project : print
ms.assetid : 4215ca86-9ceb-451d-8e67-992a8a3f9bab
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : IBidiRequestContainer::GetRequestCount, gdi.ibidirequestcontainer_ibidirequestcontainer__getrequestcount, IBidiRequestContainer interface [Print Devices], IBidiRequestContainer::GetRequestCount method, IBidiRequestContainer::GetRequestCount method [Print Devices], IBidiRequestContainer interface, print.ibidirequestcontainer_ibidirequestcontainer__getrequestcount, IBidiRequestContainer, GetRequestCount, _win32_IBidiRequestContainer_GetRequestCount, bidispl/IBidiRequestContainer::IBidiRequestContainer::GetRequestCount, IBidiRequestContainer::GetRequestCount method [Print Devices], IBidiRequestContainer::IBidiRequestContainer::GetRequestCount
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
product : Windows
targetos : Windows
req.typenames : MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---


# GetRequestCount method
The <b>IBidiRequestContainer::GetRequestCount</b> method gets the number of requests in the request list.

## Syntax

````
HRESULT IBidiRequestContainer::GetRequestCount(
  [out] ULONG *puCount
);
````

## Parameters

`puCount`

Pointer to a variable that receives the number of requests.


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
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bidispl.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\bidispl\nn-bidispl-ibidirequestcontainer.md">IBidiRequestContainer</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>

<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiRequestContainer::IBidiRequestContainer::GetRequestCount method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>