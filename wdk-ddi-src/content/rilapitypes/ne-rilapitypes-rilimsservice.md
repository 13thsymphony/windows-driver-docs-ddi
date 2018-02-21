---
UID: NE:rilapitypes.RILIMSSERVICE
title: RILIMSSERVICE
author: windows-driver-content
description: The RILIMSSERVICE enumeration has the following values.
old-location: netvista\rilimsservice.htm
old-project: netvista
ms.assetid: 11d009d7-5a97-46a8-b1d6-f1906127bf3a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILIMSSERVICE enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_IMS_SERVICE_SMS, RIL_IMS_SERVICE_SMS, rilapitypes/RIL_IMS_SERVICE_ALL, RIL_IMS_SERVICE_VIDEO, RILIMSSERVICE, RIL_IMS_SERVICE_ALL, netvista.rilimsservice, RIL_IMS_SERVICE_VOICE, RIL_IMS_SERVICE_CUSTOM, rilapitypes/RILIMSSERVICE, rilapitypes/RIL_IMS_SERVICE_CUSTOM, rilapitypes/RIL_IMS_SERVICE_VOICE, rilapitypes/RIL_IMS_SERVICE_VIDEO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILIMSSERVICE
product: Windows
targetos: Windows
req.typenames: RILIMSSERVICE
req.product: Windows 10 or later.
---

# RILIMSSERVICE Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>The RILIMSSERVICE enumeration has the following values.

## Syntax
````
enum RILIMSSERVICE  {
  RIL_IMS_SERVICE_SMS     = 0x00000001, 
  RIL_IMS_SERVICE_VOICE   = 0x00000002, 
  RIL_IMS_SERVICE_VIDEO   = 0x00000004, 
  RIL_IMS_SERVICE_CUSTOM  = 0x00000008, 
  RIL_IMS_SERVICE_ALL     = 0x0000000F  

};
````

## Constants

<table>
            
                <tr>
                    <td>RIL_IMS_SERVICE_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMS_SERVICE_CUSTOM</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMS_SERVICE_E_VOICE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMS_SERVICE_RCS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMS_SERVICE_SMS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMS_SERVICE_SUPSVC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMS_SERVICE_USSD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMS_SERVICE_VIDEO</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_IMS_SERVICE_VOICE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILIMSSERVICE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>