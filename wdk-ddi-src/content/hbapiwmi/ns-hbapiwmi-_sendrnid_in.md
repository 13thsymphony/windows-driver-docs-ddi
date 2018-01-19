---
UID : NS:hbapiwmi._SendRNID_IN
title : _SendRNID_IN
author : windows-driver-content
description : The SendRNID_IN structure is used to deliver input parameter data to the SendRNID WMI method.
old-location : storage\sendrnid_in.htm
old-project : storage
ms.assetid : 668c4d1a-52e8-49ea-bd19-e789dfa8dfa5
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _SendRNID_IN, *PSendRNID_IN, SendRNID_IN
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : hbapiwmi.h
req.include-header : Hbapiwmi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SendRNID_IN
req.alt-loc : hbapiwmi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PSendRNID_IN, SendRNID_IN"
---

# _SendRNID_IN structure
The SendRNID_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565459">SendRNID</a> WMI method.

## Syntax
````
typedef struct _SendRNID_IN {
  UCHAR wwn[8];
  ULONG wwntype;
} SendRNID_IN, *PSendRNID_IN;
````

## Members

        
            `wwn`

            Contains a worldwide name for the port to which the request node identification data (RNID) command is sent.
        
            `wwntype`

            Deprecated. Do not use.

    ## Remarks
        The WMI tool suite generates a declaration of the SendRNID_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565459">SendRNID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendRNID_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>