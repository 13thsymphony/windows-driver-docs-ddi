---
UID: NE:ksmedia.KSEVENT_CAMERACONTROL
title: KSEVENT_CAMERACONTROL
author: windows-driver-content
description: Specifies camera control event notifications that the driver generates to indicate that an operation has been completed or canceled.
old-location: stream\ksevent_cameracontrol.htm
old-project: stream
ms.assetid: 10d08e58-cd1f-4585-a93b-fabeb4fcf27c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KSEVENT_CAMERACONTROL, KSEVENT_CAMERACONTROL enumeration [Streaming Media Devices], KSEVENT_CAMERACONTROL_FOCUS, KSEVENT_CAMERACONTROL_ZOOM, ksmedia/KSEVENT_CAMERACONTROL, ksmedia/KSEVENT_CAMERACONTROL_FOCUS, ksmedia/KSEVENT_CAMERACONTROL_ZOOM, stream.ksevent_cameracontrol
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	Ksmedia.h
api_name:
-	KSEVENT_CAMERACONTROL
product: Windows
targetos: Windows
req.typenames: KSEVENT_CAMERACONTROL
---

# KSEVENT_CAMERACONTROL Enumeration
Specifies camera control event notifications that the driver generates to indicate that an operation has been completed or canceled.

## Syntax
````
typedef enum  { 
  KSEVENT_CAMERACONTROL_FOCUS  = 0,
  KSEVENT_CAMERACONTROL_ZOOM   = 1
} KSEVENT_CAMERACONTROL;
````

## Constants

<table>
            
                <tr>
                    <td>KSEVENT_CAMERACONTROL_FOCUS</td>
                    <td>A camera focus operation has completed or has been canceled. See <a href="https://msdn.microsoft.com/library/windows/hardware/jj156037">KSEVENT_CAMERACONTROL_FOCUS</a>.</td>
                </tr>
            
                <tr>
                    <td>KSEVENT_CAMERACONTROL_ZOOM</td>
                    <td>A camera zoom operation has completed or has been canceled. See <a href="https://msdn.microsoft.com/library/windows/hardware/jj156038">KSEVENT_CAMERACONTROL_ZOOM</a>.</td>
                </tr>
</table>

## Remarks

For more information, see <a href="..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_s_ex.md">KSPROPERTY_CAMERACONTROL_S_EX</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj156038">KSEVENT_CAMERACONTROL_ZOOM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj156037">KSEVENT_CAMERACONTROL_FOCUS</a>



<a href="..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_s_ex.md">KSPROPERTY_CAMERACONTROL_S_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSEVENT_CAMERACONTROL enumeration%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>