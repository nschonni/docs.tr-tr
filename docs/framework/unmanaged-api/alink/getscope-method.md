---
title: GetScope Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetScope
api_location: alink.dll
api_type: COM
f1_keywords: GetScope
helpviewer_keywords: GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b3ebcb90142cc70a2d246d2e9ea6c42babe83b18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="getscope-method1"></a><span data-ttu-id="59797-102">GetScope Method1</span><span class="sxs-lookup"><span data-stu-id="59797-102">GetScope Method1</span></span>
<span data-ttu-id="59797-103">Bir alma kapsamı alır.</span><span class="sxs-lookup"><span data-stu-id="59797-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59797-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="59797-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59797-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="59797-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="59797-106">Derleme almak için benzersiz kimliği.</span><span class="sxs-lookup"><span data-stu-id="59797-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="59797-107">Alınacak benzersiz kimliği dosyasının.</span><span class="sxs-lookup"><span data-stu-id="59797-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="59797-108">İçeri aktarmak için sıfır tabanlı kapsamı.</span><span class="sxs-lookup"><span data-stu-id="59797-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="59797-109">Alan [Imetadataımport arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) kapsam için arabirim.</span><span class="sxs-lookup"><span data-stu-id="59797-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59797-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="59797-110">Return Value</span></span>  
 <span data-ttu-id="59797-111">Yöntem başarılı olursa S_OK döndürür.</span><span class="sxs-lookup"><span data-stu-id="59797-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59797-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="59797-112">Requirements</span></span>  
 <span data-ttu-id="59797-113">ALink.h gerektirir</span><span class="sxs-lookup"><span data-stu-id="59797-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59797-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="59797-114">See Also</span></span>  
 [<span data-ttu-id="59797-115">Ialink arabirimi</span><span class="sxs-lookup"><span data-stu-id="59797-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="59797-116">Ialink2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="59797-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="59797-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="59797-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)