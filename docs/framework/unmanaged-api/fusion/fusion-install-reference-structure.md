---
title: "FUSION_INSTALL_REFERENCE Yapısı"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FUSION_INSTALL_REFERENCE
api_location: fusion.dll
api_type: COM
f1_keywords: FUSION_INSTALL_REFERENCE
helpviewer_keywords: FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 244ea215b6668685920a454c1bd9da065076f38b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="fusioninstallreference-structure"></a><span data-ttu-id="49ec9-102">FUSION_INSTALL_REFERENCE Yapısı</span><span class="sxs-lookup"><span data-stu-id="49ec9-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="49ec9-103">Genel derleme önbelleğinde uygulamanın yüklü olduğu bir derleme bir uygulamanın yaptığı bir başvuru temsil eder.</span><span class="sxs-lookup"><span data-stu-id="49ec9-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49ec9-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="49ec9-104">Syntax</span></span>  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="49ec9-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="49ec9-105">Members</span></span>  
  
|<span data-ttu-id="49ec9-106">Üye</span><span class="sxs-lookup"><span data-stu-id="49ec9-106">Member</span></span>|<span data-ttu-id="49ec9-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="49ec9-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="49ec9-108">Yapı bayt cinsinden boyutu.</span><span class="sxs-lookup"><span data-stu-id="49ec9-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="49ec9-109">Gelecekteki genişletilebilirliği için ayrılmış.</span><span class="sxs-lookup"><span data-stu-id="49ec9-109">Reserved for future extensibility.</span></span> <span data-ttu-id="49ec9-110">Bu değer, 0 (sıfır) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="49ec9-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="49ec9-111">Başvuru ekler varlık.</span><span class="sxs-lookup"><span data-stu-id="49ec9-111">The entity that adds the reference.</span></span> <span data-ttu-id="49ec9-112">Bu alan şu değerlerden biri olabilir:</span><span class="sxs-lookup"><span data-stu-id="49ec9-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="49ec9-113">-FUSION_REFCOUNT_MSI_GUID: Derleme Microsoft Windows Installer kullanılarak yüklenmiş bir uygulama tarafından başvuruluyor.</span><span class="sxs-lookup"><span data-stu-id="49ec9-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="49ec9-114">`szIdentifier` Alan ayarlanmış `MSI`ve `szNonCanonicalData` alan ayarlanmış `Windows Installer`.</span><span class="sxs-lookup"><span data-stu-id="49ec9-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="49ec9-115">Bu düzen Windows yan yana derlemeler için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="49ec9-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="49ec9-116">-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: Derleme görünür bir uygulama tarafından başvurulan **Program Ekle/Kaldır** arabirimi.</span><span class="sxs-lookup"><span data-stu-id="49ec9-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="49ec9-117">`szIdentifier` Alanı sağlar uygulama ile kaydeder belirteci **Program Ekle/Kaldır** arabirimi.</span><span class="sxs-lookup"><span data-stu-id="49ec9-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="49ec9-118">-FUSION_REFCOUNT_FILEPATH_GUID: Derleme dosya sisteminde bir dosya tarafından temsil edilen bir uygulama tarafından başvuruluyor.</span><span class="sxs-lookup"><span data-stu-id="49ec9-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="49ec9-119">`szIdentifier` Alanı, bu dosyanın yolunu sağlar.</span><span class="sxs-lookup"><span data-stu-id="49ec9-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="49ec9-120">-FUSION_REFCOUNT_OPAQUE_STRING_GUID: Derleme yalnızca donuk bir dizeyle gösterilen bir uygulama tarafından başvuruluyor.</span><span class="sxs-lookup"><span data-stu-id="49ec9-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="49ec9-121">`szIdentifier` Alan bu donuk dize sağlar.</span><span class="sxs-lookup"><span data-stu-id="49ec9-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="49ec9-122">Bu değer kaldırdığınızda, Genel Derleme Önbelleği donuk başvuruları varlığını denetlemez.</span><span class="sxs-lookup"><span data-stu-id="49ec9-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="49ec9-123">-FUSION_REFCOUNT_OSINSTALL_GUID: Bu değer ayrılmıştır.</span><span class="sxs-lookup"><span data-stu-id="49ec9-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="49ec9-124">Genel derleme önbelleğinde derleme yüklü uygulamayı tanımlayan benzersiz bir dize.</span><span class="sxs-lookup"><span data-stu-id="49ec9-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="49ec9-125">Değerin değerini bağlıdır `guidScheme` alan.</span><span class="sxs-lookup"><span data-stu-id="49ec9-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="49ec9-126">Yalnızca başvuru ekler varlık tarafından anlaşılan bir dize.</span><span class="sxs-lookup"><span data-stu-id="49ec9-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="49ec9-127">Genel Derleme Önbelleği bu dizesi depolar, ancak bunu kullanmaz.</span><span class="sxs-lookup"><span data-stu-id="49ec9-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49ec9-128">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="49ec9-128">Requirements</span></span>  
 <span data-ttu-id="49ec9-129">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49ec9-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49ec9-130">**Başlık:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="49ec9-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="49ec9-131">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49ec9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49ec9-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="49ec9-132">See Also</span></span>  
 [<span data-ttu-id="49ec9-133">Fusion yapıları</span><span class="sxs-lookup"><span data-stu-id="49ec9-133">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="49ec9-134">Genel Derleme Önbelleği</span><span class="sxs-lookup"><span data-stu-id="49ec9-134">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)