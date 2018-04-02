---
UID: NC:ufxproprietarycharger.UFX_PROPRIETARY_CHARGER_DETECT
title: UFX_PROPRIETARY_CHARGER_DETECT
author: windows-driver-content
description: The filter driver's implementation to detect if a charger is attached and get details about the charger.
old-location: buses\ufx_proprietary_charger_detect.htm
old-project: usbref
ms.assetid: E95D2713-8F95-460E-9107-4793B002A6AC
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFN_UFX_PROPRIETARY_CHARGER_DETECT, PFN_UFX_PROPRIETARY_CHARGER_DETECT callback function pointer [Buses], UFX_PROPRIETARY_CHARGER_DETECT, UfxProprietaryChargerDetect, UfxProprietaryChargerDetect callback function [Buses], buses.ufx_proprietary_charger_detect, ufxproprietarycharger/UfxProprietaryChargerDetect
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ufxproprietarycharger.h
req.include-header: 
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ufxproprietarycharger.h
api_name:
-	PFN_UFX_PROPRIETARY_CHARGER_DETECT
product: Windows
targetos: Windows
req.typenames: UFX_ENDPOINT_CALLBACKS, *PUFX_ENDPOINT_CALLBACKS
req.product: Windows 10 or later.
---


# UFX_PROPRIETARY_CHARGER_DETECT callback function
The filter driver's implementation to detect if a charger is attached  and get details about the charger.

## Syntax

```
UFX_PROPRIETARY_CHARGER_DETECT UfxProprietaryChargerDetect;

NTSTATUS UfxProprietaryChargerDetect(
  PVOID Context,
  PUFX_PROPRIETARY_CHARGER DetectedCharger
)
{...}
```

## Parameters

`Context`

A pointer to a driver-defined context.

`DetectedCharger`

A pointer to a     <a href="https://msdn.microsoft.com/library/windows/hardware/mt187979">UFX_PROPRIETARY_CHARGER</a> structure that the driver fills with charger information.


## Return Value

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## Remarks

To support handling of proprietary chargers, the USB lower filter driver must publish support. During the publishing process, the driver also registers its implementation of this  callback function. For more information, see <a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>.

In this callback function, the driver assigns the charger a GUID and sets the minimum required Dx state when the device is connected for charging. 


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
UsbLowerFilter_ProprietaryChargerDetect(
    __in PVOID Context,
    __out PUFX_PROPRIETARY_CHARGER DetectedCharger
    )
{
    NTSTATUS Status = STATUS_SUCCESS;

    PPDCP_CONTEXT PdcpContext = NULL;


    PAGED_CODE();

    PdcpContext = DeviceGetUsbLowerFilterContext((WDFDEVICE)Context);


    // Clear our event
     KeClearEvent(&amp;PdcpContext&gt;AbortOperation);


    // Wait for a while
     Timeout.QuadPart = WDF_REL_TIMEOUT_IN_MS(PdcpContext&gt;DetectionDelayInms);

    Status = KeWaitForSingleObject(
        &amp;PdcpContext&gt;AbortOperation,
        Executive,
        KernelMode,
        FALSE,
        &amp;Timeout);

    switch (Status)
    {
    case STATUS_SUCCESS:

        // The abort event was set. Abort.

        Status = STATUS_REQUEST_ABORTED;
        break;

    case STATUS_TIMEOUT:

        // Timed out, detection has completed successfully.
        // Check if we want to fail this.

        if (PdcpContext&gt;RejectNextRequest)
        {
            PdcpContext-&gt;RejectNextRequest = FALSE;
            Status = STATUS_UNSUCCESSFUL;
        }
        else if (!PdcpContext-&gt;PdcpChargerAttached)
        {
            Status = STATUS_NOT_FOUND;
        }
        else
        {
            Status = STATUS_SUCCESS;
        }
        break;

    default:
        break;
    }

    if (NT_SUCCESS(Status))
    {
        PdcpContext-&gt;PdcpChargerDetected = TRUE;
        DetectedCharger-&gt;ChargerId = GUID_USBFN_PROPRIETARY_CHARGER;
        DetectedCharger-&gt;DxState = PowerDeviceD2;
    }

    return Status;
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ufxproprietarycharger.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>