---
UID : NF:wudfddi.IWDFFile.RetrieveFileName
title : IWDFFile::RetrieveFileName method
author : windows-driver-content
description : The RetrieveFileName method retrieves the full name of the file that is associated with the underlying kernel-mode device.
old-location : wdf\iwdffile_retrievefilename.htm
old-project : wdf
ms.assetid : 7858f3ba-e02a-4115-bf30-12e3a6a75965
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IWDFFile, IWDFFile::RetrieveFileName, RetrieveFileName
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfddi.h
req.include-header : Wudfddi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.5
req.alt-api : IWDFFile.RetrieveFileName
req.alt-loc : WUDFx.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : WUDFx.dll
req.irql : 
req.typenames : "*PPOWER_ACTION, POWER_ACTION"
req.product : Windows 10 or later.
---


# RetrieveFileName method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveFileName</b> method retrieves the full name of the file that is associated with the underlying kernel-mode device.

## Syntax

````
HRESULT RetrieveFileName(
  [out]     PWSTR pFileName,
  [in, out] DWORD *pdwFileNameLengthInChars
);
````

## Parameters

`pFileName`

A pointer to a caller-supplied buffer that receives a <b>NULL</b>-terminated string that represents the full name of the file that is associated with the underlying kernel-mode device, if the supplied pointer is non-<b>NULL</b> and <b>RetrieveFileName</b> is successful.

`pdwFileNameLengthInChars`

A pointer to a caller-supplied variable that receives the size, in characters, of the full file name that <i>pFileName</i> points to. If the buffer at <i>pFileName</i> is non-<b>NULL</b>, the framework returns the size, in characters, of the file name string.

On input, the driver sets this variable to the size, in characters, of the buffer that <i>pFileName</i> points to. If the driver supplies <b>NULL</b> for <i>pFileName</i> and zero for the variable that <i>pdwFileNameLengthInChars</i> points to, the framework sets the variable to the size, in characters, that the file name string requires.


## Return Value

<b>RetrieveFileName</b> returns S_OK for the following scenarios:


<ul>
<li>
The buffer that the <i>pFileName</i> parameter points to was non-<b>NULL</b> and large enough to hold the name string, including the <b>NULL</b> character, and the framework successfully copied the string into the supplied buffer and set the variable that is pointed to by the <i>pdwFileNameLengthInChars</i> parameter to the number of characters in the string.

</li>
<li>
The buffer at <i>pFileName</i> was <b>NULL</b>, the driver preset the variable at <i>pdwFileNameLengthInChars</i> to 0, and the framework set the variable at <i>pdwFileNameLengthInChars</i> to the number of characters that are required for the string. 


</li>
</ul><b>RetrieveFileName</b> returns HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER) to indicate that the supplied buffer is non-<b>NULL</b> and did not contain enough space to hold the file name. The framework sets the variable at <i>pdwFileNameLengthInChars</i> to the number of characters that are required for the string.



The buffer that the <i>pFileName</i> parameter points to was non-<b>NULL</b> and large enough to hold the name string, including the <b>NULL</b> character, and the framework successfully copied the string into the supplied buffer and set the variable that is pointed to by the <i>pdwFileNameLengthInChars</i> parameter to the number of characters in the string.

The buffer at <i>pFileName</i> was <b>NULL</b>, the driver preset the variable at <i>pdwFileNameLengthInChars</i> to 0, and the framework set the variable at <i>pdwFileNameLengthInChars</i> to the number of characters that are required for the string. 


<b>RetrieveFileName</b> might also return other HRESULT values.

## Remarks

Your driver might call <b>RetrieveFileName</b> from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff556841">IQueueCallbackCreate::OnCreateFile</a> callback function.  For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF Drivers</a>.

The following code example shows how to retrieve the name of a file.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFFile::RetrieveFileName method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>