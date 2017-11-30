---
title: "ICeeGen::AddSectionReloc Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.AddSectionReloc
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a74f01e3904c6f3f472110288abbec42fa892fdc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="512fd-102">ICeeGen::AddSectionReloc Yöntemi</span><span class="sxs-lookup"><span data-stu-id="512fd-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="512fd-103">.Reloc yönerge kodu Bankası'na ekler.</span><span class="sxs-lookup"><span data-stu-id="512fd-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="512fd-104">Bu yöntem artık kullanılmıyor ve kullanılmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="512fd-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="512fd-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="512fd-105">Syntax</span></span>  
  
```  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="512fd-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="512fd-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="512fd-107">[in] Bellek içi kodun bir .reloc yönergesi eklenecek bölümü.</span><span class="sxs-lookup"><span data-stu-id="512fd-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="512fd-108">[in] Bölüm uzaklığı.</span><span class="sxs-lookup"><span data-stu-id="512fd-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="512fd-109">[in] Bölümüne `offset` başvuruyor.</span><span class="sxs-lookup"><span data-stu-id="512fd-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="512fd-110">[in] Aşağıdakilerden birini [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) eklemek için .reloc yönerge türünü belirten değer.</span><span class="sxs-lookup"><span data-stu-id="512fd-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="512fd-111">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="512fd-111">Requirements</span></span>  
 <span data-ttu-id="512fd-112">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="512fd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="512fd-113">**Başlık:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="512fd-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="512fd-114">**Kitaplığı:** MsCorEE.dll kaynak olarak kullanılır</span><span class="sxs-lookup"><span data-stu-id="512fd-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="512fd-115">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="512fd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="512fd-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="512fd-116">See Also</span></span>  
 [<span data-ttu-id="512fd-117">Iceegen arabirimi</span><span class="sxs-lookup"><span data-stu-id="512fd-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)