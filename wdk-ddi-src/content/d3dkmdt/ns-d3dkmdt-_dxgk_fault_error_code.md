---
UID: NS.D3DKMDT._DXGK_FAULT_ERROR_CODE
title: _DXGK_FAULT_ERROR_CODE
author: windows-driver-content
description: The DXGK_FAULT_ERROR_CODE structure provides a status code for the graphics processing unit (GPU) error reported via a page fault interrupt.
old-location: display\dxgk_fault_error_code.htm
old-project: display
ms.assetid: 753FC177-D430-40E5-98CD-B3BDFD47ACEF
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGK_FAULT_ERROR_CODE, DXGK_FAULT_ERROR_CODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_FAULT_ERROR_CODE
req.alt-loc: D3dkmdt.h
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
---

# _DXGK_FAULT_ERROR_CODE structure



## -description
The <b>DXGK_FAULT_ERROR_CODE</b> structure provides a status code for the graphics processing unit (GPU) error reported via a page fault interrupt.


## -syntax

````
typedef struct _DXGK_FAULT_ERROR_CODE {
  union {
    struct {
      UINT                    IsDeviceSpecificCode  :1;
      DXGK_GENERAL_ERROR_CODE GeneralErrorCode  :31;
    };
    struct {
      UINT IsDeviceSpecificCodeReservedBit  :1;
      UINT DeviceSpecificCode  :31;
    };
  };
} DXGK_FAULT_ERROR_CODE;
````


## -struct-fields

### -field IsDeviceSpecificCode

When set, this indicates that the GPU error code is specific to the particular vendor. In this case, <b>DeviceSpecificCode</b> should be set to a vendor specific error code.
When not set, this indicates that the GPU error can be described via a set of predefined values in <a href="display.dxgk_general_error_code">DXGK_GENERAL_ERROR_CODE</a> enumeration. <b>GeneralErrorCode</b> value should be set to the corresponding error code.

### -field GeneralErrorCode

General error code defined by <a href="display.dxgk_general_error_code">DXGK_GENERAL_ERROR_CODE</a>.

### -field IsDeviceSpecificCodeReservedBit

Same as <b>IsDeviceSpecificCode</b> member above:
When set, this indicates that the GPU error code is specific to the particular vendor. In this case, <b>DeviceSpecificCode</b> should be set to a vendor specific error code.
When not set, this indicates that the GPU error can be described via a set of predefined values in <a href="display.dxgk_general_error_code">DXGK_GENERAL_ERROR_CODE</a> enumeration. <b>GeneralErrorCode</b> value should be set to the corresponding error code.

### -field DeviceSpecificCode

A device specific error code.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmdt.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgk_general_error_code">DXGK_GENERAL_ERROR_CODE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_FAULT_ERROR_CODE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
