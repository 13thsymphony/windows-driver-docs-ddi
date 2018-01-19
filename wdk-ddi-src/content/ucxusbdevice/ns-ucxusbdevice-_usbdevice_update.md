---
UID : NS:ucxusbdevice._USBDEVICE_UPDATE
title : _USBDEVICE_UPDATE
author : windows-driver-content
description : Passed by UCX to update the specified device. This structure is in the request parameters (Parameters.Others.Arg1) of a framework request object passed in the EVT_UCX_USBDEVICE_UPDATE callback function.
old-location : buses\_usbdevice_update.htm
old-project : usbref
ms.assetid : 7E990E9A-5BF5-4D6B-A5E2-4968FBD1CEBC
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _USBDEVICE_UPDATE, USBDEVICE_UPDATE, *PUSBDEVICE_UPDATE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ucxusbdevice.h
req.include-header : Ucxclass.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : USBDEVICE_UPDATE
req.alt-loc : ucxusbdevice.h
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
req.typenames : USBDEVICE_UPDATE, *PUSBDEVICE_UPDATE
req.product : Windows 10 or later.
---

# _USBDEVICE_UPDATE structure
Passed by UCX to update the specified device. This structure is in the request parameters (<b>Parameters.Others.Arg1</b>) of a framework request object passed in the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_update.md">EVT_UCX_USBDEVICE_UPDATE</a> callback function.

## Syntax
````
typedef struct _USBDEVICE_UPDATE {
#if _cplusplus
  USBDEVICE_MGMT_HEADER                       Header;
#else 
                                              USBDEVICE_MGMT_HEADER;
#endif 
  USBDEVICE_UPDATE_FLAGS                      Flags;
  PUSB_DEVICE_DESCRIPTOR                      DeviceDescriptor;
  USB_BOS_DESCRIPTOR                          BosDescriptor;
  ULONG                                       MaxExitLatency;
  BOOLEAN                                     IsHub;
  USBDEVICE_UPDATE_FAILURE_FLAGS              FailureFlags;
  USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS Usb20HardwareLpmParameters;
  USHORT                                      RootPortResumeTime;
#endif 
} USBDEVICE_UPDATE, *P_USBDEVICE_UPDATE;
````

## Members

        
            `BosDescriptor`

            A pointer a <b>USB_BOS_DESCRIPTOR</b> structure that contains the device descriptor. See Usbspec.h.
        
            `DeviceDescriptor`

            A pointer a <a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a> structure that contains the device descriptor.
        
            `FailureFlags`

            A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_failure_flags.md">USBDEVICE_UPDATE_FAILURE_FLAGS</a> structure that indicates the errors, if any, that occurred during the update operation.
        
            `Flags`

            A bitwise-OR of <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_flags.md">USBDEVICE_UPDATE_FLAGS</a> values that indicates the attributes that must be updated by the client driver.
        
            `Header`

            A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.
        
            `IsHub`

            Indicates if the USB device to update is a USB hub (TRUE) or not (FALSE).
        
            `MaxExitLatency`

            The maximum exit latency period.
        
            `RootPortResumeTime`

            The resume time for the root port.
        
            `Usb20HardwareLpmParameters`

            A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_20_hardware_lpm_parameters.md">USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS</a>  structure that describes the Link Power Management (LPM) features.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ucxusbdevice.h (include Ucxclass.h) |

    ## See Also

        <dl>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>
</dt>
<dt>
<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_flags.md">USBDEVICE_UPDATE_FLAGS</a>
</dt>
<dt>
<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_failure_flags.md">USBDEVICE_UPDATE_FAILURE_FLAGS</a>
</dt>
<dt>
<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_20_hardware_lpm_parameters.md">USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBDEVICE_UPDATE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>