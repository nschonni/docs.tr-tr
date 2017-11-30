---
title: "CompareAssemblyIdentity İşlevi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type: COM
f1_keywords: CompareAssemblyIdentity
helpviewer_keywords: CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d9d7b4934d4295ee799fb13d3d749e6b977e644
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="7ff1f-102">CompareAssemblyIdentity İşlevi</span><span class="sxs-lookup"><span data-stu-id="7ff1f-102">CompareAssemblyIdentity Function</span></span>
<span data-ttu-id="7ff1f-103">Eşdeğer olup olmadıklarını belirlemek için iki derleme kimlikleri karşılaştırır.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ff1f-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7ff1f-104">Syntax</span></span>  
  
```  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ff1f-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="7ff1f-105">Parameters</span></span>  
 `pwzAssemblyIdentity1`  
 <span data-ttu-id="7ff1f-106">[in] Karşılaştırma ilk derlemede metinsel kimliği.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="7ff1f-107">[in] Kullanıcı tarafından belirtilen Birleştirici için gösteren bir Boole bayrağı `pwzAssemblyIdentity1`.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="7ff1f-108">[in] Karşılaştırma ikinci derlemede metinsel kimliği.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="7ff1f-109">[in] Kullanıcı tarafından belirtilen Birleştirici için gösteren bir Boole bayrağı `pwzAssemblyIdentity2`.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="7ff1f-110">[out] İki derleme eşdeğer olup olmadığını gösteren bir Boole bayrak.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="7ff1f-111">[out] Bir [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) karşılaştırması hakkında ayrıntılı bilgi içeren numaralandırması.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-111">[out] An [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ff1f-112">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="7ff1f-112">Return Value</span></span>  
 <span data-ttu-id="7ff1f-113">`pfEquivalent`İki derleme eşdeğer olup olmadığını gösteren bir Boole değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="7ff1f-114">`pResult`aşağıdakilerden birini döndürür `AssemblyComparisonResult` değerine ilişkin daha ayrıntılı bir nedenle vermek için değerleri `pfEquivalent`.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ff1f-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7ff1f-115">Remarks</span></span>  
 <span data-ttu-id="7ff1f-116">`CompareAssemblyIdentity`denetler olup olmadığını `pwzAssemblyIdentity1` ve `pwzAssemblyIdentity2` eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="7ff1f-117">`pfEquivalent`ayarlanmış `true` altında bir veya daha fazla aşağıdaki koşullardan biri:</span><span class="sxs-lookup"><span data-stu-id="7ff1f-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
-   <span data-ttu-id="7ff1f-118">İki derleme kimlikleri eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="7ff1f-119">Türü kesin adlandırılmış derlemeler için derleme adı, sürüm, ortak anahtar belirteci ve aynı olacak şekilde kültür denkliği gerektirir.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="7ff1f-120">Yalnızca adlandırılmış derlemeler için derleme adı ve kültür bir eşleşme denkliği gerektirir.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
-   <span data-ttu-id="7ff1f-121">Hem derleme kimlikleri .NET Framework üzerine Çalıştır derlemeleri bakın.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="7ff1f-122">Bu durum döndürür `true` dahi derleme sürüm numaraları eşleşmiyor.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
-   <span data-ttu-id="7ff1f-123">İki derleme Yönetilen derlemeler değildir ancak `fUnified1` veya `fUnified2` ayarlandı `true`.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="7ff1f-124">`fUnified` Bayrağı gösterir tüm sürüm numaralarını kesin adlandırılmış derleme sürüm sayısı kadar kesin adlandırılmış derlemeye eşdeğer olarak değerlendiriliyor.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="7ff1f-125">Örneğin, varsa değerini `pwzAssemblyIndentity1` olan "MyAssembly, sürüm 3.0.0.0, culture = neutral, publicKeyToken = =...", değerini `fUnified1` olan `true`, bu sürüm için 0.0.0.0 3.0.0.0 MyAssembly'nin tüm sürümleri olması gerektiğini gösterir eşdeğer olarak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="7ff1f-126">Böyle bir durumda olmadığını `pwzAssemblyIndentity2` aynı bütünleştirilmiş başvurduğu `pwzAssemblyIndentity1`, daha düşük bir sürüm numarası olan dışında `pfEquivalent` ayarlanır `true`.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="7ff1f-127">Varsa `pwzAssemblyIdentity2` daha yüksek bir sürüm numarası, başvuruyor `pfEquivalent` ayarlanır `true` yalnızca değerini `fUnified2` olan `true`.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="7ff1f-128">`pResult` Parametresi neden iki derleme eşdeğer veya eşdeğer değil olarak kabul edilir hakkında ayrıntılı bilgi içerir.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="7ff1f-129">Daha fazla bilgi için bkz: [AssemblyComparisonResult numaralandırması](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="7ff1f-129">For more information, see [AssemblyComparisonResult Enumeration](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ff1f-130">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="7ff1f-130">Requirements</span></span>  
 <span data-ttu-id="7ff1f-131">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ff1f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ff1f-132">**Başlık:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="7ff1f-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7ff1f-133">**Kitaplığı:** bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="7ff1f-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ff1f-134">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ff1f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff1f-135">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7ff1f-135">See Also</span></span>  
 [<span data-ttu-id="7ff1f-136">Fusion genel statik işlevleri</span><span class="sxs-lookup"><span data-stu-id="7ff1f-136">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="7ff1f-137">AssemblyComparisonResult numaralandırması</span><span class="sxs-lookup"><span data-stu-id="7ff1f-137">AssemblyComparisonResult Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)