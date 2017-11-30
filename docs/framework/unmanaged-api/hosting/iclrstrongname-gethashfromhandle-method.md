---
title: ICLRStrongName::GetHashFromHandle Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 01fefe99e82584267b3c0f3e0e528dd798affa15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="f426e-102">ICLRStrongName::GetHashFromHandle Metodu</span><span class="sxs-lookup"><span data-stu-id="f426e-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="f426e-103">Bir karma belirtilen karma algoritması kullanılarak belirtilen dosya tanıtıcısı sahip bir dosya içeriğini oluşturur.</span><span class="sxs-lookup"><span data-stu-id="f426e-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f426e-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="f426e-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f426e-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="f426e-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="f426e-106">[in] Karma hale getirilmesi için dosya tanıtıcısı.</span><span class="sxs-lookup"><span data-stu-id="f426e-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="f426e-107">[içinde out] Karma algoritmasını belirtir sabiti.</span><span class="sxs-lookup"><span data-stu-id="f426e-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="f426e-108">Varsayılan algoritma için sıfır değerini kullanın.</span><span class="sxs-lookup"><span data-stu-id="f426e-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="f426e-109">[out] Döndürülen karma arabellek.</span><span class="sxs-lookup"><span data-stu-id="f426e-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="f426e-110">[in] İstenen en büyük boyutunu `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f426e-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="f426e-111">[out] Dönen bayt cinsinden boyutu `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f426e-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f426e-112">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="f426e-112">Return Value</span></span>  
 <span data-ttu-id="f426e-113">`S_OK`Yöntem başarıyla tamamlandı Aksi takdirde hata belirten bir HRESULT değeri (bkz [ortak HRESULT değerleri](http://go.microsoft.com/fwlink/?LinkId=213878) bir listesi için).</span><span class="sxs-lookup"><span data-stu-id="f426e-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f426e-114">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="f426e-114">Requirements</span></span>  
 <span data-ttu-id="f426e-115">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f426e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f426e-116">**Başlık:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f426e-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f426e-117">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="f426e-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f426e-118">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f426e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f426e-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f426e-119">See Also</span></span>  
 [<span data-ttu-id="f426e-120">Iclrstrongname arabirimi</span><span class="sxs-lookup"><span data-stu-id="f426e-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)