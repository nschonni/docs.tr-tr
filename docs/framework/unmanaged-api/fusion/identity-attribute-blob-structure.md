---
title: "IDENTITY_ATTRIBUTE_BLOB Yapısı"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: IDENTITY_ATTRIBUTE_BLOB
api_location: fusion.dll
api_type: COM
f1_keywords: IDENTITY_ATTRIBUTE_BLOB
helpviewer_keywords: IDENTITY_ATTRIBUTE_BLOB structure [.NET Framework fusion]
ms.assetid: af14ae5f-d226-47dd-ba90-8fc6e6605d4d
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b6d732f94eaa1e6988273d947ec924acf7b2521
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="identityattributeblob-structure"></a><span data-ttu-id="db265-102">IDENTITY_ATTRIBUTE_BLOB Yapısı</span><span class="sxs-lookup"><span data-stu-id="db265-102">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>
<span data-ttu-id="db265-103">Tek bir özniteliği derlemedeki hakkında bilgi içerir ve üç oluşur `DWORD`s.</span><span class="sxs-lookup"><span data-stu-id="db265-103">Contains information about a single attribute in an assembly, and consists of three `DWORD`s.</span></span> <span data-ttu-id="db265-104">Her `DWORD` tarafından üretilen karakter arabellek içine bir uzaklık `CurrentIntoBuffer` yöntemi [Ienumıdentıty_attrıbute](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) arabirimi</span><span class="sxs-lookup"><span data-stu-id="db265-104">Each `DWORD` is an offset into a character buffer produced by the `CurrentIntoBuffer` method of the [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) interface</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db265-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="db265-105">Syntax</span></span>  
  
```  
typedef struct _IDENTITY_ATTRIBUTE_BLOB {  
    DWORD  ofsNamespace;  
    DWORD  ofsName;  
    DWORD  ofsValue;  
}   IDENTITY_ATTRIBUTE_BLOB;  
```  
  
## <a name="members"></a><span data-ttu-id="db265-106">Üyeler</span><span class="sxs-lookup"><span data-stu-id="db265-106">Members</span></span>  
  
|<span data-ttu-id="db265-107">Üye</span><span class="sxs-lookup"><span data-stu-id="db265-107">Member</span></span>|<span data-ttu-id="db265-108">Açıklama</span><span class="sxs-lookup"><span data-stu-id="db265-108">Description</span></span>|  
|------------|-----------------|  
|`ofsNamespace`|<span data-ttu-id="db265-109">Karakter arabellek içine ilk uzaklığı.</span><span class="sxs-lookup"><span data-stu-id="db265-109">The first offset into the character buffer.</span></span> <span data-ttu-id="db265-110">Bu uzaklık özniteliğin ad alanı, ancak bir null karakter dizisi tarafından izlenmeyen.</span><span class="sxs-lookup"><span data-stu-id="db265-110">This offset is not followed by the attribute's namespace, but by a series of null characters.</span></span> <span data-ttu-id="db265-111">Bu nedenle, bu kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="db265-111">Therefore, it is not used.</span></span>|  
|`ofsName`|<span data-ttu-id="db265-112">Karakter arabellek içine ikinci uzaklığı.</span><span class="sxs-lookup"><span data-stu-id="db265-112">The second offset into the character buffer.</span></span> <span data-ttu-id="db265-113">Bu konum özniteliğin adı başlangıcını işaretler.</span><span class="sxs-lookup"><span data-stu-id="db265-113">This location marks the start of the attribute's name.</span></span>|  
|`ofsValue`|<span data-ttu-id="db265-114">Karakter arabellek içine üçüncü uzaklığı.</span><span class="sxs-lookup"><span data-stu-id="db265-114">The third offset into the character buffer.</span></span> <span data-ttu-id="db265-115">Bu konum özniteliğin değeri başlangıcını işaretler.</span><span class="sxs-lookup"><span data-stu-id="db265-115">This location marks the start of the attribute's value.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="db265-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="db265-116">Sample</span></span>  
 <span data-ttu-id="db265-117">Aşağıdaki örnekte, sonuçta bir doldurulan neden birkaç temel adımlar gösterilmektedir `IDENTITY_ATTRIBUTE_BLOB` yapısı:</span><span class="sxs-lookup"><span data-stu-id="db265-117">The following example illustrates several basic steps, which eventually result in a populated `IDENTITY_ATTRIBUTE_BLOB` structure:</span></span>  
  
1.  <span data-ttu-id="db265-118">Elde bir [Ireferenceıdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) derleme için.</span><span class="sxs-lookup"><span data-stu-id="db265-118">Obtain an [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) for the assembly.</span></span>  
  
2.  <span data-ttu-id="db265-119">Çağrı `IReferenceIdentity::EnumAttributes` yöntemi ve elde bir [Ienumıdentıty_attrıbute](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md).</span><span class="sxs-lookup"><span data-stu-id="db265-119">Call the `IReferenceIdentity::EnumAttributes` method, and obtain an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md).</span></span>  
  
3.  <span data-ttu-id="db265-120">Bir karakter arabellek oluşturun ve olarak cast bir `IDENTITY_ATTRIBUTE_BLOB` yapısı.</span><span class="sxs-lookup"><span data-stu-id="db265-120">Create a character buffer, and cast it as an `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
4.  <span data-ttu-id="db265-121">Çağrı `CurrentIntoBuffer` yöntemi `IEnumIDENTITY_ATTRIBUTE` arabirimi.</span><span class="sxs-lookup"><span data-stu-id="db265-121">Call the `CurrentIntoBuffer` method of the `IEnumIDENTITY_ATTRIBUTE` interface.</span></span> <span data-ttu-id="db265-122">Bu yöntem öznitelikleri kopyalar `Namespace`, `Name`, ve `Value` karakter arabellek içine.</span><span class="sxs-lookup"><span data-stu-id="db265-122">This method copies the attributes `Namespace`, `Name`, and `Value` into the character buffer.</span></span> <span data-ttu-id="db265-123">Bu dizeler için üç uzaklıkları içinde kullanılabilir olacağı `IDENTITY_ATTRIBUTE_BLOB` yapısı.</span><span class="sxs-lookup"><span data-stu-id="db265-123">The three offsets to those strings will become available in the `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
```  
// EnumAssemblyAttributes.cpp : main project file.  
  
#include "stdafx.h"  
  
#include "fusion.h"  
#include "windows.h"  
#include "stdio.h"  
#include "mscoree.h"  
#include "isolation.h"  
  
typedef HRESULT (__stdcall *PFNGETREF)(LPCWSTR pwzFile, REFIID riid, IUnknown **ppUnk);  
typedef HRESULT (__stdcall *PFNGETAUTH)(IIdentityAuthority **ppIIdentityAuthority);  
  
PFNGETREF                   g_pfnGetAssemblyIdentityFromFile = NULL;  
PFNGETAUTH                  g_pfnGetIdentityAuthority = NULL;  
IUnknown                    *g_pUnk = NULL;  
  
bool Init()  
{  
    HRESULT     hr = S_OK;  
    DWORD       dwSize = 0;  
    bool        bRC = false;  
  
    hr = CorBindToRuntimeEx(NULL, L"wks", 0, CLSID_CorRuntimeHost,  
                           IID_ICorRuntimeHost, (void **)&g_pUnk);  
    if(FAILED(hr)) {  
        printf("Error: Failed to initialize CLR runtime! hr = 0x%0x\n",  
                hr);  
        goto Exit;  
    }  
  
    if (SUCCEEDED(hr)) {  
        hr = GetRealProcAddress("GetAssemblyIdentityFromFile",  
                         (VOID **)&g_pfnGetAssemblyIdentityFromFile);  
    }  
  
    if (SUCCEEDED(hr)) {  
        hr = GetRealProcAddress("GetIdentityAuthority",  
                                (VOID **)&g_pfnGetIdentityAuthority);  
    }  
  
    if (!g_pfnGetAssemblyIdentityFromFile ||   
        !g_pfnGetIdentityAuthority)  
    {  
        printf("Error: Cannot get required APIs from fusion.dll!\n");  
        goto Exit;  
    }  
  
    bRC = true;  
  
Exit:  
    return bRC;  
}  
  
void Shutdown()  
{  
    if(g_pUnk) {  
        g_pUnk->Release();  
        g_pUnk = NULL;  
    }  
}  
  
void Usage()  
{  
    printf("EnumAssemblyAttributes: A tool to enumerate the identity   
            attributes of a given assembly.\n\n");  
    printf("Usage: EnumAssemblyAttributes AssemblyFilePath\n");  
    printf("\n");  
}  
  
int _cdecl wmain(int argc, LPCWSTR argv[])  
{  
    int     iResult = 1;  
    IUnknown                    *pUnk  = NULL;  
    IReferenceIdentity          *pRef  = NULL;  
    HRESULT                     hr     = S_OK;     
    IEnumIDENTITY_ATTRIBUTE     *pEnum = NULL;  
    BYTE                        abData[1024];  
    DWORD                       cbAvailable;  
    DWORD                       cbUsed;  
    IDENTITY_ATTRIBUTE_BLOB     *pBlob;  
  
    if(argc != 2) {  
        Usage();  
        goto Exit;  
    }  
  
    if(!Init()) {  
        printf("Failure initializing EnumIdAttr.\n");  
        goto Exit;  
    }  
  
    hr = g_pfnGetAssemblyIdentityFromFile(argv[1],   
                            __uuidof(IReferenceIdentity), &pUnk);  
  
    if (FAILED(hr)) {  
        printf("GetAssemblyIdentityFromFile failed with hr = 0x%x",   
                hr);  
        goto Exit;  
    }  
  
    hr = pUnk->QueryInterface(__uuidof(IReferenceIdentity),   
                              (void**)&pRef);  
    if (FAILED(hr)) {  
        goto Exit;  
    }  
  
    hr = pRef->EnumAttributes(&pEnum);  
    if (FAILED(hr)) {  
        printf("IReferenceIdentity::EnumAttributes failed with hr =   
                0x%x", hr);  
        goto Exit;  
    }  
  
    pBlob = (IDENTITY_ATTRIBUTE_BLOB *)(abData);  
    while (1) {  
        cbAvailable = sizeof(abData);  
        hr = pEnum->CurrentIntoBuffer(cbAvailable, abData, &cbUsed);  
        if (FAILED(hr)) {  
            printf("IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer failed   
                    with hr = 0x%x", hr);  
            goto Exit;  
        }  
  
        if (! cbUsed) {  
            break;  
        }  
  
        LPWSTR pwzNameSpace = (LPWSTR)(abData + pBlob->ofsNamespace);  
        LPWSTR pwzName      = (LPWSTR)(abData + pBlob->ofsName);  
        LPWSTR pwzValue     = (LPWSTR)(abData + pBlob->ofsValue);  
        printf("%ws: %ws = %ws\n", pwzNameSpace, pwzName, pwzValue);  
  
        hr = pEnum->Skip(1);  
        if (FAILED(hr)) {  
            printf("IEnumIDENTITY_ATTRIBUTE::Skip failed with hr =   
                    0x%x", hr);  
            goto Exit;  
        }  
    }  
  
    iResult = 0;  
  
Exit:  
  
    Shutdown();  
  
    if (pUnk) {  
        pUnk->Release();  
    }  
  
    if (pRef) {  
        pRef->Release();  
    }  
  
    if (pEnum) {  
        pEnum->Release();  
    }  
  
    return iResult;  
}  
```  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="db265-124">Örnek çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="db265-124">To run the sample</span></span>  
 <span data-ttu-id="db265-125">C:\\> EnumAssemblyAttributes.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span><span class="sxs-lookup"><span data-stu-id="db265-125">C:\\> EnumAssemblyAttributes.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span></span>  
  
### <a name="sample-output"></a><span data-ttu-id="db265-126">Örnek çıktı</span><span class="sxs-lookup"><span data-stu-id="db265-126">Sample output</span></span>  
 <span data-ttu-id="db265-127">Culture = neutral =</span><span class="sxs-lookup"><span data-stu-id="db265-127">Culture = neutral</span></span>  
  
 <span data-ttu-id="db265-128">adı Sistem =</span><span class="sxs-lookup"><span data-stu-id="db265-128">name = System</span></span>  
  
 <span data-ttu-id="db265-129">processorArchitecture = MSIL</span><span class="sxs-lookup"><span data-stu-id="db265-129">processorArchitecture = MSIL</span></span>  
  
 <span data-ttu-id="db265-130">PublicKeyToken = b77a5c561934e089</span><span class="sxs-lookup"><span data-stu-id="db265-130">PublicKeyToken = b77a5c561934e089</span></span>  
  
 <span data-ttu-id="db265-131">Sürüm 2.0.0.0 =</span><span class="sxs-lookup"><span data-stu-id="db265-131">Version = 2.0.0.0</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db265-132">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="db265-132">Requirements</span></span>  
 <span data-ttu-id="db265-133">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db265-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db265-134">**Başlık:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="db265-134">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="db265-135">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db265-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db265-136">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="db265-136">See Also</span></span>  
 [<span data-ttu-id="db265-137">Ireferenceıdentity arabirimi</span><span class="sxs-lookup"><span data-stu-id="db265-137">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)  
 [<span data-ttu-id="db265-138">Ienumıdentıty_attrıbute arabirimi</span><span class="sxs-lookup"><span data-stu-id="db265-138">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)  
 [<span data-ttu-id="db265-139">Identıty_attrıbute yapısı</span><span class="sxs-lookup"><span data-stu-id="db265-139">IDENTITY_ATTRIBUTE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-structure.md)  
 [<span data-ttu-id="db265-140">Fusion yapıları</span><span class="sxs-lookup"><span data-stu-id="db265-140">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)