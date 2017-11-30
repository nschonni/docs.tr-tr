---
title: "CorDebugThreadState Numaralandırması"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugThreadState
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugThreadState
helpviewer_keywords: CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dc3555d0ecd85208688a4aae69aef7c6c88303b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="3622d-102">CorDebugThreadState Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="3622d-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="3622d-103">Hata ayıklama için bir iş parçacığı durumunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="3622d-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3622d-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3622d-104">Syntax</span></span>  
  
```  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="3622d-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="3622d-105">Members</span></span>  
  
|<span data-ttu-id="3622d-106">Üye</span><span class="sxs-lookup"><span data-stu-id="3622d-106">Member</span></span>|<span data-ttu-id="3622d-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="3622d-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="3622d-108">Hata ayıklama olayı oluşmadığı sürece ücretsiz olarak, iş parçacığı çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="3622d-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="3622d-109">İş parçacığı çalıştırılamıyor.</span><span class="sxs-lookup"><span data-stu-id="3622d-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3622d-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3622d-110">Remarks</span></span>  
 <span data-ttu-id="3622d-111">Hata ayıklayıcı kullanan `CorDebugThreadState` bir iş parçacığının yürütme denetlemek için numaralandırması.</span><span class="sxs-lookup"><span data-stu-id="3622d-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="3622d-112">Bir iş parçacığı durumu kullanarak ayarlayabilirsiniz [Icordebugthread::setdebugstate](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) veya [Icordebugcontroller::setallthreadsdebugstate](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3622d-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="3622d-113">Sağlanan bir geri çağırma [API barındırma](../../../../docs/framework/unmanaged-api/hosting/index.md) kesintiye uğramış bir durum gerekli olmadığı için ileti Pompalama, sağlar.</span><span class="sxs-lookup"><span data-stu-id="3622d-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3622d-114">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="3622d-114">Requirements</span></span>  
 <span data-ttu-id="3622d-115">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3622d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3622d-116">**Başlık:** CorDebug.idl, CorDegug.h</span><span class="sxs-lookup"><span data-stu-id="3622d-116">**Header:** CorDebug.idl, CorDegug.h</span></span>  
  
 <span data-ttu-id="3622d-117">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3622d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3622d-118">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3622d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3622d-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3622d-119">See Also</span></span>  
 [<span data-ttu-id="3622d-120">Hata ayıklama numaralandırmaları</span><span class="sxs-lookup"><span data-stu-id="3622d-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)