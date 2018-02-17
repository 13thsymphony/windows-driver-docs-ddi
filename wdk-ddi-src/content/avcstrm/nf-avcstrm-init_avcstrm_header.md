---
UID: NF:avcstrm.INIT_AVCSTRM_HEADER
title: INIT_AVCSTRM_HEADER macro
author: windows-driver-content
description: The INIT_AVCSTRM_HEADER macro initializes the SizeOfThisBlock, Version and Function members of the AVC_STREAM_REQUEST_BLOCK structure.
old-location: stream\init_avcstrm_header.htm
old-project: stream
ms.assetid: 744d6e49-9321-4cba-a4e7-48a4abb02319
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: avcsref_97f7d983-5637-4ac4-ad1c-53328adca831.xml, avcstrm/INIT_AVCSTRM_HEADER, stream.init_avcstrm_header, INIT_AVCSTRM_HEADER macro [Streaming Media Devices], INIT_AVCSTRM_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: avcstrm.h
req.include-header: Avcstrm.h
req.target-type: Desktop
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
req.lib: avcstrm.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	avcstrm.h
apiname:
-	INIT_AVCSTRM_HEADER
product: Windows
targetos: Windows
req.typenames: AVCSTRM_FUNCTION
---


# INIT_AVCSTRM_HEADER function
The <b>INIT_AVCSTRM_HEADER</b> macro initializes the <b>SizeOfThisBlock</b>, <b>Version</b> and <b>Function</b> members of the <a href="..\avcstrm\ns-avcstrm-_avc_stream_request_block.md">AVC_STREAM_REQUEST_BLOCK</a> structure.

## Syntax

````
VOID INIT_AVCSTRM_HEADER(
  [in] PAVC_STREAM_REQUEST_BLOCK AVCStrm,
  [in] AVCSTRM_FUNCTION          Request
);
````

## Parameters

`AVCStrm`

Points to a caller-allocated AVC_STREAM_REQUEST_BLOCK structure.

`Request`

Indicates the type of the request (function code) from the <a href="..\avcstrm\ne-avcstrm-_avcstrm_function.md">AVCSTRM_FUNCTION</a> enumeration. Each function code is documented under the <a href="..\avcstrm\ni-avcstrm-ioctl_avcstrm_class.md">IOCTL_AVCSTRM_CLASS</a> topic.


## Return Value

None

## Remarks

The macro is defined as follows:

<pre class="syntax" xml:space="preserve"><code>#define INIT_AVCSTRM_HEADER( AVCStrm, Request )             \
        (AVCStrm)-&gt;SizeOfThisBlock = sizeof(AVC_STREAM_REQUEST_BLOCK); \
        (AVCStrm)-&gt;Function = Request;                    \
        (AVCStrm)-&gt;Version  = CURRENT_AVCSTRM_DDI_VERSION;</code></pre>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | avcstrm.h (include Avcstrm.h) |
| **Library** | avcstrm.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554110">AVCSTRM_CLOSE</a>



<a href="..\avcstrm\ns-avcstrm-_avc_stream_request_block.md">AVC_STREAM_REQUEST_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554134">AVCSTRM_SET_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554107">AVCSTRM_ABORT_STREAMING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554135">AVCSTRM_WRITE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554125">AVCSTRM_OPEN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554132">AVCSTRM_SET_PROPERTY</a>



<a href="..\avcstrm\ni-avcstrm-ioctl_avcstrm_class.md">IOCTL_AVCSTRM_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554124">AVCSTRM_GET_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554130">AVCSTRM_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554121">AVCSTRM_GET_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20INIT_AVCSTRM_HEADER macro%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>