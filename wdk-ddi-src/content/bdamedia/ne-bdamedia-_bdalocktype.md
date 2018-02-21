---
UID: NE:bdamedia._BdaLockType
title: "_BdaLockType"
author: windows-driver-content
description: The BDA_LockType enumerated type contains values that specify lock types for a signal.
old-location: stream\bda_locktype.htm
old-project: stream
ms.assetid: 6119727a-05af-4a70-a321-5f0f2e439b93
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: bdamedia/Bda_LockType_PLL, BDA_LockType enumeration [Streaming Media Devices], stream.bda_locktype, Bda_LockType_PLL, bdaref_46e4b273-15bc-47bc-a14b-2a6be1cc3c0f.xml, Bda_LockType_DecoderDemod, BDA_LockType, Bda_LockType_None, bdamedia/Bda_LockType_DecoderDemod, _BdaLockType, bdamedia/Bda_LockType_None, Bda_LockType_Complete, bdamedia/Bda_LockType_Complete, bdamedia/BDA_LockType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bdamedia.h
req.include-header: Bdamedia.h
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
-	bdamedia.h
apiname:
-	BDA_LockType
product: Windows
targetos: Windows
req.typenames: BDA_LockType
---

# _BdaLockType Enumeration
The BDA_LockType enumerated type contains values that specify lock types for a signal.

## Syntax
````
typedef enum _BdaLockType { 
  Bda_LockType_None          = 0x00,
  Bda_LockType_PLL           = 0x01,
  Bda_LockType_DecoderDemod  = 0x02,
  Bda_LockType_Complete      = 0x80
} BDA_LockType;
````

## Constants

<table>
            
                <tr>
                    <td>Bda_LockType_Complete</td>
                    <td>To be supplied.</td>
                </tr>
            
                <tr>
                    <td>Bda_LockType_DecoderDemod</td>
                    <td>The driver supports a decoder-demodulator lock.</td>
                </tr>
            
                <tr>
                    <td>Bda_LockType_None</td>
                    <td>The driver does not support any lock types.</td>
                </tr>
            
                <tr>
                    <td>Bda_LockType_PLL</td>
                    <td>The driver supports a phase-lock-loop (PLL) lock.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdamedia.h (include Bdamedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564369">KSPROPERTY_BDA_SIGNAL_LOCK_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564370">KSPROPERTY_BDA_SIGNAL_LOCK_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BDA_LockType enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>