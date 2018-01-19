---
UID : NS:ntddk._WHEA_XPF_PROCINFO
title : _WHEA_XPF_PROCINFO
author : windows-driver-content
description : The WHEA_XPF_PROCINFO structure describes processor error information that is specific to the x86 and x64 processor architectures.
old-location : whea\whea_xpf_procinfo.htm
old-project : whea
ms.assetid : 90fb54dd-a2df-423c-8dd6-bd99c5ad1de4
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : _WHEA_XPF_PROCINFO, *PWHEA_XPF_PROCINFO, WHEA_XPF_PROCINFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddk.h
req.include-header : Ntddk.h
req.target-type : Windows
req.target-min-winverclnt : Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : WHEA_XPF_PROCINFO
req.alt-loc : ntddk.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PWHEA_XPF_PROCINFO, WHEA_XPF_PROCINFO"
---

# _WHEA_XPF_PROCINFO structure
The WHEA_XPF_PROCINFO structure describes processor error information that is specific to the x86 and x64 processor architectures.

## Syntax
````
typedef struct _WHEA_XPF_PROCINFO {
  GUID                        CheckInfoId;
  WHEA_XPF_PROCINFO_VALIDBITS ValidBits;
  union {
    WHEA_XPF_CACHE_CHECK CacheCheck;
    WHEA_XPF_TLB_CHECK   TlbCheck;
    WHEA_XPF_BUS_CHECK   BusCheck;
    WHEA_XPF_MS_CHECK    MsCheck;
    ULONGLONG            AsULONGLONG;
  } CheckInfo;
  ULONGLONG                   TargetId;
  ULONGLONG                   RequesterId;
  ULONGLONG                   ResponderId;
  ULONGLONG                   InstructionPointer;
} WHEA_XPF_PROCINFO, *PWHEA_XPF_PROCINFO;
````

## Members

        
            `CheckInfo`

            A union of unions that are specific to each different type of processor error information.

This member contains valid data only if the <b>ValidBits.CheckInfo</b> bit is set.
        
            `CheckInfoId`

            A GUID that identifies the processor error information that is contained in the <b>CheckInfo</b> member. The following are the possible GUIDs that can be specified for this member:
        
            `InstructionPointer`

            The instruction pointer at the time that the error occurred.

This member contains valid data only if the <b>ValidBits.InstructionPointer</b> bit is set.
        
            `RequesterId`

            An identifier that uniquely identifies the requester associated with the error.

This member contains valid data only if the <b>ValidBits.RequesterId</b> bit is set.
        
            `ResponderId`

            An identifier that uniquely identifies the responder associated with the error.

This member contains valid data only if the <b>ValidBits.Responder</b> bit is set.
        
            `TargetId`

            An identifier that uniquely identifies the target associated with the error.

This member contains valid data only if the <b>ValidBits.TargetId</b> bit is set.
        
            `ValidBits`

            A <a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo_validbits.md">WHEA_XPF_PROCINFO_VALIDBITS</a> union that specifies which members of this structure contain valid data.

    ## Remarks
        The <a href="..\ntddk\ns-ntddk-whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure contains an array of WHEA_XPF_PROCINFO structures, each of which describes specific error information associated with the processor error that occurred.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Ntddk.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_xpf_bus_check.md">WHEA_XPF_BUS_CHECK</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_xpf_cache_check.md">WHEA_XPF_CACHE_CHECK</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_xpf_ms_check.md">WHEA_XPF_MS_CHECK</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo_validbits.md">WHEA_XPF_PROCINFO_VALIDBITS</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_xpf_tlb_check.md">WHEA_XPF_TLB_CHECK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_PROCINFO structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>