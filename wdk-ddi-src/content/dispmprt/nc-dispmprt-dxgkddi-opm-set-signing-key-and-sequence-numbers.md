---
UID: NC.dispmprt.DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
title: DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
author: windows-driver-content
description: The DxgkDdiOPMSetSigningKeyAndSequenceNumbers function sets the given protected output object's signing key and two sequence numbers.
old-location: display\dxgkddiopmsetsigningkeyandsequencenumbers.htm
old-project: display
ms.assetid: 285521c7-4034-4db8-9441-6c4eaee27ee3
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiOPMSetSigningKeyAndSequenceNumbers
req.alt-loc: dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.iface: IDebugSystemObjects4
---

# DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS callback



## -description
<p>The<i> DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i> function sets the given protected output object's signing key and two sequence numbers.</p>


## -prototype

````
DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS DxgkDdiOPMSetSigningKeyAndSequenceNumbers;

NTSTATUS DxgkDdiOPMSetSigningKeyAndSequenceNumbers(
  _In_       PVOID                             MiniportDeviceContext,
  _In_       HANDLE                            ProtectedOutputHandle,
  _In_ const PDXGKMDT_OPM_ENCRYPTED_PARAMETERS EncryptedParameters
)
{ ... }
````


## -parameters
<dl>

### -param <i>MiniportDeviceContext</i> [in]

<dd>
<p>A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="display.dxgkddiadddevice">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.</p>
</dd>

### -param <i>ProtectedOutputHandle</i> [in]

<dd>
<p>The handle to a protected output object. The <a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-create-protected-output.md">DxgkDdiOPMCreateProtectedOutput</a> function creates the protected output object and returns the handle to the object.</p>
</dd>

### -param <i>EncryptedParameters</i> [in]

<dd>
<p>A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt--dxgkmdt-opm-encrypted-parameters.md">DXGKMDT_OPM_ENCRYPTED_PARAMETERS</a> structure that contains a 256-byte array. The array contains between 40 and 256 bytes of data that is encrypted with the public key from the appropriate certificate. For more information about the public key, download the Output Content Protection document at the <a href="http://go.microsoft.com/fwlink/p/?linkid=204788">Output Content Protection and Windows Vista</a> website. If the protected output has OPM semantics, the data is encrypted with the public key from the display miniport driver's OPM certificate. If the protected output has Certified Output Protection Protocol (COPP) semantics, the data is encrypted with the public key from the display miniport driver's COPP certificate. </p>
<p>The algorithm that the display miniport driver should use to decrypt the data in the array depends on the semantics of the protected output. Protected outputs with OPM semantics use the RSAES-OAEP encryption scheme to decrypt the data. For more information about RSAES-OAEP, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> website. Protected outputs with COPP semantics use the standard RSA encryption algorithm to decrypt the encrypted data. </p>
<p>After the display miniport driver decrypts the data, only the first 40 bytes of the data is currently useful. The first 16 bytes of the decrypted data contain the random number that the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-get-random-number.md">DxgkDdiOPMGetRandomNumber</a> function returned when the handle in the <i>ProtectedOutputHandle</i> parameter was passed to it. The next 16 bytes contain the 128-bit AES signing key. The next 4 bytes contain the sequence number that is used by <a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-get-information.md">DxgkDdiOPMGetInformation</a> or <a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-get-copp-compatible-information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>. The final 4 bytes contain the sequence number that is used by <a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-configure-protected-output.md">DxgkDdiOPMConfigureProtectedOutput</a>. The remainder of the decrypted data should be ignored if it exists. </p>
</dd>
</dl>

## -returns
<p><i>DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i> returns one of the following values.</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The function successfully set the signing key and two sequence numbers.</p><dl>
<dt><b>STATUS_OPM_INVALID_ENCRYPTED_PARAMETERS</b></dt>
</dl><p><i>DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i> returns this value for one of the following reasons: </p>

<p>If the protected output has OPM semantics, the data that the display miniport driver decrypted was not encoded with the RSAES-OAEP encoding algorithm. For more information about RSAES-OAEP, see section 7.1.2 in the PKCS #1 v2.1: RSA Cryptography Standard, at the <a href="http://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> website. </p>

<p>The data was not encrypted by the caller with the appropriate public key. If the output has OPM semantics, the caller should encrypt the data with the public key from the display miniport driver's OPM certificate. If the output has COPP semantics, the caller should encrypt the data with the public key from the display miniport driver's COPP certificate.</p>

<p>The caller did not encrypt at least 40 bytes of data.</p>

<p>The 16-byte random number in the data that the display miniport driver decrypted did not match the 16-byte random number that the <a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-get-random-number.md">DxgkDdiOPMGetRandomNumber</a> function returned.</p>

<p> </p>

<p>This function might also return other error codes that are defined in Ntstatus.h.</p>

## -remarks
<p>The signing key is used to verify that data that is passed to the <a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-configure-protected-output.md">DxgkDdiOPMConfigureProtectedOutput</a> and <a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-get-information.md">DxgkDdiOPMGetInformation</a> functions comes from the application that indirectly uses the protected output. The signing key is also used to sign the data that is returned by the <b>DxgkDdiOPMGetInformation</b> and <a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-get-copp-compatible-information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> functions. One of the sequence numbers is used by <i>DxgkDdiOPMConfigureProtectedOutput</i>. The other sequence number is used by <i>DxgkDdiOPMGetInformation</i> or <i>DxgkDdiOPMGetCOPPCompatibleInformation</i>.</p>

<p><i>DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i> should return a failure code if an error occurs or if the data in the <a href="..\d3dkmdt\ns-d3dkmdt--dxgkmdt-opm-encrypted-parameters.md">DXGKMDT_OPM_ENCRYPTED_PARAMETERS</a> structure that is pointed to by the <i>EncryptedParameters</i> parameter is not in the required format. Otherwise, <i>DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i> should perform the following sequence of operations:</p>

<p>Decrypt the data that is pointed to by <i>EncryptedParameters</i> with the appropriate private key and encryption scheme. If the output has OPM semantics, the display miniport driver should use its OPM private key to decrypt the data. If the output has COPP semantics, the display miniport driver should use its COPP private key to decrypt the data. </p>

<p>If the output has OPM semantics, verify that the data that was decrypted was encoded with the RSAES-OAEP encoding algorithm. </p>

<p>Verify that at least 40 bytes of the data was decrypted.</p>

<p>Verify that the random number that is contained in the first 16 bytes of the data that was decrypted matches the random number that the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-get-random-number.md">DxgkDdiOPMGetRandomNumber</a> returned when the handle in the <i>ProtectedOutputHandle</i> parameter was passed to it.</p>

<p>Cache the 128-bit AES signing key and the two 32-bit sequence numbers.</p>

<p>Before a protected output object's handle is passed to <i>DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i>, it is passed to <a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-get-random-number.md">DxgkDdiOPMGetRandomNumber</a>. Each protected output object handle is only passed to <i>DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i> once.</p>

<p><i>DxgkDdiOPMSetSigningKeyAndSequenceNumbers</i> should be made pageable.</p>

<p>RSAES-OAEP is a parameterized encryption scheme and MGF1 is a parameterized mask generation function. Following are the parameters OPM uses when it uses RSAES-OAEP and MGF1. For more information about the following terms and the RSA Cryptography Standard, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=70462">Secure Hashing</a> websites.</p>

<p></p>

<p>SHA-512</p>

<p>MGF1 (Defined on page 48 in PKCS #1 v2.1: RSA Cryptography Standard)</p>

<p>L is always the empty string. </p>

<p>Hash:  SHA-512</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL (see Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkddiadddevice">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-configure-protected-output.md">DxgkDdiOPMConfigureProtectedOutput</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-create-protected-output.md">DxgkDdiOPMCreateProtectedOutput</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-get-copp-compatible-information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-get-information.md">DxgkDdiOPMGetInformation</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-get-random-number.md">DxgkDdiOPMGetRandomNumber</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt--dxgkmdt-opm-encrypted-parameters.md">DXGKMDT_OPM_ENCRYPTED_PARAMETERS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
