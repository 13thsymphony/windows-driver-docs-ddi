---
UID : NE:ntddsd.SD_REQUEST_FUNCTION
title : SD_REQUEST_FUNCTION
author : windows-driver-content
description : The SD_REQUEST_FUNCTION enumeration indicates the type of request packet that a Secure Digital (SD) card driver sends to the bus driver.
old-location : sd\sd_request_function.htm
old-project : SD
ms.assetid : 9eec7597-be3a-4811-8786-11de0f9ac3da
ms.author : windowsdriverdev
ms.date : 12/18/2017
ms.keywords : SD_REQUEST_FUNCTION, SD_REQUEST_FUNCTION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddsd.h
req.include-header : Ntddsd.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SD_REQUEST_FUNCTION
req.alt-loc : ntddsd.h
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
req.typenames : SD_REQUEST_FUNCTION
---

# SD_REQUEST_FUNCTION Enumeration
The SD_REQUEST_FUNCTION enumeration indicates the type of request packet that a Secure Digital (SD) card driver sends to the bus driver.

## Syntax
````
typedef enum  { 
  SDRF_GET_PROPERTY    = 0,
  SDRF_SET_PROPERTY    = 1,
  SDRF_DEVICE_COMMAND  = 2
} SD_REQUEST_FUNCTION;
````

## Constants

<table>

<tr>
<td>SDRF_DEVICE_COMMAND</td>
<td>Indicates a device-specific command.</td>
</tr>

<tr>
<td>SDRF_GET_PROPERTY</td>
<td>Indicates a get property request. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff537927">SDBUS_PROPERTY</a> enumeration lists the properties that an SD driver can get or set.</td>
</tr>

<tr>
<td>SDRF_SET_PROPERTY</td>
<td>Indicates a set property request. The SDBUS_PROPERTY enumeration lists the properties that an SD driver can get or set.</td>
</tr>
</table>

## Remarks

The caller of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537909">SdBusSubmitRequest</a> routine assigns a value from the SD_REQUEST_FUNCTION enumeration to the <b>RequestFunction</b> member of the <a href="https://msdn.microsoft.com/09b30bf0-fe85-4ad5-bd3e-113ed3a093ac">SDBUS_REQUEST_PACKET</a> structure to specify the type of request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddsd.h (include Ntddsd.h) |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/09b30bf0-fe85-4ad5-bd3e-113ed3a093ac">SDBUS_REQUEST_PACKET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537909">SdBusSubmitRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SD\buses]:%20SD_REQUEST_FUNCTION enumeration%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>