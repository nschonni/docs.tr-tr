---
title: ICorDebugRegisterSet::GetRegisters Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.GetRegisters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7edae3d3be1bcfb80b7a1e432fd5f25e119f078f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="02b85-102">ICorDebugRegisterSet::GetRegisters Metodu</span><span class="sxs-lookup"><span data-stu-id="02b85-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="02b85-103">Her kayıt değerini (kod şu anda yürütülmekte bilgisayarda) alır bit maskesi kullanılarak belirtilir.</span><span class="sxs-lookup"><span data-stu-id="02b85-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02b85-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="02b85-104">Syntax</span></span>  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02b85-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="02b85-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="02b85-106">[in] Bir bit maskesi alınacak değerler hangi kaydı belirtir.</span><span class="sxs-lookup"><span data-stu-id="02b85-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="02b85-107">Her bitin bir kasaya karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="02b85-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="02b85-108">Bir bit birine ayarlanırsa, kasanın değer alınır; Aksi takdirde kasanın değeri alınamadı.</span><span class="sxs-lookup"><span data-stu-id="02b85-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="02b85-109">[in] Alınacak kayıt değerlerinin sayısı.</span><span class="sxs-lookup"><span data-stu-id="02b85-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="02b85-110">[out] Bir dizi `CORDB_REGISTER` nesneleri, her biri bir kayıt değeri alır.</span><span class="sxs-lookup"><span data-stu-id="02b85-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02b85-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="02b85-111">Remarks</span></span>  
 <span data-ttu-id="02b85-112">Dizinin boyutu bir bit maskesi için bitler sayısına eşit olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="02b85-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="02b85-113">`regCount` Parametresi kayıt değerlerini alacak arabellek öğe sayısını belirtir.</span><span class="sxs-lookup"><span data-stu-id="02b85-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="02b85-114">Varsa `regCount` değeri maskesiyle belirtilen yazmaçlar sayısı için çok küçük, daha yüksek numaralı yazmaçlar kümesinden kesilir.</span><span class="sxs-lookup"><span data-stu-id="02b85-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="02b85-115">Varsa `regCount` değer çok büyük, kullanılmayan `regBuffer` öğeleri değiştirilmemiş olacaktır.</span><span class="sxs-lookup"><span data-stu-id="02b85-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="02b85-116">Bit maskesi kullanılamıyor, bir kayıt belirtiyorsa `GetRegisters` konusu kasaya belirsiz bir değer döndürür.</span><span class="sxs-lookup"><span data-stu-id="02b85-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02b85-117">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="02b85-117">Requirements</span></span>  
 <span data-ttu-id="02b85-118">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02b85-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02b85-119">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02b85-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02b85-120">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02b85-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02b85-121">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02b85-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02b85-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="02b85-122">See Also</span></span>  
 [<span data-ttu-id="02b85-123">Icordebugregisterset arabirimi</span><span class="sxs-lookup"><span data-stu-id="02b85-123">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="02b85-124">Icordebugregisterset2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="02b85-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)