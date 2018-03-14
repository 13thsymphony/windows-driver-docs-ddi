---
UID: NF:wudfddi.IWDFFile3.GetInitiatorProcessId
title: IWDFFile3::GetInitiatorProcessId method
author: windows-driver-content
description: The GetInitiatorProcessId method retrieves the initiator process ID associated with an IWDFFile interface.
old-location: wdf\iwdffile3_getinitiatorprocessid.htm
old-project: wdf
ms.assetid: 4D23A651-7231-40CE-B9C2-4382D4E7F683
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetInitiatorProcessId method, GetInitiatorProcessId method, IWDFFile3 interface, GetInitiatorProcessId,IWDFFile3.GetInitiatorProcessId, IWDFFile3, IWDFFile3 interface, GetInitiatorProcessId method, IWDFFile3::GetInitiatorProcessId, umdf.iwdffile3_getinitiatorprocessid, wdf.iwdffile3_getinitiatorprocessid, wudfddi/IWDFFile3::GetInitiatorProcessId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFFile3.GetInitiatorProcessId
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# GetInitiatorProcessId method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInitiatorProcessId</b> method retrieves the initiator process ID associated with an <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface.

## Syntax

````
void GetInitiatorProcessId(
  [out] DWORD *pdwProcessId
);
````

## Parameters

`pdwProcessId`

Specifies the address of a location that receives the initiator process identifier associated with the file, if any exists.  Otherwise, the location receives 0.


## Return Value

This method does not return a value.

## Remarks

Starting in Windows 8, a system component may issue a create on behalf of an app. The driver can call <b>GetInitiatorProcessId</b> to determine which process the create operation is ultimately intended for.

<b>GetInitiatorProcessId</b> returns zero if no initiator process is associated with the create operation.

For more information about framework file objects, see <a href="https://msdn.microsoft.com/f81ae0ed-a29c-476e-9b16-ff554eef1de9">Driver-Created Versus Application-Created File Objects</a>.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
STDMETHODCALLTYPE
CMyQueue::OnCreateFile(
    __in IWDFIoQueue *pWdfQueue,
    __in IWDFIoRequest *pWdfRequest,
    __in IWDFFile*  pWdfFileObject
    )
 ...
    IWDFFile3*  pWdfFileObject3 = NULL;
    HRESULT  hr = S_OK;
    DWORD initiatorProcessId;

    //
    // Obtain IWDFFile3 interface from IWDFFile.
    //
    hr = pWdfFileObject-&gt;QueryInterface(IID_PPV_ARGS(&amp;pWdfFileObject3));
    if (!SUCCEEDED(hr))
    {
        goto Done;
    }
    pWdfFileObject3-&gt;GetInitiatorProcessId(&amp;initiatorProcessId);
    ...

</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdffile3.md">IWDFFile3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFFile3::GetInitiatorProcessId method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>