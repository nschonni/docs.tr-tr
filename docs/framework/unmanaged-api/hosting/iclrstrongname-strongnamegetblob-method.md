---
title: "ICLRStrongName::StrongNameGetBlob Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d4ae90367cb84c97d5964ceb815943249af7b240
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="c845c-102">ICLRStrongName::StrongNameGetBlob Yöntemi</span><span class="sxs-lookup"><span data-stu-id="c845c-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="c845c-103">Belirtilen arabellek yürütülebilir dosyanın belirtilen adresteki ikili gösterimidir doldurur.</span><span class="sxs-lookup"><span data-stu-id="c845c-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c845c-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c845c-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c845c-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="c845c-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c845c-106">[in] Yüklenecek yürütülebilir dosyanın geçerli bir yol.</span><span class="sxs-lookup"><span data-stu-id="c845c-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="c845c-107">[in] Arabelleğe hangi yürütülebilir dosyası yüklenemiyor.</span><span class="sxs-lookup"><span data-stu-id="c845c-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="c845c-108">[içinde out] Bayt cinsinden en büyük boyutu, istenen `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="c845c-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="c845c-109">Return, bayt cinsinden gerçek boyutu bağlı, `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="c845c-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c845c-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="c845c-110">Return Value</span></span>  
 <span data-ttu-id="c845c-111">`S_OK`Yöntem başarıyla tamamlandı Aksi takdirde hata belirten bir HRESULT değeri (bkz [ortak HRESULT değerleri](http://go.microsoft.com/fwlink/?LinkId=213878) bir listesi için).</span><span class="sxs-lookup"><span data-stu-id="c845c-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c845c-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="c845c-112">Requirements</span></span>  
 <span data-ttu-id="c845c-113">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c845c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c845c-114">**Başlık:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c845c-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c845c-115">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="c845c-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c845c-116">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c845c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c845c-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c845c-117">See Also</span></span>  
 [<span data-ttu-id="c845c-118">Strongnamegetblobfromımage yöntemi</span><span class="sxs-lookup"><span data-stu-id="c845c-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="c845c-119">Iclrstrongname arabirimi</span><span class="sxs-lookup"><span data-stu-id="c845c-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)