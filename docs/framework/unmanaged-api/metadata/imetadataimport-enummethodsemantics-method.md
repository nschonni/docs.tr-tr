---
title: "IMetaDataImport::EnumMethodSemantics Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMethodSemantics
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0d5ec79701f73b8beb7759d72b972fc347a339c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="85796-102">IMetaDataImport::EnumMethodSemantics Yöntemi</span><span class="sxs-lookup"><span data-stu-id="85796-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="85796-103">Özellikleri ve belirtilen yöntem ilgili özellik değişikliği olayları numaralandırır.</span><span class="sxs-lookup"><span data-stu-id="85796-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85796-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="85796-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85796-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="85796-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="85796-106">[içinde out] Numaralayıcı gösteren bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="85796-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="85796-107">Bu, bu yöntem ilk çağrısı için NULL olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="85796-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="85796-108">[in] Numaralandırma kapsamını sınırlar MethodDef belirteci.</span><span class="sxs-lookup"><span data-stu-id="85796-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="85796-109">[out] Özellikleri ve olayları depolamak için kullanılan dizisi.</span><span class="sxs-lookup"><span data-stu-id="85796-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="85796-110">[in] En büyük boyutunu `rEventProp` dizi.</span><span class="sxs-lookup"><span data-stu-id="85796-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="85796-111">[out] Olay veya döndürülen özellikleri sayısı `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="85796-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85796-112">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="85796-112">Return Value</span></span>  
  
|<span data-ttu-id="85796-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85796-113">HRESULT</span></span>|<span data-ttu-id="85796-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="85796-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="85796-115">`EnumMethodSemantics`başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="85796-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="85796-116">Olayları veya Numaralandırılacak özellikleri yok.</span><span class="sxs-lookup"><span data-stu-id="85796-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="85796-117">Bu durumda, `pcEventProp` sıfırdır.</span><span class="sxs-lookup"><span data-stu-id="85796-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85796-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="85796-118">Remarks</span></span>  
 <span data-ttu-id="85796-119">Birçok ortak dil çalışma zamanı türleri tanımlama *özelliği* `Changed` olayları ve `On` *özelliği* `Changed` ilgili özellikleri için yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="85796-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="85796-120">Örneğin, <xref:System.Windows.Forms.Control?displayProperty=nameWithType> türünü tanımlayan bir <xref:System.Windows.Forms.Control.Font%2A> özelliği, bir <xref:System.Windows.Forms.Control.FontChanged> olayı ve bir <xref:System.Windows.Forms.Control.OnFontChanged%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="85796-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="85796-121">Ayarlama erişimcisi yöntemi <xref:System.Windows.Forms.Control.Font%2A> özelliği çağrıları <xref:System.Windows.Forms.Control.OnFontChanged%2A> sırayla başlatır yöntemi <xref:System.Windows.Forms.Control.FontChanged> olay.</span><span class="sxs-lookup"><span data-stu-id="85796-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="85796-122">Çağrısıyla sonlandırmalısınız `EnumMethodSemantics` için MethodDef kullanarak <xref:System.Windows.Forms.Control.OnFontChanged%2A> başvurularını almak için <xref:System.Windows.Forms.Control.Font%2A> özelliği ve <xref:System.Windows.Forms.Control.FontChanged> olay.</span><span class="sxs-lookup"><span data-stu-id="85796-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85796-123">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="85796-123">Requirements</span></span>  
 <span data-ttu-id="85796-124">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85796-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85796-125">**Başlık:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="85796-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85796-126">**Kitaplığı:** bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="85796-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="85796-127">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85796-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85796-128">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="85796-128">See Also</span></span>  
 [<span data-ttu-id="85796-129">Imetadataımport arabirimi</span><span class="sxs-lookup"><span data-stu-id="85796-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="85796-130">Imetadataımport2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="85796-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)