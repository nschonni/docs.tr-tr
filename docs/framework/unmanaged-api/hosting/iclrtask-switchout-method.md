---
title: "ICLRTask::SwitchOut Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.SwitchOut
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 82fffd5de9735db51d9ea5f417c745736b98b53d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="05c09-102">ICLRTask::SwitchOut Yöntemi</span><span class="sxs-lookup"><span data-stu-id="05c09-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="05c09-103">Geçerli görev temsil ortak dil çalışma zamanı (CLR) bildirir [Iclrtask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) örneğidir artık çalıştırılabilir bir durumda.</span><span class="sxs-lookup"><span data-stu-id="05c09-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05c09-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="05c09-104">Syntax</span></span>  
  
```  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="05c09-105">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="05c09-105">Return Value</span></span>  
  
|<span data-ttu-id="05c09-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="05c09-106">HRESULT</span></span>|<span data-ttu-id="05c09-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="05c09-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="05c09-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="05c09-108">S_OK</span></span>|<span data-ttu-id="05c09-109">`SwitchOut`başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="05c09-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="05c09-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="05c09-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="05c09-111">CLR süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.</span><span class="sxs-lookup"><span data-stu-id="05c09-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="05c09-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="05c09-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="05c09-113">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="05c09-113">The call timed out.</span></span>|  
|<span data-ttu-id="05c09-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="05c09-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="05c09-115">Arayan kilidi kendisine ait değil.</span><span class="sxs-lookup"><span data-stu-id="05c09-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="05c09-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="05c09-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="05c09-117">Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.</span><span class="sxs-lookup"><span data-stu-id="05c09-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="05c09-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="05c09-118">E_FAIL</span></span>|<span data-ttu-id="05c09-119">Bilinmeyen yıkıcı bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="05c09-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="05c09-120">Bir yöntem E_FAIL döndüğünde, CLR artık işlemi içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="05c09-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="05c09-121">Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="05c09-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05c09-122">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="05c09-122">Remarks</span></span>  
 <span data-ttu-id="05c09-123">Bir konak çağırır `SwitchOut` geçici olarak görev yürütülmeden durdurduğu CLR bildirmek için geçerli `ICLRTask` örneği temsil eder ve görevi yeniden zamanlayın.</span><span class="sxs-lookup"><span data-stu-id="05c09-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05c09-124">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="05c09-124">Requirements</span></span>  
 <span data-ttu-id="05c09-125">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05c09-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05c09-126">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="05c09-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05c09-127">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="05c09-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05c09-128">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05c09-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c09-129">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="05c09-129">See Also</span></span>  
 [<span data-ttu-id="05c09-130">Iclrtask arabirimi</span><span class="sxs-lookup"><span data-stu-id="05c09-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="05c09-131">Iclrtaskmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="05c09-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="05c09-132">Ihosttask arabirimi</span><span class="sxs-lookup"><span data-stu-id="05c09-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="05c09-133">Ihosttaskmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="05c09-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)