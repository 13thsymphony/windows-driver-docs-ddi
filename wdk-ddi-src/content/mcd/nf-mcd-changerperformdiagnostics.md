---
UID: NF:mcd.ChangerPerformDiagnostics
title: ChangerPerformDiagnostics function
author: windows-driver-content
description: ChangerPerformDiagnostics performs diagnostic tests on the changer device.
old-location: storage\changerperformdiagnostics.htm
old-project: storage
ms.assetid: 87767b2b-8ca3-4d19-8719-673562246a41
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ChangerPerformDiagnostics
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ChangerPerformDiagnostics
req.alt-loc: mcd.h
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
req.typenames: LAMP_INTENSITY_WHITE
---

# ChangerPerformDiagnostics function



## -description
<b>ChangerPerformDiagnostics</b> performs diagnostic tests on the changer device.



## -syntax

````
NTSTATUS ChangerPerformDiagnostics(
  _In_  PDEVICE_OBJECT                    DeviceObject,
  _Out_ PWMI_CHANGER_PROBLEM_DEVICE_ERROR ChangerDeviceError
);
````


## -parameters

### -param DeviceObject [in]

Pointer to the device object that represents the changer.


### -param ChangerDeviceError [out]

Pointer to the buffer of type <a href="..\wmidata\ns-wmidata-_wmi_changer_problem_device_error.md">WMI_CHANGER_PROBLEM_DEVICE_ERROR</a> in which the minidriver returns the diagnostic information.


## -returns
<b>ChangerPerformDiagnostics</b> returns the status returned by the system port driver or one of the following values:
      

STATUS_SUCCESS

STATUS_INSUFFICIENT_RESOURCES

STATUS_BUFFER_TOO_SMALL


## -remarks
<b>ChangerPerformDiagnostics</b> routine performs diagnostic tests on the changer device, and reports the problem to the caller. The kind of tests performed depends on the diagnostics support provided by the device. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Mcd.h (include Mcd.h or Ntddchgr.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wmidata\ns-wmidata-_wmi_changer_problem_device_error.md">WMI_CHANGER_PROBLEM_DEVICE_ERROR</a>
</dt>
<dt>
<a href="..\ntddchgr\ne-ntddchgr-_changer_device_problem_type.md">CHANGER_DEVICE_PROBLEM_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ChangerPerformDiagnostics function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

