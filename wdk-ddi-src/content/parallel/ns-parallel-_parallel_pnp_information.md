---
UID: NS:parallel._PARALLEL_PNP_INFORMATION
title: "_PARALLEL_PNP_INFORMATION"
author: windows-driver-content
description: The PARALLEL_PNP_INFORMATION structure specifies information about the capabilities of a parallel port.
old-location: parports\parallel_pnp_information.htm
old-project: parports
ms.assetid: 9288fc11-e19b-46dd-95e4-6de8c7cdc61d
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PPARALLEL_PNP_INFORMATION, PARALLEL_PNP_INFORMATION, PARALLEL_PNP_INFORMATION structure [Parallel Ports], PPARALLEL_PNP_INFORMATION, PPARALLEL_PNP_INFORMATION structure pointer [Parallel Ports], _PARALLEL_PNP_INFORMATION, cisspd_71ac405c-ab56-434c-a945-9afee36c0972.xml, parallel/PARALLEL_PNP_INFORMATION, parallel/PPARALLEL_PNP_INFORMATION, parports.parallel_pnp_information"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: parallel.h
req.include-header: Parallel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
-	parallel.h
api_name:
-	PARALLEL_PNP_INFORMATION
product: Windows
targetos: Windows
req.typenames: PARALLEL_PNP_INFORMATION, *PPARALLEL_PNP_INFORMATION
---

# _PARALLEL_PNP_INFORMATION structure
The PARALLEL_PNP_INFORMATION structure specifies information about the capabilities of a parallel port.

## Syntax
````
typedef struct _PARALLEL_PNP_INFORMATION {
  PHYSICAL_ADDRESS             OriginalEcpController;
  PUCHAR                       EcpController;
  ULONG                        SpanOfEcpController;
  ULONG                        PortNumber;
  ULONG                        HardwareCapabilities;
  PPARALLEL_SET_CHIP_MODE      TrySetChipMode;
  PPARALLEL_CLEAR_CHIP_MODE    ClearChipMode;
  ULONG                        FifoDepth;
  ULONG                        FifoWidth;
  PHYSICAL_ADDRESS             EppControllerPhysicalAddress;
  ULONG                        SpanOfEppController;
  ULONG                        Ieee1284_3DeviceCount;
  PPARALLEL_TRY_SELECT_ROUTINE TrySelectDevice;
  PPARALLEL_DESELECT_ROUTINE   DeselectDevice;
  PVOID                        Context;
  ULONG                        CurrentMode;
  PWSTR                        PortName;
} PARALLEL_PNP_INFORMATION, *PPARALLEL_PNP_INFORMATION;
````

## Members


`ClearChipMode`

Pointer to the system-supplied <a href="..\parallel\nc-parallel-pparallel_clear_chip_mode.md">PPARALLEL_CLEAR_CHIP_MODE</a> callback that a kernel-mode driver can use to clear the operating mode of the parallel port.

`Context`

Pointer to the device extension of a parallel port's functional device object (<a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">FDO</a>).

`CurrentMode`

The current operating mode of the parallel port.

`DeselectDevice`

Pointer to the system-supplied <a href="..\parallel\nc-parallel-pparallel_deselect_routine.md">PPARALLEL_DESELECT_ROUTINE</a> callback that a kernel-mode driver can use to deselect an IEEE 1284.3 device.

`EcpController`

Pointer to the I/O port resource that is used to control the port in ECP mode.

`EppControllerPhysicalAddress`

Not used.

`FifoDepth`

Specifies the size, in words, of the hardware first in/first out (FIFO) buffer. The FIFO word size, in bits, is the value of <b>FifoWidth</b>.

`FifoWidth`

Specifies the FIFO word size, in bits, which is the number of bits handled in parallel.

`HardwareCapabilities`

Specifies the hardware capabilities of the parallel port. The following capabilities can be set using a bitwise OR of the following constants:





#### PPT_1284_3_PRESENT



#### PPT_BYTE_PRESENT



#### PPT_ECP_PRESENT



#### PPT_EPP_32_PRESENT



#### PPT_EPP_PRESENT



#### PT_NO_HARDWARE_PRESENT

`Ieee1284_3DeviceCount`

Specifies the number of daisy-chain devices currently attached to a parallel port. In Microsoft Windows XP, from zero to two devices can be simultaneously connected to a parallel port. In Windows 2000, from zero to four devices can be simultaneously connected to a parallel port.

`OriginalEcpController`

Specifies the base physical address that the system-supplied function driver for parallel ports uses to control the ECP operation of the parallel port.

`PortName`

The symbolic link name of the parallel port.

`PortNumber`

Not used.

`SpanOfEcpController`

Specifies the size, in bytes, of the I/O port resource.

`SpanOfEppController`

Not used.

`TrySelectDevice`

Pointer to the system-supplied <a href="..\parallel\nc-parallel-pparallel_try_select_routine.md">PPARALLEL_TRY_SELECT_ROUTINE</a> callback that a kernel-mode driver can use to attempt to select an IEEE 1284.3 device.

`TrySetChipMode`

Pointer to the system-supplied <a href="..\parallel\nc-parallel-pparallel_set_chip_mode.md">PPARALLEL_SET_CHIP_MODE</a> callback that a kernel-mode driver can use to change the operating mode of the parallel port.

## Remarks
For more information, see <a href="https://msdn.microsoft.com/d8ae2296-05b6-419a-93cc-00fcb12d41fe">Obtaining Information About a ParallelPort</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | parallel.h (include Parallel.h) |

## See Also

<a href="..\parallel\ns-parallel-_parallel_port_information.md">PARALLEL_PORT_INFORMATION</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_pnp_info.md">IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>



<a href="..\parallel\nc-parallel-pparallel_deselect_routine.md">PPARALLEL_DESELECT_ROUTINE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_more_parallel_port_info.md">IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO</a>



<a href="..\parallel\nc-parallel-pparallel_try_select_routine.md">PPARALLEL_TRY_SELECT_ROUTINE</a>



<a href="..\parallel\nc-parallel-pparallel_set_chip_mode.md">PPARALLEL_SET_CHIP_MODE</a>



<a href="..\parallel\nc-parallel-pparallel_clear_chip_mode.md">PPARALLEL_CLEAR_CHIP_MODE</a>



<a href="..\parallel\ns-parallel-_more_parallel_port_information.md">MORE_PARALLEL_PORT_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PARALLEL_PNP_INFORMATION structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>