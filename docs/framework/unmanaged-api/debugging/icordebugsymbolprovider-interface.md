---
title: ICorDebugSymbolProvider arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 96f5d897b1f426fd85fd274d5e56e8726b8cb892
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="281ea-102">ICorDebugSymbolProvider arabirimi</span><span class="sxs-lookup"><span data-stu-id="281ea-102">ICorDebugSymbolProvider Interface</span></span>
<span data-ttu-id="281ea-103">Hata ayıklama sembol bilgilerini almak için kullanılan yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="281ea-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="281ea-104">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="281ea-104">Methods</span></span>  
  
|<span data-ttu-id="281ea-105">Yöntem</span><span class="sxs-lookup"><span data-stu-id="281ea-105">Method</span></span>|<span data-ttu-id="281ea-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="281ea-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="281ea-107">GetAssemblyImageBytes yöntemi</span><span class="sxs-lookup"><span data-stu-id="281ea-107">GetAssemblyImageBytes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="281ea-108">Birleştirilmiş derlemede göreli sanal adres (RVA) verilen birleştirilmiş bir bütünleştirilmiş koddan verileri okur.</span><span class="sxs-lookup"><span data-stu-id="281ea-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="281ea-109">GetAssemblyImageMetadata yöntemi</span><span class="sxs-lookup"><span data-stu-id="281ea-109">GetAssemblyImageMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="281ea-110">Birleştirilmiş bir derlemeye ait meta verileri döndürür.</span><span class="sxs-lookup"><span data-stu-id="281ea-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="281ea-111">GetCodeRange yöntemi</span><span class="sxs-lookup"><span data-stu-id="281ea-111">GetCodeRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="281ea-112">Yöntemi başlangıç adresi ve bir yöntem göreli sanal adres (RVA) verilen boyutunu alır.</span><span class="sxs-lookup"><span data-stu-id="281ea-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="281ea-113">GetInstanceFieldSymbols yöntemi</span><span class="sxs-lookup"><span data-stu-id="281ea-113">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="281ea-114">Örnek TypeSpec'te imza karşılık gelen alan simgelerini alır.</span><span class="sxs-lookup"><span data-stu-id="281ea-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="281ea-115">GetMergedAssemblyRecords yöntemi</span><span class="sxs-lookup"><span data-stu-id="281ea-115">GetMergedAssemblyRecords Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="281ea-116">Sembol kayıtları için tüm birleştirilmiş derlemeleri alır.</span><span class="sxs-lookup"><span data-stu-id="281ea-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="281ea-117">GetMethodLocalSymbols yöntemi</span><span class="sxs-lookup"><span data-stu-id="281ea-117">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="281ea-118">Bu yöntemin göreli sanal adres (RVA) verilen bir yöntemin yerel simgelerini alır.</span><span class="sxs-lookup"><span data-stu-id="281ea-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="281ea-119">GetMethodParameterSymbols yöntemi</span><span class="sxs-lookup"><span data-stu-id="281ea-119">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="281ea-120">Bu yöntemin göreli sanal adres (RVA) verilen bir yöntemin parametre simgelerini alır.</span><span class="sxs-lookup"><span data-stu-id="281ea-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="281ea-121">GetMethodProps yöntemi</span><span class="sxs-lookup"><span data-stu-id="281ea-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="281ea-122">Bu yönteme göreli sanal adres (RVA) verilen yöntemin meta veri simgesi ve kendi genel parametreleri hakkında bilgi gibi yöntemi özellikleri hakkında bilgi döndürür.</span><span class="sxs-lookup"><span data-stu-id="281ea-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="281ea-123">GetObjectSize yöntemi</span><span class="sxs-lookup"><span data-stu-id="281ea-123">GetObjectSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="281ea-124">TypeSpec'te imzası dayalı bir nesne için nesne boyutu döndürür.</span><span class="sxs-lookup"><span data-stu-id="281ea-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="281ea-125">GetStaticFieldSymbols yöntemi</span><span class="sxs-lookup"><span data-stu-id="281ea-125">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="281ea-126">TypeSpec'te imza karşılık gelen statik alan simgelerini alır.</span><span class="sxs-lookup"><span data-stu-id="281ea-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="281ea-127">GetTypeProps yöntemi</span><span class="sxs-lookup"><span data-stu-id="281ea-127">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="281ea-128">Göreli sanal adres (RAV) bir vtable verilen imza genel parametrelerinin sayısı gibi bir tür özellikleri hakkında bilgi döndürür.</span><span class="sxs-lookup"><span data-stu-id="281ea-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="281ea-129">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="281ea-129">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="281ea-130">Bu arabirim yalnızca .NET yerel ile kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="281ea-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="281ea-131">Bu arabirim .NET yerel dışında Icordebug senaryoları için uygularsanız, ortak dil çalışma zamanı bu arabirim göz ardı eder.</span><span class="sxs-lookup"><span data-stu-id="281ea-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="281ea-132">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="281ea-132">Requirements</span></span>  
 <span data-ttu-id="281ea-133">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="281ea-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="281ea-134">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="281ea-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="281ea-135">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="281ea-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="281ea-136">**.NET framework sürümleri:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="281ea-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="281ea-137">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="281ea-137">See Also</span></span>  
 [<span data-ttu-id="281ea-138">Hata ayıklama arabirimleri</span><span class="sxs-lookup"><span data-stu-id="281ea-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="281ea-139">Hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="281ea-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)