---
title: ICLRErrorReportingManager::GetBucketParametersForCurrentException Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80bf3e9b1cee9f19534f985dccf4508467dbe26e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="64426-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Metodu</span><span class="sxs-lookup"><span data-stu-id="64426-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="64426-103">Geçerli özel durumun çağıran iş parçacığı üzerinde Watson demet alır.</span><span class="sxs-lookup"><span data-stu-id="64426-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="64426-104">A *demet* aynı kod hatası için ilgili hata verileri koleksiyonudur.</span><span class="sxs-lookup"><span data-stu-id="64426-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="64426-105">*Watson* toplama ve bir özel durum ile ilişkili verileri çözümlemek için teknoloji başvuruyor.</span><span class="sxs-lookup"><span data-stu-id="64426-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64426-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="64426-106">Syntax</span></span>  
  
```  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64426-107">Parametreler</span><span class="sxs-lookup"><span data-stu-id="64426-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="64426-108">[out] Bir işaretçi bir [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) özel durum için hata verileri içeren yapısı.</span><span class="sxs-lookup"><span data-stu-id="64426-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64426-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="64426-109">Requirements</span></span>  
 <span data-ttu-id="64426-110">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64426-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64426-111">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="64426-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64426-112">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="64426-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64426-113">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64426-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64426-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="64426-114">See Also</span></span>  
 [<span data-ttu-id="64426-115">Iclrerrorreportingmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="64426-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)