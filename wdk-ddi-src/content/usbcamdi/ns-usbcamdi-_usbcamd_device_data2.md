---
UID : NS:usbcamdi._USBCAMD_DEVICE_DATA2
title : _USBCAMD_DEVICE_DATA2
author : windows-driver-content
description : The USBCAMD_DEVICE_DATA2 structure specifies the entry points for a camera minidriver's functions that USBCAMD calls.
old-location : stream\usbcamd_device_data2.htm
old-project : stream
ms.assetid : 51339fd1-a962-4e3c-b9c9-5fe54ff53aa0
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _USBCAMD_DEVICE_DATA2, USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : usbcamdi.h
req.include-header : Usbcamdi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : USBCAMD_DEVICE_DATA2
req.alt-loc : usbcamdi.h
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
req.typenames : USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product : Windows 10 or later.
---

# _USBCAMD_DEVICE_DATA2 structure
The USBCAMD_DEVICE_DATA2 structure specifies the entry points for a camera minidriver's functions that USBCAMD calls.

## Syntax
````
typedef struct _USBCAMD_DEVICE_DATA2 {
  ULONG                             Sig;
  PCAM_INITIALIZE_ROUTINE           CamInitialize;
  PCAM_INITIALIZE_ROUTINE           CamUnInitialize;
  PCAM_PROCESS_PACKET_ROUTINE_EX    CamProcessUSBPacketEx;
  PCAM_NEW_FRAME_ROUTINE_EX         CamNewVideoFrameEx;
  PCAM_PROCESS_RAW_FRAME_ROUTINE_EX CamProcessRawVideoFrameEx;
  PCAM_START_CAPTURE_ROUTINE_EX     CamStartCaptureEx;
  PCAM_STOP_CAPTURE_ROUTINE_EX      CamStopCaptureEx;
  PCAM_CONFIGURE_ROUTINE_EX         CamConfigureEx;
  PCAM_STATE_ROUTINE                CamSaveState;
  PCAM_STATE_ROUTINE                CamRestoreState;
  PCAM_ALLOCATE_BW_ROUTINE_EX       CamAllocateBandwidthEx;
  PCAM_FREE_BW_ROUTINE_EX           CamFreeBandwidthEx;
} USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2;
````

## Members

        
            `CamAllocateBandwidthEx`

            Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_allocate_bw_routine_ex.md">CamAllocateBandwidthEx</a> callback function. This entry point is required.
        
            `CamConfigureEx`

            Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_configure_routine_ex.md">CamConfigureEx</a> callback function. This entry point is required.
        
            `CamFreeBandwidthEx`

            Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_free_bw_routine_ex.md">CamFreeBandwidthEx</a> callback function. This entry point is required.
        
            `CamInitialize`

            Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_initialize_routine.md">CamInitialize</a> callback function. This entry point is required.
        
            `CamNewVideoFrameEx`

            Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_new_frame_routine_ex.md">CamNewVideoFrameEx</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.
        
            `CamProcessRawVideoFrameEx`

            Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_process_raw_frame_routine_ex.md">CamProcessRawVideoFrameEx</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.
        
            `CamProcessUSBPacketEx`

            Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_process_packet_routine_ex.md">CamProcessUSBPacketEx</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.
        
            `CamRestoreState`

            Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_state_routine.md">CamRestoreState</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.
        
            `CamSaveState`

            Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557635">CamSaveState</a> callback function. This is an optional entry point. If the minidriver does not implement this function, it must point to an empty function.
        
            `CamStartCaptureEx`

            Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_start_capture_routine_ex.md">CamStartCaptureEx</a> callback function. This entry point is required.
        
            `CamStopCaptureEx`

            Pointer to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcam_stop_capture_routine_ex.md">CamStopCaptureEx</a> callback function. This entry point is required.
        
            `CamUnInitialize`

            Pointer to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557646">CamUnInitialize</a> callback function. This entry point is required.
        
            `Sig`

            Reserved. Do not use.

    ## Remarks
        A camera minidriver passes a USBCAMD_DEVICE_DATA2 structure to USBCAMD as a parameter to USBCAMD service <a href="..\usbcamdi\nf-usbcamdi-usbcamd_initializenewinterface.md">USBCAMD_InitializeNewInterface</a>.

Camera minidrivers that must be backward compatible with the original USBCAMD library must use the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbcamdi.h (include Usbcamdi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\usbcamdi\nf-usbcamdi-usbcamd_initializenewinterface.md">USBCAMD_InitializeNewInterface</a>
</dt>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-pcam_initialize_routine.md">CamInitialize</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557646">CamUnInitialize</a>
</dt>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-pcam_process_packet_routine_ex.md">CamProcessUSBPacketEx</a>
</dt>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-pcam_new_frame_routine_ex.md">CamNewVideoFrameEx</a>
</dt>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-pcam_process_raw_frame_routine_ex.md">CamProcessRawVideoFrameEx</a>
</dt>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-pcam_start_capture_routine_ex.md">CamStartCaptureEx</a>
</dt>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-pcam_stop_capture_routine_ex.md">CamStopCaptureEx</a>
</dt>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-pcam_configure_routine_ex.md">CamConfigureEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557635">CamSaveState</a>
</dt>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-pcam_state_routine.md">CamRestoreState</a>
</dt>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-pcam_allocate_bw_routine_ex.md">CamAllocateBandwidthEx</a>
</dt>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-pcam_free_bw_routine_ex.md">CamFreeBandwidthEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_DEVICE_DATA2 structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>