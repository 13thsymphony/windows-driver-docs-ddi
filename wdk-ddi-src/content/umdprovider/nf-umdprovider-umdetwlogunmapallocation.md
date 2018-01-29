---
UID : NF:umdprovider.UMDEtwLogUnmapAllocation
title : UMDEtwLogUnmapAllocation function
author : windows-driver-content
description : Indicates that a Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) memory allocation, or a portion of the allocation, is no longer being used. Call this function whether or not the allocation is being destroyed.
old-location : display\umdetwlogunmapallocation.htm
old-project : display
ms.assetid : 36c204fb-638d-44d2-8379-a5bd79e4167a
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : UMDEtwLogUnmapAllocation, UMDEtwLogUnmapAllocation function [Display Devices], umdprovider/UMDEtwLogUnmapAllocation, display.umdetwlogunmapallocation
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : umdprovider.h
req.include-header : Umdprovider.h
req.target-type : Desktop
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : UMDETW_ALLOCATION_SEMANTIC
req.product : Windows 10 or later.
---


# UMDEtwLogUnmapAllocation function
Indicates that a Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) memory allocation, or a portion of the allocation, is no longer being used. Call this function whether or not the allocation is being destroyed.

## Syntax

````
void UMDEtwLogUnmapAllocation(
   ULONGLONG                  hD3DAllocation,
   ULONGLONG                  hDxgAllocation,
   ULONGLONG                  Offset,
   ULONGLONG                  Size,
   UMDETW_ALLOCATION_USAGE    Usage,
   UMDETW_ALLOCATION_SEMANTIC Semantic
);
````

## Parameters

`hD3DAllocation`

A handle to the Direct3D allocation.

 For Direct3D 10 user-mode drivers, the handle will be the value of the <i>hResource</i> parameter of the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a> function. For Direct3D 9 user-mode drivers, the handle will be the value of the <i>pResource</i> parameter that the driver returns in the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> function.

The driver can set this value to <b>NULL</b> if it uses allocations internally.

`hDxgAllocation`

A handle to the DirectX graphics kernel subsystem (Dxgkrnl.sys) allocation that the Direct3D allocation is mapped to.

`Offset`

The starting address, in bytes, of the Direct3D allocation within the Dxgkrnl allocation.

`Size`

The size, in bytes, of the Direct3D allocation within the Dxgkrnl allocation.

`Usage`

A <a href="..\umdprovider\ns-umdprovider-_umdetw_allocation_usage.md">UMDETW_ALLOCATION_USAGE</a> structure that indicates the reason for this mapping.

`Semantic`

If the allocation is used internally by the user-mode driver, this is a <a href="..\umdprovider\ne-umdprovider-_umdetw_allocation_semantic.md">UMDETW_ALLOCATION_SEMANTIC</a> structure that indicates what the allocation is used for.


## Return Value

This function does not return a value.

## Remarks

When called, this function logs an event that describes which API resource the allocation is, or was, being used for. If no API resource was associated with the allocation, the function logs an event that describes the purpose that the driver indicated for this allocation.

The user-mode display driver must completely account for the video memory it allocates, so it must call this function to log an event every time the allocation changes.

The driver should pass the same parameters values to <b>UMDEtwLogUnmapAllocation</b> as it did to <a href="..\umdprovider\nf-umdprovider-umdetwlogmapallocation.md">UMDEtwLogMapAllocation</a>.

<b>UMDEtwLogUnmapAllocation</b> is defined inline in Umdprovider.h as:
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>FORCEINLINE void LogMapAllocation(BOOLEAN Enter,
                    ULONGLONG hD3DAllocation,
                    ULONGLONG hDxgAllocation,
                    ULONGLONG Offset,
                    ULONGLONG Size,
                    UMDETW_ALLOCATION_USAGE Usage,
                    UMDETW_ALLOCATION_SEMANTIC Semantic)
{
    if (Enabled)
    {   
        EVENT_DATA_DESCRIPTOR Descriptors[6];
        
        // Create a description of the event
        EventDataDescCreate(&amp;Descriptors[0], &amp;hD3DAllocation, 8);
        EventDataDescCreate(&amp;Descriptors[1], &amp;hDxgAllocation, 8);
        EventDataDescCreate(&amp;Descriptors[2], &amp;Offset, 8);
        EventDataDescCreate(&amp;Descriptors[3], &amp;Size, 8);
        EventDataDescCreate(&amp;Descriptors[4], &amp;Usage, 4);
        EventDataDescCreate(&amp;Descriptors[5], &amp;Semantic, 4);

        // Log the event
        EventWrite(
            RegHandle,
            Enter ? (InRundown ? &amp;RundownAllocationEvent : &amp;MapAllocationEvent) : &amp;UnmapAllocationEvent,
            sizeof(Descriptors) / sizeof(Descriptors[0]),
            Descriptors
        );
    }
}

FORCEINLINE void UMDEtwLogUnmapAllocation(ULONGLONG hD3DAllocation,
                              ULONGLONG hDxgAllocation,
                              ULONGLONG Offset,
                              ULONGLONG Size,
                              UMDETW_ALLOCATION_USAGE Usage,
                              UMDETW_ALLOCATION_SEMANTIC Semantic)
{
    LogMapAllocation(FALSE,
                     hD3DAllocation,
                     hDxgAllocation,
                     Offset,
                     Size,
                     Usage,
                     Semantic);
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | umdprovider.h (include Umdprovider.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>

<a href="..\umdprovider\nf-umdprovider-umdetwlogmapallocation.md">UMDEtwLogMapAllocation</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a>

<a href="..\umdprovider\ns-umdprovider-_umdetw_allocation_usage.md">UMDETW_ALLOCATION_USAGE</a>

<a href="..\umdprovider\ne-umdprovider-_umdetw_allocation_semantic.md">UMDETW_ALLOCATION_SEMANTIC</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20UMDEtwLogUnmapAllocation function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>