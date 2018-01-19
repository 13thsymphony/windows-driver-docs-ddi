---
UID : NS:pepfx._PEP_PPM_QUERY_VETO_REASON
title : _PEP_PPM_QUERY_VETO_REASON
author : windows-driver-content
description : The PEP_PPM_QUERY_VETO_REASON structure supplies a wide-character, null-terminated string that contains a descriptive, human-readable name for a veto reason.
old-location : kernel\pep_ppm_query_veto_reason.htm
old-project : kernel
ms.assetid : 21716141-487B-4950-A55D-C9EE3B8C8612
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _PEP_PPM_QUERY_VETO_REASON, *PPEP_PPM_QUERY_VETO_REASON, PEP_PPM_QUERY_VETO_REASON
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : pepfx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 10.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PEP_PPM_QUERY_VETO_REASON
req.alt-loc : pepfx.h
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
req.typenames : "*PPEP_PPM_QUERY_VETO_REASON, PEP_PPM_QUERY_VETO_REASON"
---

# _PEP_PPM_QUERY_VETO_REASON structure
The <b>PEP_PPM_QUERY_VETO_REASON</b> structure supplies a wide-character, null-terminated string that contains a descriptive, human-readable name for a veto reason.

## Syntax
````
typedef struct _PEP_PPM_QUERY_VETO_REASON {
  ULONG  VetoReason;
  USHORT NameSize;
  PWSTR  Name;
} PEP_PPM_QUERY_VETO_REASON, *PPEP_PPM_QUERY_VETO_REASON;
````

## Members

        
            `Name`

            [in] A pointer to a PoFx-allocated string buffer. If this buffer pointer is non-<b>NULL</b>, the PEP writes a wide-character, null-terminated string to the buffer (and writes nothing to the <b>NameSize</b> member). Otherwise, the PEP writes nothing to this buffer and instead writes the required string size to the <b>NameSize</b> member.
        
            `NameSize`

            [out] The size, in bytes, of the string buffer pointed to by the <b>Name</b> member. This string size includes the storage space for the null character that terminates the wide-character string.
        
            `VetoReason`

            [in] The index that identifies this veto reason. If the platform extension plug-in (PEP) supports N veto reasons, valid veto reason indexes range from 1 to N. The PEP previously specified the number of supported veto reasons in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASONS</a> notification.

    ## Remarks
        This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASON</a> notification. The <b>VetoReason</b> and <b>Name</b> members contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). If the input value of the <b>Name</b> member is <b>NULL</b>, the PEP writes an output value (the required string buffer size) to the <b>NameSize</b> member.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pepfx.h |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASON</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASONS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_QUERY_VETO_REASON structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>