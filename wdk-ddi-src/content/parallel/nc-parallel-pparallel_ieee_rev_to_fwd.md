---
UID: NC.parallel.PPARALLEL_IEEE_REV_TO_FWD
title: PPARALLEL_IEEE_REV_TO_FWD
author: windows-driver-content
description: The PPARALLEL_IEEE_REV_TO_FWD-typed callback routine changes the transfer mode from reverse to forward. The system-supplied bus driver for parallel ports supplies this routine.
old-location: parports\pparallel_ieee_rev_to_fwd.htm
old-project: parports
ms.assetid: 4c9c88bf-e7f9-484b-b476-0def92cf48b2
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RegisterOpRegionHandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: parallel.h
req.include-header: Parallel.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PPARALLEL_IEEE_REV_TO_FWD
req.alt-loc: parallel.h
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

# PPARALLEL_IEEE_REV_TO_FWD callback



## -description
The PPARALLEL_IEEE_REV_TO_FWD-typed callback routine changes the transfer mode from reverse to forward. The system-supplied bus driver for parallel ports supplies this routine.


## -prototype

````
typedef NTSTATUS ( *PPARALLEL_IEEE_REV_TO_FWD)(
  _In_ PVOID Context
);
````


## -parameters

### -param Context [in]

Pointer to a device extension of a parallel device's physical device object (<a href="wdkgloss.p#wdkgloss.pdo#wdkgloss.pdo"><i>PDO</i></a>).

## -returns
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The transfer mode was changed from reverse to forward.
<dl>
<dt><b>STATUS_<i>Xxx</i></b></dt>
</dl>An internal operation resulted in an NTSTATUS error.

 

## -remarks
To obtain a pointer to the system-supplied PPARALLEL_IEEE_REV_TO_FWD callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_parclass_connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a> request, which returns a <a href="parports.parclass_information">PARCLASS_INFORMATION</a> structure. The <b>IeeeRevToFwdMode</b> member of the PARCLASS_INFORMATION structure is a pointer to this callback.

If the device is connected and is in the forward mode, the PPARALLEL_IEEE_REV_TO_FWD callback returns without further processing. Otherwise, the PPARALLEL_IEEE_REV_TO_FWD callback puts a parallel device in the forward mode and connects a previously negotiated forward protocol. The <a href="..\parallel\nc-parallel-pnegotiate_ieee_mode.md">PNEGOTIATE_IEEE_MODE</a> callback can be used to negotiate a forward protocol.

The PPARALLEL_IEEE_REV_TO_FWD callback runs in the caller's thread at the IRQL of the caller.

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
<dt>Parallel.h (include Parallel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>
</dt>
<dt>
<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>
</dt>
<dt>
<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_default_modes.md">IOCTL_PAR_GET_DEFAULT_MODES</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pdetermine_ieee_modes.md">PDETERMINE_IEEE_MODES</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pnegotiate_ieee_mode.md">PNEGOTIATE_IEEE_MODE</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pparallel_ieee_fwd_to_rev.md">PPARALLEL_IEEE_FWD_TO_REV</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pterminate_ieee_mode.md">PTERMINATE_IEEE_MODE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PPARALLEL_IEEE_REV_TO_FWD function pointer%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
