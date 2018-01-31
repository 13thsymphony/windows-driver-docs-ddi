---
UID : NF:bidispl.IBidiSpl2.SendRecvXMLString
title : IBidiSpl2::SendRecvXMLString method
author : windows-driver-content
description : The IBidiSpl2::SendRecvXMLString method sends a bidirectional printer communication request and receives the response as Unicode strings formatted in accordance with the Bidirectional Communication Schemas.
old-location : print\ibidispl2_ibidispl2__sendrecvxmlstring.htm
old-project : print
ms.assetid : 7d61402e-e248-4770-a828-9c266e528115
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : SendRecvXMLString, IBidiSpl2::SendRecvXMLString method [Print Devices], IBidiSpl2 interface, IBidiSpl2::SendRecvXMLString method [Print Devices], _win32_IBidiSpl2_SendRecvXMLString, IBidiSpl2::IBidiSpl2::SendRecvXMLString, IBidiSpl2 interface [Print Devices], IBidiSpl2::SendRecvXMLString method, IBidiSpl2::SendRecvXMLString, print.ibidispl2_ibidispl2__sendrecvxmlstring, IBidiSpl2, bidispl/IBidiSpl2::IBidiSpl2::SendRecvXMLString, gdi.ibidispl2_ibidispl2__sendrecvxmlstring
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : bidispl.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Windows Vista
req.target-min-winversvr : Windows Server 2008
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
-	IBidiSpl2.IBidiSpl2 : :SendRecvXMLString
product : Windows
targetos : Windows
req.typenames : "*PMPEG2_TRANSPORT_STRIDE, MPEG2_TRANSPORT_STRIDE"
---


# SendRecvXMLString method
The <b>IBidiSpl2::SendRecvXMLString</b> method sends a bidirectional printer communication request and receives the response as Unicode strings formatted in accordance with the <a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schemas</a>.

## Syntax

````
HRESULT IBidiSpl2::SendRecvXMLString(
  [in]  BSTR bstrRequest,
  [out] BSTR *pbstrResponse
);
````

## Parameters

`bstrRequest`

The bidi communication request as a Unicode string that complies with one of the <a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schemas</a>.

`pbstrResponse`

A pointer to the printer's response as a Unicode string that complies with one of the <a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schemas</a>.


## Return Value

The method returns one of the following values.
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
The operation was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The interface handle is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>None of the above</b></dt>
</dl>
</td>
<td width="60%">
The <b>HRESULT</b> contains an error code that corresponds to the last error.

</td>
</tr>
</table> 

Note that the <b>HRESULT</b> may contain a system error code that is defined in <a href="https://msdn.microsoft.com/e273f5eb-e4f4-4aa7-9ed9-b418eebc6144">Bidi Error Codes</a>.


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

<a href="..\bidispl\nn-bidispl-ibidispl2.md">IBidiSpl2</a>

<a href="https://msdn.microsoft.com/42b5e6cf-b434-4734-86f3-b3b9d15ea468">Print Spooler Components</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiSpl2::IBidiSpl2::SendRecvXMLString method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>