---
UID: NE:avc._KSPIN_FLAG_AVC
title: "_KSPIN_FLAG_AVC"
author: windows-driver-content
description: The KSPIN_FLAG_AVC enumeration type is used for connection management and in the AVC_FUNCTION_GET_CONNECTINFO function code.
old-location: stream\kspin_flag_avc.htm
old-project: stream
ms.assetid: 45a85718-8997-4c54-b283-e26247866735
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: avcref_9fab0898-b113-4d2f-ae4a-8cc6b01217d9.xml, KSPIN_FLAG_AVC_PERMANENT, KSPIN_FLAG_AVCMASK, avc/KSPIN_FLAG_AVC_PCRONLY, _KSPIN_FLAG_AVC, avc/KSPIN_FLAG_AVC_PERMANENT, avc/KSPIN_FLAG_AVC_CONNECTED, stream.kspin_flag_avc, avc/KSPIN_FLAG_AVC, KSPIN_FLAG_AVC_FIXEDPCR, KSPIN_FLAG_AVC_CONNECTED, avc/KSPIN_FLAG_AVC_FIXEDPCR, KSPIN_FLAG_AVC, avc/KSPIN_FLAG_AVCMASK, KSPIN_FLAG_AVC_PCRONLY, KSPIN_FLAG_AVC enumeration [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	avc.h
apiname:
-	KSPIN_FLAG_AVC
product: Windows
targetos: Windows
req.typenames: KSPIN_FLAG_AVC
---

# _KSPIN_FLAG_AVC Enumeration
The KSPIN_FLAG_AVC enumeration type is used for connection management and in the <b>AVC_FUNCTION_GET_CONNECTINFO</b> function code.

## Syntax
````
typedef enum _KSPIN_FLAG_AVC { 
  KSPIN_FLAG_AVCMASK        = 0x03,
  KSPIN_FLAG_AVC_PERMANENT  = 0x01,
  KSPIN_FLAG_AVC_CONNECTED  = 0x02,
  KSPIN_FLAG_AVC_PCRONLY    = 0x04,
  KSPIN_FLAG_AVC_FIXEDPCR   = 0x08
} KSPIN_FLAG_AVC;
````

## Constants

<table>
            
                <tr>
                    <td>KSPIN_FLAG_AVC_CONNECTED</td>
                    <td>Part of the AV/C Connect Status bitmask. Represents a connection that is currently active, but not necessarily permanent.</td>
                </tr>
            
                <tr>
                    <td>KSPIN_FLAG_AVC_FIXEDPCR</td>
                    <td>Represents a permanent connection between a subunit plug and a unit (serial bus) plug. Specifying this flag implies KSPIN_FLAG_AVC_PERMANENT, although that bit is not set if this one is set.</td>
                </tr>
            
                <tr>
                    <td>KSPIN_FLAG_AVC_PCRONLY</td>
                    <td>No subunit plug control. Only unit input and output plugs are available, and this AVCPRECONNECTINFO structure represents one of them.</td>
                </tr>
            
                <tr>
                    <td>KSPIN_FLAG_AVC_PERMANENT</td>
                    <td>Part of the AV/C Connect Status bitmask. Represents a permanent connection between two subunits within the same unit.</td>
                </tr>
            
                <tr>
                    <td>KSPIN_FLAG_AVCMASK</td>
                    <td>The mask to isolate the AV/C defined bit flags</td>
                </tr>
</table>

## Remarks

These bit flags are used by the intersect handler to determine plug compatibility, as well as to indicate whether the intersect handler is responsible for obtaining a plug handle from <i>61883.sys</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | avc.h (include Avc.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554154">AVC_FUNCTION_GET_CONNECTINFO</a>



<a href="..\avc\nc-avc-pfnavcintersecthandler.md">AV/C Intersect Handler</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPIN_FLAG_AVC enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>