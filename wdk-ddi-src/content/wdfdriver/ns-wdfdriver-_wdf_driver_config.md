---
UID : NS:wdfdriver._WDF_DRIVER_CONFIG
title : _WDF_DRIVER_CONFIG
author : windows-driver-content
description : The WDF_DRIVER_CONFIG structure is an input parameter to WdfDriverCreate.
old-location : wdf\wdf_driver_config.htm
old-project : wdf
ms.assetid : 24197846-9664-4fc6-8578-5bcaf0e4a71c
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WDF_DRIVER_CONFIG, WDF_DRIVER_CONFIG, *PWDF_DRIVER_CONFIG
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdfdriver.h
req.include-header : Wdf.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.alt-api : WDF_DRIVER_CONFIG
req.alt-loc : wdfdriver.h
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
req.typenames : WDF_DRIVER_CONFIG, *PWDF_DRIVER_CONFIG
req.product : Windows 10 or later.
---

# _WDF_DRIVER_CONFIG structure
<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_DRIVER_CONFIG structure is an input parameter to <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>.

## Syntax
````
typedef struct _WDF_DRIVER_CONFIG {
  ULONG                     Size;
  PFN_WDF_DRIVER_DEVICE_ADD EvtDriverDeviceAdd;
  PFN_WDF_DRIVER_UNLOAD     EvtDriverUnload;
  ULONG                     DriverInitFlags;
  ULONG                     DriverPoolTag;
} WDF_DRIVER_CONFIG, *PWDF_DRIVER_CONFIG;
````

## Members

        
            `DriverInitFlags`

            A bitwise OR of one or more <a href="..\wdfdriver\ne-wdfdriver-_wdf_driver_init_flags.md">WDF_DRIVER_INIT_FLAGS</a>-typed values that identify driver initialization flags.
        
            `DriverPoolTag`

            (KMDF versions 1.5 and later.) A driver-defined pool tag that the framework will assign to all of the driver's pool allocations. Debuggers display this tag. For more information about specifying a pool tag, see the following Remarks section.
        
            `EvtDriverDeviceAdd`

            A pointer to a driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.
        
            `EvtDriverUnload`

            A pointer to a driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_unload.md">EvtDriverUnload</a> callback function.
        
            `Size`

            The size, in bytes, of this structure.

    ## Remarks
        Your driver can optionally specify a pool tag that the framework will assign to all of the driver's pool allocations. Drivers typically specify a character string of up to four characters, delimited by single quotation marks, in reverse order (for example, 'dcba'). The ASCII value of each character in the tag must be between 0 and 127.  

If <b>DriverPoolTag</b> is zero, the framework creates a default pool tag by using the first four characters of your driver's kernel-mode service name. If the service name begins with "WDF" (the name is not case sensitive and does not include the quotation marks), the next four characters are used. If fewer than four characters are available, "FxDr" is used. 

To initialize a WDF_DRIVER_CONFIG structure, drivers must call <a href="..\wdfdriver\nf-wdfdriver-wdf_driver_config_init.md">WDF_DRIVER_CONFIG_INIT</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdriver.h (include Wdf.h) |

    ## See Also

        <dl>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_unload.md">EvtDriverUnload</a>
</dt>
<dt>
<a href="..\wdfdriver\nf-wdfdriver-wdf_driver_config_init.md">WDF_DRIVER_CONFIG_INIT</a>
</dt>
<dt>
<a href="..\wdfdriver\ne-wdfdriver-_wdf_driver_init_flags.md">WDF_DRIVER_INIT_FLAGS</a>
</dt>
<dt>
<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DRIVER_CONFIG structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>