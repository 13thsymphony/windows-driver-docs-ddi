---
UID: NS.TCPXCV._DELETE_PORT_DATA_1
title: _DELETE_PORT_DATA_1
author: windows-driver-content
description: The XcvData function uses a DELETE_PORT_DATA_1 structure when it deletes a port.
old-location: print\delete_port_data_1.htm
old-project: print
ms.assetid: d4fb5bf9-7982-4abd-91ba-59b7798a18c7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _DELETE_PORT_DATA_1, DELETE_PORT_DATA_1, *PDELETE_PORT_DATA_1, PDELETE_PORT_DATA_1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: tcpxcv.h
req.include-header: Tcpxcv.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DELETE_PORT_DATA_1
req.alt-loc: tcpxcv.h
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
req.product: Windows 10 or later.
---

# _DELETE_PORT_DATA_1 structure



## -description
The <a href="print.xcvdata">XcvData</a> function uses a DELETE_PORT_DATA_1 structure when it deletes a port.



## -syntax

````
typedef struct _DELETE_PORT_DATA_1 {
  WCHAR psztPortName[MAX_PORTNAME_LEN];
  BYTE  Reserved[98];
  DWORD dwVersion;
  DWORD dwReserved;
} DELETE_PORT_DATA_1, *PDELETE_PORT_DATA_1;
````


## -struct-fields

### -field psztPortName

Specifies the name of the port to be deleted. The MAX_PORTNAME_LEN constant is defined in tcpxcv.h.


### -field Reserved

Is reserved for system use.


### -field dwVersion

Specifies the version of this structure, which is currently 1.


### -field dwReserved

Is obsolete, and must be set to 0.


## -remarks
When the <a href="print.xcvdata">XcvData</a> function is called to delete a port, its <i>pInputData</i> parameter must be set with the address of a DELETE_PORT_DATA_1 structure. Set this function's <i>pszDataName</i> parameter to the string L"DeletePort". 

See <a href="https://msdn.microsoft.com/7b2b1cff-ab8f-44e0-9327-dc60a0072bf5">TCPMON Xcv Interface</a> for more information.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Tcpxcv.h (include Tcpxcv.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.xcvdata">XcvData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DELETE_PORT_DATA_1 structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

