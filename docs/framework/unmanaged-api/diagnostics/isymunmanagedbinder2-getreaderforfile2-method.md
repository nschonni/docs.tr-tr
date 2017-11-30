---
title: ISymUnmanagedBinder2::GetReaderForFile2 Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder2.GetReaderForFile2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d232bfed801a17e1ee47dee7643ae0bf21d338e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="64f88-102">ISymUnmanagedBinder2::GetReaderForFile2 Metodu</span><span class="sxs-lookup"><span data-stu-id="64f88-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="64f88-103">Bir meta veri arabirimi ve bir dosya adı doğru döndürür <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> modülü ile ilişkili hata ayıklama simgeleri okuma yapacak arabirimi.</span><span class="sxs-lookup"><span data-stu-id="64f88-103">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="64f88-104">Bu yöntem program veritabanı (PDB) dosyası için daha kapsamlı bir arama sağlar [Isymunmanagedbinder::getreaderforfile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="64f88-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64f88-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="64f88-105">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64f88-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="64f88-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="64f88-107">[in] Meta veri alma arayüzü için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="64f88-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="64f88-108">[in] Dosya adı için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="64f88-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="64f88-109">[in] Arama yolu için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="64f88-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="64f88-110">[in] Değerini [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) bir simge Okuyucu için arama yaparken kullanılacak ilkeyi belirtir numaralandırması.</span><span class="sxs-lookup"><span data-stu-id="64f88-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="64f88-111">[out] Ayarlanmış bir işaretçi döndürülen için <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="64f88-111">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64f88-112">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="64f88-112">Return Value</span></span>  
 <span data-ttu-id="64f88-113">Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="64f88-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64f88-114">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="64f88-114">Requirements</span></span>  
 <span data-ttu-id="64f88-115">**Başlık:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="64f88-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64f88-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="64f88-116">Remarks</span></span>  
 <span data-ttu-id="64f88-117">Bu yöntemin sürümü modülü yanındaki sağ dışındaki alanlarda PDB dosyası arayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="64f88-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="64f88-118">Arama İlkesi birleştirerek denetlenebilir [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="64f88-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="64f88-119">Örneğin, `AllowReferencePathAccess | AllowSymbolServerAccess` yürütülebilir dosyanın yanındaki ve bir simge sunucuda PDB arar ancak kayıt defterini sorgulayın veya yürütülebilir dosyanın yolunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="64f88-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="64f88-120">Varsa `searchPath` parametresi sağlanır, bu dizinlerin her zaman aranır.</span><span class="sxs-lookup"><span data-stu-id="64f88-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64f88-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="64f88-121">See Also</span></span>  
 [<span data-ttu-id="64f88-122">Isymunmanagedbinder2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="64f88-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="64f88-123">GetReaderForFile yöntemi</span><span class="sxs-lookup"><span data-stu-id="64f88-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)