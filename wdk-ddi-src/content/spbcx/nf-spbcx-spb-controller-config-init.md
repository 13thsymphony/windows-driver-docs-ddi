---
UID: NF.spbcx.SPB_CONTROLLER_CONFIG_INIT
title: SPB_CONTROLLER_CONFIG_INIT
author: windows-driver-content
description: The SPB_CONTROLLER_CONFIG_INIT function initializes an SPB_CONTROLLER_CONFIG structure.
old-location: spb\spb_controller_config_init.htm
old-project: SPB
ms.assetid: 78D46903-A13D-4BC2-803F-E1656A43E865
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SPB_CONTROLLER_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: spbcx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SPB_CONTROLLER_CONFIG_INIT
req.alt-loc: Spbcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any IRQL
req.iface: 
req.product: Windows 10 or later.
---

# SPB_CONTROLLER_CONFIG_INIT function



## -description
<p>The <b>SPB_CONTROLLER_CONFIG_INIT</b> function initializes an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406206">SPB_CONTROLLER_CONFIG</a> structure.</p>


## -syntax

````
VOID SPB_CONTROLLER_CONFIG_INIT(
  _Out_ SPB_CONTROLLER_CONFIG *Config
);
````


## -parameters
<dl>

### -param Config [out]

<dd>
<p>A pointer to the <b>SPB_CONTROLLER_CONFIG</b> structure that is to be initialized.</p>
</dd>
</dl>

## -returns
<p>None.</p>

## -remarks
<p>Your SPB controller driver must use this function to initialize an <b>SPB_CONTROLLER_CONFIG</b> structure before passing this structure as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a> method. This method completes the initialization of the SPB framework extension (SpbCx).</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Spbcx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any IRQL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406206">SPB_CONTROLLER_CONFIG</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_CONTROLLER_CONFIG_INIT function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
