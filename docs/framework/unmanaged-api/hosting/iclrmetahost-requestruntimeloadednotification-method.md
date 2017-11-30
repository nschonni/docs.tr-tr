---
title: "ICLRMetaHost::RequestRuntimeLoadedNotification Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.RequestRuntimeLoadedNotification
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 32eb92263685bc3be9f0c28dea88ecfa78c2b52c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="27aed-102">ICLRMetaHost::RequestRuntimeLoadedNotification Yöntemi</span><span class="sxs-lookup"><span data-stu-id="27aed-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="27aed-103">Ortak dil çalışma zamanı (CLR) sürüm ilk yüklendi, ancak henüz başlamamış çağrılacak garanti bir geri çağırma işlevi sağlar.</span><span class="sxs-lookup"><span data-stu-id="27aed-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="27aed-104">Bu yöntem yerini [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="27aed-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27aed-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="27aed-105">Syntax</span></span>  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27aed-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="27aed-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="27aed-107">[in] Yeni bir çalışma zamanı yüklendiğinde çağrılan geri çağırma işlevi.</span><span class="sxs-lookup"><span data-stu-id="27aed-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27aed-108">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="27aed-108">Return Value</span></span>  
 <span data-ttu-id="27aed-109">Bu yöntem aşağıdaki belirli HRESULTs yanı sıra HRESULT yöntem hatası olduğunu gösteren hatalar.</span><span class="sxs-lookup"><span data-stu-id="27aed-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="27aed-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27aed-110">HRESULT</span></span>|<span data-ttu-id="27aed-111">Açıklama</span><span class="sxs-lookup"><span data-stu-id="27aed-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27aed-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="27aed-112">S_OK</span></span>|<span data-ttu-id="27aed-113">Yöntem başarıyla tamamlandı.</span><span class="sxs-lookup"><span data-stu-id="27aed-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="27aed-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="27aed-114">E_POINTER</span></span>|<span data-ttu-id="27aed-115">`pCallbackFunction`null şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="27aed-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27aed-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="27aed-116">Remarks</span></span>  
 <span data-ttu-id="27aed-117">Geri çağırma aşağıdaki şekilde çalışır:</span><span class="sxs-lookup"><span data-stu-id="27aed-117">The callback works in the following way:</span></span>  
  
-   <span data-ttu-id="27aed-118">Yalnızca bir çalışma zamanı ilk kez yüklendiğinde geri çağırma çağrılır.</span><span class="sxs-lookup"><span data-stu-id="27aed-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
-   <span data-ttu-id="27aed-119">Geri çağırma desteklemeyeceğini aynı çalışma zamanı yükler için çağrılır.</span><span class="sxs-lookup"><span data-stu-id="27aed-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
-   <span data-ttu-id="27aed-120">Yeniden girme olmayan çalışma zamanı yükler için geri çağırma işlevi çağrıları serileştirilir.</span><span class="sxs-lookup"><span data-stu-id="27aed-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="27aed-121">Geri çağırma işlevi aşağıdaki prototipe sahiptir:</span><span class="sxs-lookup"><span data-stu-id="27aed-121">The callback function has the following prototype:</span></span>  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="27aed-122">Geri çağırma işlev prototipleri aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="27aed-122">The callback function prototypes are as follows:</span></span>  
  
-   <span data-ttu-id="27aed-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="27aed-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
-   <span data-ttu-id="27aed-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="27aed-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="27aed-125">Ana bilgisayar yüklenemiyor veya desteklemeyeceğini bir şekilde yüklenmesi başka bir çalışma zamanı neden çalışırsa `pfnCallbackThreadSet` ve `pfnCallbackThreadUnset` aşağıdaki şekilde geri işlevi kullanılması gereken sağlanan Parametreler:</span><span class="sxs-lookup"><span data-stu-id="27aed-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
-   <span data-ttu-id="27aed-126">`pfnCallbackThreadSet`Bu tür bir yük denenmeden önce bir çalışma zamanı yüküne neden iş parçacığı tarafından çağrılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="27aed-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
-   <span data-ttu-id="27aed-127">`pfnCallbackThreadUnset`iş parçacığı artık böyle bir çalışma zamanı yükleme neden olur (ve ten ilk geri dönmeden önce) çağrılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="27aed-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
-   <span data-ttu-id="27aed-128">`pfnCallbackThreadSet`ve `pfnCallbackThreadUnset` hem de yeniden girme olmayan olması.</span><span class="sxs-lookup"><span data-stu-id="27aed-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27aed-129">Ana bilgisayar uygulamaları değil çağırmalıdır `pfnCallbackThreadSet` ve `pfnCallbackThreadUnset` kapsamı dışında `pCallbackFunction` parametresi.</span><span class="sxs-lookup"><span data-stu-id="27aed-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27aed-130">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="27aed-130">Requirements</span></span>  
 <span data-ttu-id="27aed-131">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27aed-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27aed-132">**Başlık:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="27aed-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="27aed-133">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="27aed-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27aed-134">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27aed-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27aed-135">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="27aed-135">See Also</span></span>  
 [<span data-ttu-id="27aed-136">Iclrmetahost arabirimi</span><span class="sxs-lookup"><span data-stu-id="27aed-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="27aed-137">Barındırma</span><span class="sxs-lookup"><span data-stu-id="27aed-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)