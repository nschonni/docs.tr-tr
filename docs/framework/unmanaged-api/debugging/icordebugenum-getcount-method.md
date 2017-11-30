---
title: ICorDebugEnum::GetCount Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEnum.GetCount
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEnum::GetCount
helpviewer_keywords:
- ICorDebugEnum::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: d8a74304-1cb2-4977-a21d-e1af48c563ff
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bca3631f9c7a8f6ec3d145f8573241642cb1b1c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="3d8dc-102">ICorDebugEnum::GetCount Metodu</span><span class="sxs-lookup"><span data-stu-id="3d8dc-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="3d8dc-103">Sabit listede öğe sayısını alır.</span><span class="sxs-lookup"><span data-stu-id="3d8dc-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d8dc-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3d8dc-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d8dc-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="3d8dc-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="3d8dc-106">[out] Listedeki öğe sayısı için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="3d8dc-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d8dc-107">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="3d8dc-107">Requirements</span></span>  
 <span data-ttu-id="3d8dc-108">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d8dc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d8dc-109">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d8dc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d8dc-110">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d8dc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d8dc-111">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d8dc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>