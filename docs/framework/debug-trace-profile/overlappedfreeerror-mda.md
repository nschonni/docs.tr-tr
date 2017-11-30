---
title: overlappedFreeError MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- OverlappedFreeError MDA
- overlapped free method call error
- managed debugging assistants (MDAs), overlapped structures
- overlapped structures
- MDAs (managed debugging assistants), overlapped structures
- freeing overlapped structures
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 645c9f6c5a2a693fb2b88b2b2bc1c40501eecde8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="overlappedfreeerror-mda"></a><span data-ttu-id="0e40a-102">overlappedFreeError MDA</span><span class="sxs-lookup"><span data-stu-id="0e40a-102">overlappedFreeError MDA</span></span>
<span data-ttu-id="0e40a-103">`overlappedFreeError` Yönetilen hata ayıklama Yardımcısı (MDA) etkinleştirilmiş olduğunda <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> yöntemi çakışan işlem tamamlanmadan önce çağrılır.</span><span class="sxs-lookup"><span data-stu-id="0e40a-103">The `overlappedFreeError` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> method is called before the overlapped operation has completed.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="0e40a-104">Belirtiler</span><span class="sxs-lookup"><span data-stu-id="0e40a-104">Symptoms</span></span>  
 <span data-ttu-id="0e40a-105">Erişim ihlalleri veya çöpünün toplanma yığın bozulması.</span><span class="sxs-lookup"><span data-stu-id="0e40a-105">Access violations or corruption of the garbage-collected heap.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="0e40a-106">Sebep</span><span class="sxs-lookup"><span data-stu-id="0e40a-106">Cause</span></span>  
 <span data-ttu-id="0e40a-107">Çakışan bir yapı işlemi tamamlandı önce bırakılmış.</span><span class="sxs-lookup"><span data-stu-id="0e40a-107">An overlapped structure was freed before the operation completed.</span></span> <span data-ttu-id="0e40a-108">Serbest bırakılmış sonra Çakışan işaretçi kullanarak işlev yapısına daha sonra yazabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0e40a-108">The function that is using the overlapped pointer might write to the structure later, after it has been freed.</span></span> <span data-ttu-id="0e40a-109">Başka bir nesneye artık bu bölge belleğinde, yığın bozulması neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="0e40a-109">That can cause heap corruption because another object might now occupy that region.</span></span>  
  
 <span data-ttu-id="0e40a-110">Çakışan işlem başarıyla başlamadıysa bu MDA hata temsil edemeyebilir.</span><span class="sxs-lookup"><span data-stu-id="0e40a-110">This MDA might not represent an error if the overlapped operation did not start successfully.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="0e40a-111">Çözüm</span><span class="sxs-lookup"><span data-stu-id="0e40a-111">Resolution</span></span>  
 <span data-ttu-id="0e40a-112">Çakışan yapı kullanarak g/ç işlemi çağırmadan önce tamamlandığından emin olmak <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="0e40a-112">Ensure that the I/O operation using the overlapped structure has completed before calling the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29> method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="0e40a-113">Çalışma zamanı etkisi</span><span class="sxs-lookup"><span data-stu-id="0e40a-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="0e40a-114">Bu MDA CLR üzerinde etkisi yoktur.</span><span class="sxs-lookup"><span data-stu-id="0e40a-114">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="0e40a-115">Çıkış</span><span class="sxs-lookup"><span data-stu-id="0e40a-115">Output</span></span>  
 <span data-ttu-id="0e40a-116">Bu MDA için örnek çıktı verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="0e40a-116">The following is sample output for this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="0e40a-117">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="0e40a-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0e40a-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0e40a-118">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="0e40a-119">Yönetilen hata ayıklama Yardımcıları ile hataları tanılama</span><span class="sxs-lookup"><span data-stu-id="0e40a-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="0e40a-120">Birlikte çalışma hazırlama</span><span class="sxs-lookup"><span data-stu-id="0e40a-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)