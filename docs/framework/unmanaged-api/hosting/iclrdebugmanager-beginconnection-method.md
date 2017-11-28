---
title: "ICLRDebugManager::BeginConnection Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.BeginConnection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 302b2abfdde7bbccbef51de21233948d042420be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="8af59-102">ICLRDebugManager::BeginConnection Yöntemi</span><span class="sxs-lookup"><span data-stu-id="8af59-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="8af59-103">Ana bilgisayar ve hata ayıklayıcısı görevlerin bir listesi bir tanımlayıcı ve kolay bir ad ile ilişkilendirmek için arasında yeni bir bağlantı kurar.</span><span class="sxs-lookup"><span data-stu-id="8af59-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af59-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="8af59-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8af59-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="8af59-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="8af59-106">[in] Ortak dil çalışma zamanı (CLR) görevler liste ile ilişkilendirmek için tanımlayıcı.</span><span class="sxs-lookup"><span data-stu-id="8af59-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="8af59-107">[in] CLR görevlerinin listesi ile ilişkilendirmek için bir kolay ad.</span><span class="sxs-lookup"><span data-stu-id="8af59-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8af59-108">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="8af59-108">Return Value</span></span>  
  
|<span data-ttu-id="8af59-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8af59-109">HRESULT</span></span>|<span data-ttu-id="8af59-110">Açıklama</span><span class="sxs-lookup"><span data-stu-id="8af59-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8af59-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8af59-111">S_OK</span></span>|<span data-ttu-id="8af59-112">`BeginConnection`başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="8af59-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="8af59-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8af59-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8af59-114">CLR süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.</span><span class="sxs-lookup"><span data-stu-id="8af59-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8af59-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8af59-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8af59-116">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="8af59-116">The call timed out.</span></span>|  
|<span data-ttu-id="8af59-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8af59-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8af59-118">Arayan kilidi kendisine ait değil.</span><span class="sxs-lookup"><span data-stu-id="8af59-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8af59-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8af59-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8af59-120">Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.</span><span class="sxs-lookup"><span data-stu-id="8af59-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8af59-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8af59-121">E_FAIL</span></span>|<span data-ttu-id="8af59-122">Bilinmeyen yıkıcı bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="8af59-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8af59-123">CLR, artık bir yöntem E_FAIL döndükten sonra işlemi içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="8af59-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8af59-124">Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="8af59-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8af59-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8af59-125">E_INVALIDARG</span></span>|<span data-ttu-id="8af59-126">`dwConnectionId`sıfır oluştu veya `BeginConnection` bu kullanarak zaten çağrıldı `dwConnectionId` değeri veya `szConnectionName` null idi.</span><span class="sxs-lookup"><span data-stu-id="8af59-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="8af59-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8af59-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8af59-128">Bu bağlantı ile ilişkili görevleri listesini tutmak için yeterli bellek ayrılamadı.</span><span class="sxs-lookup"><span data-stu-id="8af59-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8af59-129">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8af59-129">Remarks</span></span>  
 <span data-ttu-id="8af59-130">[Iclrdebugmanager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) üç yöntem sunar `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), ve [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), görev listeleri tanımlayıcıları ve kolay adlar ile ilişkilendirme.</span><span class="sxs-lookup"><span data-stu-id="8af59-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8af59-131">Bu üç yöntem, her bir dizi görevi için belirli bir sırayla çağrılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="8af59-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="8af59-132">`BeginConnection`Yeni bir bağlantı kurmak için önce çağrılır.</span><span class="sxs-lookup"><span data-stu-id="8af59-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="8af59-133">`SetConnectionTasks`ardından bu bağlantı ile ilişkili görevleri kümesi sağlamak için çağrılır.</span><span class="sxs-lookup"><span data-stu-id="8af59-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="8af59-134">`EndConnection`Görev listesi ve tanımlayıcısı ve kolay ad arasındaki ilişkiyi kaldırmak için son çağrılır. Ancak, çağrıları farklı bağlantılar için iç içe.</span><span class="sxs-lookup"><span data-stu-id="8af59-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8af59-135">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="8af59-135">Requirements</span></span>  
 <span data-ttu-id="8af59-136">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8af59-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8af59-137">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8af59-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8af59-138">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="8af59-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8af59-139">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8af59-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af59-140">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8af59-140">See Also</span></span>  
 [<span data-ttu-id="8af59-141">Iclrcontrol arabirimi</span><span class="sxs-lookup"><span data-stu-id="8af59-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="8af59-142">Iclrdebugmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="8af59-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="8af59-143">EndConnection yöntemi</span><span class="sxs-lookup"><span data-stu-id="8af59-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)  
 [<span data-ttu-id="8af59-144">SetConnectionTasks yöntemi</span><span class="sxs-lookup"><span data-stu-id="8af59-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [<span data-ttu-id="8af59-145">Ihostcontrol arabirimi</span><span class="sxs-lookup"><span data-stu-id="8af59-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)