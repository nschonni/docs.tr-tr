---
title: ICorDebugCode3::GetReturnValueLiveOffset Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugCode3.GetReturnValueLiveOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4516f2244b72bd4f254c5090b09d6d90579f1ae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="e97c9-102">ICorDebugCode3::GetReturnValueLiveOffset Metodu</span><span class="sxs-lookup"><span data-stu-id="e97c9-102">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>
<span data-ttu-id="e97c9-103">Belirtilen bir IL uzaklığı, hata ayıklayıcı dönüş değeri bir işleve alabilmesi adına, bir kesme noktası nereye yerleştirileceğini yerel uzaklıkları alır.</span><span class="sxs-lookup"><span data-stu-id="e97c9-103">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e97c9-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e97c9-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e97c9-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="e97c9-105">Parameters</span></span>  
 `ILoffset`  
 <span data-ttu-id="e97c9-106">IL uzaklığı.</span><span class="sxs-lookup"><span data-stu-id="e97c9-106">The IL offset.</span></span> <span data-ttu-id="e97c9-107">Bir işlev çağrısı site olmalı veya işlev çağrısı başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="e97c9-107">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="e97c9-108">Depolamak kullanılabilir bayt sayısını `pOffsets`.</span><span class="sxs-lookup"><span data-stu-id="e97c9-108">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="e97c9-109">Gerçekte döndürülen uzaklıkları sayısı için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="e97c9-109">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="e97c9-110">Genellikle, değer 1'dir, ancak tek bir IL yönergesi birden çok eşleyebilirsiniz `CALL` derleme yönergeleri.</span><span class="sxs-lookup"><span data-stu-id="e97c9-110">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="e97c9-111">Yerel uzaklıkları dizisi.</span><span class="sxs-lookup"><span data-stu-id="e97c9-111">An array of native offsets.</span></span> <span data-ttu-id="e97c9-112">Genellikle, `pOffsets` tek bir IL yönergesi birden çok eşlemek üzere birden çok eşleyebilirsiniz rağmen tek bir uzaklık içerir `CALL` derleme yönergeleri.</span><span class="sxs-lookup"><span data-stu-id="e97c9-112">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e97c9-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e97c9-113">Remarks</span></span>  
 <span data-ttu-id="e97c9-114">Bu yöntem ile birlikte kullanılan [Icordebugılframe3::getreturnvalueforıloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) bir başvuru türü döndüren bir yöntem dönüş değerini almak için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="e97c9-114">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="e97c9-115">Bu yöntemin bir işlev çağrısı siteye uzaklığı bir IL geçirme bir veya daha fazla yerel uzaklıklarını döndürür.</span><span class="sxs-lookup"><span data-stu-id="e97c9-115">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="e97c9-116">Hata ayıklayıcı kesme noktaları bu yerel uzaklıkları işlevinde sonra ayarlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e97c9-116">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="e97c9-117">Hata ayıklayıcı kesme noktaları geldiğinde, bu yönteme geçirilen aynı IL uzaklığı sonra geçirebilirsiniz [Icordebugılframe3::getreturnvalueforıloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) dönüş değerini almak için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="e97c9-117">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="e97c9-118">Hata ayıklayıcı sonra ayarlayın kesme noktaları temizlemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="e97c9-118">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e97c9-119">`ICorDebugCode3::GetReturnValueLiveOffset` Ve [Icordebugılframe3::getreturnvalueforıloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) yöntemleri yalnızca başvuru türleri dönüş değeri bilgilerini edinin izin verir.</span><span class="sxs-lookup"><span data-stu-id="e97c9-119">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="e97c9-120">Değer türlerinden dönüş değeri bilgileri alınıyor (diğer bir deyişle, türetilen tüm türleri <xref:System.ValueType>) desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="e97c9-120">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="e97c9-121">İşlevi döndürür `HRESULT` aşağıdaki tabloda gösterilen değerleri.</span><span class="sxs-lookup"><span data-stu-id="e97c9-121">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="e97c9-122">`HRESULT`değer</span><span class="sxs-lookup"><span data-stu-id="e97c9-122">`HRESULT` value</span></span>|<span data-ttu-id="e97c9-123">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e97c9-123">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="e97c9-124">Başarılı.</span><span class="sxs-lookup"><span data-stu-id="e97c9-124">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="e97c9-125">Verilen IL uzaklığı sitesini bir çağrı yönergesi değil ya da işlevi döndürür `void`.</span><span class="sxs-lookup"><span data-stu-id="e97c9-125">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="e97c9-126">Verilen IL uzaklığı, uygun bir çağrı olmakla birlikte bir dönüş değeri almak için dönüş türü desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="e97c9-126">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="e97c9-127">`ICorDebugCode3::GetReturnValueLiveOffset` Yöntemi yalnızca x86 tabanlı üzerinde kullanılabilir ve AMD64 sistemleri.</span><span class="sxs-lookup"><span data-stu-id="e97c9-127">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e97c9-128">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="e97c9-128">Requirements</span></span>  
 <span data-ttu-id="e97c9-129">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e97c9-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e97c9-130">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e97c9-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e97c9-131">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e97c9-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e97c9-132">**.NET framework sürümleri:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e97c9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e97c9-133">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e97c9-133">See Also</span></span>  
 [<span data-ttu-id="e97c9-134">Getreturnvalueforıloffset yöntemi</span><span class="sxs-lookup"><span data-stu-id="e97c9-134">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)  
 [<span data-ttu-id="e97c9-135">Icordebugcode3 arabirimi</span><span class="sxs-lookup"><span data-stu-id="e97c9-135">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)