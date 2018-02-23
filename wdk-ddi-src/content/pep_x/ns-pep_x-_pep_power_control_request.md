---
UID: NS:pep_x._PEP_POWER_CONTROL_REQUEST
title: "_PEP_POWER_CONTROL_REQUEST"
author: windows-driver-content
description: The PEP_POWER_CONTROL_REQUEST structure contains a request from a driver for a power control operation.
old-location: kernel\pep_power_control_request.htm
old-project: kernel
ms.assetid: E6665E96-5C58-4533-906A-D9525BA6824C
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.pep_power_control_request, PPEP_POWER_CONTROL_REQUEST, *PPEP_POWER_CONTROL_REQUEST, pepfx/PEP_POWER_CONTROL_REQUEST, PEP_POWER_CONTROL_REQUEST structure [Kernel-Mode Driver Architecture], PPEP_POWER_CONTROL_REQUEST structure pointer [Kernel-Mode Driver Architecture], pepfx/PPEP_POWER_CONTROL_REQUEST, PEP_POWER_CONTROL_REQUEST, _PEP_POWER_CONTROL_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_POWER_CONTROL_REQUEST
product: Windows
targetos: Windows
req.typenames: "*PPEP_POWER_CONTROL_REQUEST, PEP_POWER_CONTROL_REQUEST"
---

# _PEP_POWER_CONTROL_REQUEST structure
The <b>PEP_POWER_CONTROL_REQUEST</b> structure contains a request from a driver for a power control operation.

## Syntax
````
typedef struct _PEP_POWER_CONTROL_REQUEST {
  PEPHANDLE DeviceHandle;
  LPCGUID   PowerControlCode;
  PVOID     InBuffer;
  SIZE_T    InBufferSize;
  PVOID     OutBuffer;
  SIZE_T    OutBufferSize;
  SIZE_T    BytesReturned;
  NTSTATUS  Status;
} PEP_POWER_CONTROL_REQUEST, *PPEP_POWER_CONTROL_REQUEST;
````

## Members


`BytesReturned`

[out] The number of bytes that the PEP wrote to the output buffer pointed to by <b>OutBuffer</b>.

`DeviceHandle`

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.

`InBuffer`

[in] A pointer to a driver-allocated input buffer that contains the input parameters for this power control operation. This is the same value that the requesting driver supplied as the <i>InBuffer</i> parameter to the <b>PoFxPowerControl</b> routine.

`InBufferSize`

[in] The size in bytes of the buffer pointed to by <b>InBuffer</b>. This is the same value that the requesting driver supplied as the <i>InBufferSize</i> parameter to the <b>PoFxPowerControl</b> routine.

`OutBuffer`

[in] A pointer to a driver-allocated output buffer to which the PEP writes the results of this power control operation. This is the same value that the requesting driver supplied as the <i>OutBuffer</i> parameter to the <b>PoFxPowerControl</b> routine.

`OutBufferSize`

[in] The size in bytes of the buffer pointed to by <b>OutBuffer</b>.

`PowerControlCode`

[in] A pointer to a <a href="http://msdn.microsoft.com/library/windows/desktop/aa373931(v=vs.85).aspx">GUID</a> value that specifies the power control operation to perform. This is the same value that the requesting driver supplied as the <i>PowerControlCode</i> parameter to the <a href="..\wdm\nf-wdm-pofxpowercontrol.md">PoFxPowerControl</a> routine.

`Status`

[out] The status of the requested power control operation. If the operation is successful, the PEP sets this member to STATUS_SUCCESS. Otherwise, the PEP sets this member to an appropriate error status code.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186797">PEP_DPM_POWER_CONTROL_REQUEST</a> notification. The first six members of the structure contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management Framework</a> (PoFx). The last two members contain values that the PEP writes to the structure in response to this notification. In addition, the PEP writes to the output buffer pointed to by the <b>OutBuffer</b> member.

If the output buffer is too small to receive all of the result data from the operation, the PEP sets the <b>Status</b> member of the structure to STATUS_INSUFFICIENT_RESOURCES, sets  the <b>BytesReturned</b> member to the required size of the output buffer, and (typically) writes no data to the output buffer.

The driver for a device can call the <a href="..\wdm\nf-wdm-pofxpowercontrol.md">PoFxPowerControl</a> routine to request a power control operation on the device. During this call, PoFx delegates the handling of this request to the PEP that owns the device. The <b>PowerControlCode</b> member of the <b>PEP_POWER_CONTROL_REQUEST</b> structure contains a custom control code whose meaning is understood by both the driver and the PEP for the device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pep_x.h) |

## See Also

<a href="..\wdm\nf-wdm-pofxpowercontrol.md">PoFxPowerControl</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186797">PEP_DPM_POWER_CONTROL_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_POWER_CONTROL_REQUEST structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>