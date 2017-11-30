---
title: "CeeSectionRelocType Numaralandırması"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CeeSectionRelocType
api_location: mscoree.dll
api_type: COM
f1_keywords: CeeSectionRelocType
helpviewer_keywords: CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d78b6b3867cb168e4ebf93c07f17a911e1955832
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="94a09-102">CeeSectionRelocType Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="94a09-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="94a09-103">Türü etkilemek için değerler sağlar `reloc` çağrıda yayılan yönerge [Iceegen::addsectionreloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span><span class="sxs-lookup"><span data-stu-id="94a09-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94a09-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="94a09-104">Syntax</span></span>  
  
```  
typedef enum  {  
    srRelocAbsolute,  
    srRelocHighLow          = 3,  
    srRelocHighAdj,       
    srRelocMapToken,  
    srRelocRelative,  
    srRelocFilePos,  
    srRelocCodeRelative,  
    srRelocIA64Imm64,  
    srRelocDir64,  
    srRelocIA64PcRel25,  
    srRelocIA64PcRel64,    srRelocAbsoluteTagged,    srRelocSentinel,    srNoBaseReloc       = 0x4000,  
    srRelocPtr          = 0x8000,  
    srRelocAbsolutePtr      = srRelocPtr + srRelocAbsolute,  
    srRelocHighLowPtr       = srRelocPtr + srRelocHighLow,  
    srRelocRelativePtr      = srRelocPtr + srRelocRelative,  
    srRelocIA64Imm64Ptr     = srRelocPtr + srRelocIA64Imm64,  
    srRelocDir64Ptr         = srRelocPtr + srRelocDir64  
    } CeeSectionRelocType;  
```  
  
## <a name="members"></a><span data-ttu-id="94a09-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="94a09-105">Members</span></span>  
  
|<span data-ttu-id="94a09-106">Üye</span><span class="sxs-lookup"><span data-stu-id="94a09-106">Member</span></span>|<span data-ttu-id="94a09-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="94a09-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="94a09-108">Yalnızca bir bölüm göreli oluşturur `reloc`, gönderen bir .reloc bölüme hiçbir şey yok.</span><span class="sxs-lookup"><span data-stu-id="94a09-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="94a09-109">Oluşturan bir `reloc` işaretçi ölçekli konumu.</span><span class="sxs-lookup"><span data-stu-id="94a09-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="94a09-110">Platforma bağlı olarak bu BASED_HIGHLOW veya BASED_DIR64 uygulamasına dönüştürülür.</span><span class="sxs-lookup"><span data-stu-id="94a09-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="94a09-111">Oluşturan bir `reloc` en üst burada 16 bit alt dahil edilmiştir .reloc tablosundaki Sonraki sözcüğü 32-bit sayının 16 bit.</span><span class="sxs-lookup"><span data-stu-id="94a09-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="94a09-112">Hiçbir şey .reloc bölüme gönderme bir belirteç harita yeniden konumlandırma oluşturur.</span><span class="sxs-lookup"><span data-stu-id="94a09-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="94a09-113">Değer göreli adresi düzeltmesi olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="94a09-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="94a09-114">Yalnızca bir bölüm göreli oluşturur `reloc`, gönderen bir .reloc bölüme hiçbir şey yok.</span><span class="sxs-lookup"><span data-stu-id="94a09-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="94a09-115">Bu `reloc` bölümünde, bölümün sanal adres dosya konumuna göre değil.</span><span class="sxs-lookup"><span data-stu-id="94a09-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="94a09-116">Kod göreli adresi düzeltmesi belirtir.</span><span class="sxs-lookup"><span data-stu-id="94a09-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="94a09-117">Oluşturan bir `reloc` bir IA64 bir 64 bit adresi için `movl` yönergesi.</span><span class="sxs-lookup"><span data-stu-id="94a09-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="94a09-118">Oluşturan bir `reloc` bir 64-bit adresi için.</span><span class="sxs-lookup"><span data-stu-id="94a09-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="94a09-119">Oluştur bir `reloc` bir IA64 bir 25 bit PC göreli adresi için `br.call` yönergesi.</span><span class="sxs-lookup"><span data-stu-id="94a09-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="94a09-120">Oluşturan bir `reloc` bir IA64 bir 64-bit PC göreli adresi için `brl.call` yönergesi.</span><span class="sxs-lookup"><span data-stu-id="94a09-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="94a09-121">30 bit'lik bir bölüm-göreli oluşturur `reloc`, etiketli işaretçi değerleri için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="94a09-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="94a09-122">Bu numaralandırma herhangi eklemeler sağlamaya yardımcı olmak için bir sentinel değer iç ağa yansıtılır `reloc` adı dizi.</span><span class="sxs-lookup"><span data-stu-id="94a09-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="94a09-123">Bir taban yayma değil belirtir `reloc`.</span><span class="sxs-lookup"><span data-stu-id="94a09-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="94a09-124">Bellek öncesi düzeltmesi içeriğinin bir bölümü yerine bir işaretçi olduğunu belirten bir değer uzaklığı.</span><span class="sxs-lookup"><span data-stu-id="94a09-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94a09-125">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="94a09-125">Requirements</span></span>  
 <span data-ttu-id="94a09-126">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94a09-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94a09-127">**Başlık:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="94a09-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94a09-128">**Kitaplığı:** bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="94a09-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94a09-129">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94a09-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a09-130">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="94a09-130">See Also</span></span>  
 [<span data-ttu-id="94a09-131">Meta veri numaralandırmalar</span><span class="sxs-lookup"><span data-stu-id="94a09-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="94a09-132">Iceegen arabirimi</span><span class="sxs-lookup"><span data-stu-id="94a09-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 [<span data-ttu-id="94a09-133">AddSectionReloc yöntemi</span><span class="sxs-lookup"><span data-stu-id="94a09-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)