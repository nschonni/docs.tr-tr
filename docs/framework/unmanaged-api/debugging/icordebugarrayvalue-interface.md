---
title: Icordebugarrayvalue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue interface
helpviewer_keywords: ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 13e226ccdcd6becc98d524c429b5cadae8d19c3e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvalue-interface1"></a><span data-ttu-id="82576-102">Icordebugarrayvalue Interface1</span><span class="sxs-lookup"><span data-stu-id="82576-102">ICorDebugArrayValue Interface1</span></span>
<span data-ttu-id="82576-103">Tek boyutlu veya çok boyutlu bir array temsil eden Icordebugheapvalue sınıfıdır.</span><span class="sxs-lookup"><span data-stu-id="82576-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="82576-104">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="82576-104">Methods</span></span>  
  
|<span data-ttu-id="82576-105">Yöntem</span><span class="sxs-lookup"><span data-stu-id="82576-105">Method</span></span>|<span data-ttu-id="82576-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="82576-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="82576-107">Getbaseındicies yöntemi</span><span class="sxs-lookup"><span data-stu-id="82576-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="82576-108">Dizideki her boyut temel dizinini alır.</span><span class="sxs-lookup"><span data-stu-id="82576-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="82576-109">GetCount yöntemi</span><span class="sxs-lookup"><span data-stu-id="82576-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="82576-110">Dizideki öğeler toplam sayısını alır.</span><span class="sxs-lookup"><span data-stu-id="82576-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="82576-111">GetDimensions yöntemi</span><span class="sxs-lookup"><span data-stu-id="82576-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="82576-112">Dizi boyutları alır.</span><span class="sxs-lookup"><span data-stu-id="82576-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="82576-113">GetElement yöntemi</span><span class="sxs-lookup"><span data-stu-id="82576-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="82576-114">Dizideki verilen öğe temsil eden bir değer alır.</span><span class="sxs-lookup"><span data-stu-id="82576-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="82576-115">GetElementAtPosition yöntemi</span><span class="sxs-lookup"><span data-stu-id="82576-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="82576-116">Verilen konumunda dizinin sıfır tabanlı, tek boyutlu bir dizi olarak davranma öğeyi alır.</span><span class="sxs-lookup"><span data-stu-id="82576-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="82576-117">GetElementType yöntemi</span><span class="sxs-lookup"><span data-stu-id="82576-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="82576-118">Dizideki öğeleri basit türünü alır.</span><span class="sxs-lookup"><span data-stu-id="82576-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="82576-119">GetRank yöntemi</span><span class="sxs-lookup"><span data-stu-id="82576-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="82576-120">Dizideki boyut sayısını alır.</span><span class="sxs-lookup"><span data-stu-id="82576-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="82576-121">Hasbaseındicies yöntemi</span><span class="sxs-lookup"><span data-stu-id="82576-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="82576-122">Dizi temel dizinleri olup olmadığını belirler.</span><span class="sxs-lookup"><span data-stu-id="82576-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82576-123">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="82576-123">Remarks</span></span>  
 <span data-ttu-id="82576-124">`ICorDebugArrayValue`tek boyutlu ve çok boyutlu diziler destekler.</span><span class="sxs-lookup"><span data-stu-id="82576-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82576-125">Bu arabirim, makineler arası veya çapraz işlem uzaktan çağrılan desteklemez.</span><span class="sxs-lookup"><span data-stu-id="82576-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82576-126">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="82576-126">Requirements</span></span>  
 <span data-ttu-id="82576-127">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82576-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82576-128">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82576-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82576-129">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82576-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82576-130">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82576-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82576-131">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="82576-131">See Also</span></span>  
 [<span data-ttu-id="82576-132">Hata ayıklama arabirimleri</span><span class="sxs-lookup"><span data-stu-id="82576-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)