---
title: "ForwardTranslateAccelerator işlevi (WPF yönetilmeyen API Başvurusu)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ForwardTranslateAccelerator
api_location: PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 663b28ed1a9430a6280ccd0ee9a44da2dea0c3cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="1c333-102">ForwardTranslateAccelerator işlevi (WPF yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="1c333-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="1c333-103">Bu API Windows Presentation Foundation (WPF) altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.</span><span class="sxs-lookup"><span data-stu-id="1c333-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="1c333-104">Windows Presentation Foundation (WPF) altyapısı tarafından windows yönetimi için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="1c333-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c333-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="1c333-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c333-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="1c333-106">Parameters</span></span>  
 <span data-ttu-id="1c333-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="1c333-107">pMsg</span></span>  
 <span data-ttu-id="1c333-108">Bir ileti için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="1c333-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="1c333-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="1c333-109">appUnhandled</span></span>  
 <span data-ttu-id="1c333-110">`true`ne zaman uygulama zaten giriş iletiyi işlemek için bir fırsat verildi, ancak bunu işlediği değil; Aksi takdirde `false`.</span><span class="sxs-lookup"><span data-stu-id="1c333-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c333-111">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="1c333-111">Requirements</span></span>  
 <span data-ttu-id="1c333-112">**Platformlar:** bkz [.NET Framework sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c333-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c333-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="1c333-113">**DLL:**</span></span>  
  
 <span data-ttu-id="1c333-114">.NET Framework 3.0 ve 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="1c333-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="1c333-115">.NET Framework 4 ve üzeri: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="1c333-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="1c333-116">**.NET framework sürümü:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c333-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c333-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1c333-117">See Also</span></span>  
 [<span data-ttu-id="1c333-118">WPF yönetilmeyen API Başvurusu</span><span class="sxs-lookup"><span data-stu-id="1c333-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)