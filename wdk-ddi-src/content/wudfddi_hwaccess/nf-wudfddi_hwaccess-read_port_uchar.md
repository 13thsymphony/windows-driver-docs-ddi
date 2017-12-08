---
UID: NF.wudfddi_hwaccess.READ_PORT_UCHAR
title: READ_PORT_UCHAR function
author: windows-driver-content
description: The READ_PORT_UCHAR function reads a byte from the specified port address.
old-location: wdf\read_port_uchar.htm
old-project: wdf
ms.assetid: B72EDABF-B5A5-4887-A8D6-77F4047CEDA8
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: READ_PORT_UCHAR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfddi_hwaccess.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: READ_PORT_UCHAR
req.alt-loc: Wudfddi_hwaccess.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# READ_PORT_UCHAR function



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]
The <b>READ_PORT_UCHAR</b>  function reads a byte from the specified port address.


## -syntax

````
UCHAR READ_PORT_UCHAR(
  _In_ IWDFDevice3 *pDevice,
  _In_ PUCHAR      Port
);
````


## -parameters

### -param pDevice [in]

Specifies a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a> interface for the device object of the device to access.

### -param Port [in]

Specifies the port address, which must be a mapped memory range in I/O space.

## -returns
<b>READ_PORT_UCHAR</b> returns the byte that is read from the specified port address.

## -remarks
For more information, see <a href="wdf.reading_and_writing_to_device_registers_in_umdf_1_x_drivers">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.

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
End of support
</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
1.11
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wudfddi_hwaccess.h</dt>
</dl>
</td>
</tr>
</table>