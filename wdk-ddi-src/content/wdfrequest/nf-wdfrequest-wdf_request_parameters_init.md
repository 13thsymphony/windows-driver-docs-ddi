---
UID: NF:wdfrequest.WDF_REQUEST_PARAMETERS_INIT
title: WDF_REQUEST_PARAMETERS_INIT function
author: windows-driver-content
description: The WDF_REQUEST_PARAMETERS_INIT function initializes a WDF_REQUEST_PARAMETERS structure.
old-location: wdf\wdf_request_parameters_init.htm
old-project: wdf
ms.assetid: c4e83638-4931-460f-848b-ceb0f7a00afb
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_1c1e97cb-9ca1-473a-aa30-d39fdadbc726.xml, WDF_REQUEST_PARAMETERS_INIT, WDF_REQUEST_PARAMETERS_INIT function, kmdf.wdf_request_parameters_init, wdf.wdf_request_parameters_init, wdfrequest/WDF_REQUEST_PARAMETERS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	wdfrequest.h
api_name:
-	WDF_REQUEST_PARAMETERS_INIT
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WDF_REQUEST_PARAMETERS_INIT function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_PARAMETERS_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a> structure.

## Syntax

```
void WDF_REQUEST_PARAMETERS_INIT(
  PWDF_REQUEST_PARAMETERS Parameters
);
```

## Parameters

`Parameters`

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a> structure.


## Return Value

None

## Remarks

Drivers must call <b>WDF_REQUEST_PARAMETERS_INIT</b> to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a> structure before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549969">WdfRequestGetParameters</a>.

The <b>WDF_REQUEST_PARAMETERS_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a> structure and sets the structure's <b>Size</b> member.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a> structure and then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549969">WdfRequestGetParameters</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyEvtIoDefault(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request
    )
{
    WDF_REQUEST_PARAMETERS  params;

    WDF_REQUEST_PARAMETERS_INIT(&amp;params);

    WdfRequestGetParameters(
                            Request,
                            &amp;params
                            );
...
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfrequest.h (include Wdf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549969">WdfRequestGetParameters</a>