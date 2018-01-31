---
UID : NC:parallel.PPARALLEL_IEEE_REV_TO_FWD
title : PPARALLEL_IEEE_REV_TO_FWD
author : windows-driver-content
description : The PPARALLEL_IEEE_REV_TO_FWD-typed callback routine changes the transfer mode from reverse to forward. The system-supplied bus driver for parallel ports supplies this routine.
old-location : parports\pparallel_ieee_rev_to_fwd.htm
old-project : parports
ms.assetid : 4c9c88bf-e7f9-484b-b476-0def92cf48b2
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : parports.pparallel_ieee_rev_to_fwd, PPARALLEL_IEEE_REV_TO_FWD function pointer [Parallel Ports], PPARALLEL_IEEE_REV_TO_FWD, parallel/PPARALLEL_IEEE_REV_TO_FWD, cisspd_f42cc965-4f4d-4d18-b111-0e19fca9a9d5.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : parallel.h
req.include-header : Parallel.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : RILGBATOKEN, *LPRILGBATOKEN
---


# PPARALLEL_IEEE_REV_TO_FWD callback function
The PPARALLEL_IEEE_REV_TO_FWD-typed callback routine changes the transfer mode from reverse to forward. The system-supplied bus driver for parallel ports supplies this routine.

## Syntax

```
PPARALLEL_IEEE_REV_TO_FWD PparallelIeeeRevToFwd;

NTSTATUS PparallelIeeeRevToFwd(
  PVOID Context
)
{...}
```

## Parameters

`Context`

Pointer to a device extension of a parallel device's physical device object (<a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PDO</a>).


## Return Value

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The transfer mode was changed from reverse to forward.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_<i>Xxx</i></b></dt>
</dl>
</td>
<td width="60%">
An internal operation resulted in an NTSTATUS error.

</td>
</tr>
</table>

## Remarks

To obtain a pointer to the system-supplied PPARALLEL_IEEE_REV_TO_FWD callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_parclass_connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a> request, which returns a <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure. The <b>IeeeRevToFwdMode</b> member of the PARCLASS_INFORMATION structure is a pointer to this callback.

If the device is connected and is in the forward mode, the PPARALLEL_IEEE_REV_TO_FWD callback returns without further processing. Otherwise, the PPARALLEL_IEEE_REV_TO_FWD callback puts a parallel device in the forward mode and connects a previously negotiated forward protocol. The <a href="..\parallel\nc-parallel-pnegotiate_ieee_mode.md">PNEGOTIATE_IEEE_MODE</a> callback can be used to negotiate a forward protocol.

The PPARALLEL_IEEE_REV_TO_FWD callback runs in the caller's thread at the IRQL of the caller.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | parallel.h (include Parallel.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>

<a href="..\parallel\nc-parallel-pterminate_ieee_mode.md">PTERMINATE_IEEE_MODE</a>

<a href="..\parallel\nc-parallel-pdetermine_ieee_modes.md">PDETERMINE_IEEE_MODES</a>

<a href="..\parallel\nc-parallel-pparallel_ieee_fwd_to_rev.md">PPARALLEL_IEEE_FWD_TO_REV</a>

<a href="..\parallel\nc-parallel-pnegotiate_ieee_mode.md">PNEGOTIATE_IEEE_MODE</a>

<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>

<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_default_modes.md">IOCTL_PAR_GET_DEFAULT_MODES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PPARALLEL_IEEE_REV_TO_FWD function pointer%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>