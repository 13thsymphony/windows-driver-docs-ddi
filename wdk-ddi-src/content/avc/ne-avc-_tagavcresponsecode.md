---
UID: NE:avc._tagAvcResponseCode
title: "_tagAvcResponseCode"
author: windows-driver-content
description: The AvcResponseCode enumeration type is used to indicate the type of response received by a subunit driver from its AV/C subunit through AVC_FUNCTION_COMMAND or AVC_FUNCTION_SEND_RESPONSE function codes.
old-location: stream\avcresponsecode.htm
old-project: stream
ms.assetid: 81a0ff7f-60a0-437e-8db2-ac364000d580
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVC_RESPONSE_ACCEPTED, AVC_RESPONSE_CHANGED, AVC_RESPONSE_IMPLEMENTED, AVC_RESPONSE_INTERIM, AVC_RESPONSE_IN_TRANSITION, AVC_RESPONSE_NOTIMPL, AVC_RESPONSE_REJECTED, AVC_RESPONSE_STABLE, AvcResponseCode, AvcResponseCode enumeration [Streaming Media Devices], _tagAvcResponseCode, avc/AVC_RESPONSE_ACCEPTED, avc/AVC_RESPONSE_CHANGED, avc/AVC_RESPONSE_IMPLEMENTED, avc/AVC_RESPONSE_INTERIM, avc/AVC_RESPONSE_IN_TRANSITION, avc/AVC_RESPONSE_NOTIMPL, avc/AVC_RESPONSE_REJECTED, avc/AVC_RESPONSE_STABLE, avc/AvcResponseCode, avcref_28d2a6d6-4b1f-4b5e-af90-294da5dd14e5.xml, stream.avcresponsecode
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	avc.h
api_name:
-	AvcResponseCode
product:
- Windows
targetos: Windows
req.typenames: AvcResponseCode
---

# _tagAvcResponseCode Enumeration
The AvcResponseCode enumeration type is used to indicate the type of response received by a subunit driver from its AV/C subunit through <b>AVC_FUNCTION_COMMAND</b> or <b>AVC_FUNCTION_SEND_RESPONSE</b> function codes.

## Syntax
````
typedef enum _tagAvcResponseCode { 
  AVC_RESPONSE_NOTIMPL        = 0x08,
  AVC_RESPONSE_ACCEPTED       = 0x09,
  AVC_RESPONSE_REJECTED       = 0x0a,
  AVC_RESPONSE_IN_TRANSITION  = 0x0b,
  AVC_RESPONSE_STABLE         = 0x0c,
  AVC_RESPONSE_IMPLEMENTED    = 0x0c,
  AVC_RESPONSE_CHANGED        = 0x0d,
  AVC_RESPONSE_INTERIM        = 0x0f
} AvcResponseCode;
````

## Constants

<table>
            
                <tr>
                    <td>AVC_RESPONSE_NOTIMPL</td>
                    <td>Indicates the subunit does not support the specified control command.</td>
                </tr>
            
                <tr>
                    <td>AVC_RESPONSE_ACCEPTED</td>
                    <td>Indicates the subunit does implement the specified control command and that subunit state permits execution of the command. Note: Command execution may not have completed by the time the <b>AVC_RESPONSE_ACCEPTED</b> has been returned.</td>
                </tr>
            
                <tr>
                    <td>AVC_RESPONSE_REJECTED</td>
                    <td>Specifies a response indicating the command or request was rejected.</td>
                </tr>
            
                <tr>
                    <td>AVC_RESPONSE_IN_TRANSITION</td>
                    <td>Specifies a response indicating the command or request was accepted.</td>
                </tr>
            
                <tr>
                    <td>AVC_RESPONSE_STABLE</td>
                    <td>Indicates the subunit implements the command. Same meaning as AVC_RESPONSE_IMPLMENTED.</td>
                </tr>
            
                <tr>
                    <td>AVC_RESPONSE_IMPLEMENTED</td>
                    <td>Indicates the subunit implements the command. Same meaning as AVC_RESPONSE_STABLE.</td>
                </tr>
            
                <tr>
                    <td>AVC_RESPONSE_CHANGED</td>
                    <td>Indicates the subunit state has changed.</td>
                </tr>
            
                <tr>
                    <td>AVC_RESPONSE_INTERIM</td>
                    <td>Indicates the subunit is unable to respond with either <b>AVC_RESPONSE_ACCEPTED</b> or <b>AVC_RESPONSE_REJECTED</b> within the 100 millisecond timeframe for responses. The subunit will ultimately return a response frame with either a <b>AVC_RESPONSE_ACCEPTED</b> or <b>AVC_RESPONSE_REJECTED</b> code.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | avc.h (include Avc.h) |

## See Also

<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554170">AVC_FUNCTION_SEND_RESPONSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554150">AVC_FUNCTION_COMMAND</a>