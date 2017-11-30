---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4bce99f11ba5a18e80c24fc51e65b66de97f9e7d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="a0a1f-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="a0a1f-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="a0a1f-103">Belirtilen işlem için belirtilen işlem, bir işlenmemiş yürütme özel durum nedeniyle tamamlandı.</span><span class="sxs-lookup"><span data-stu-id="a0a1f-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a0a1f-104">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a0a1f-104">Description</span></span>  
 <span data-ttu-id="a0a1f-105">Geçerli işlemi tamamlamak için girişimi sırasında bir hata oluştuğunda izlenen.</span><span class="sxs-lookup"><span data-stu-id="a0a1f-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="a0a1f-106">Bir yanıt önce aşması veya hataya çağırana gönderilir.</span><span class="sxs-lookup"><span data-stu-id="a0a1f-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="a0a1f-107">Sorun giderme</span><span class="sxs-lookup"><span data-stu-id="a0a1f-107">Troubleshooting</span></span>  
 <span data-ttu-id="a0a1f-108">Özel durum iletisi ve tıklatılabilir tüm öğeler için izlenen iletisini inceleyin.</span><span class="sxs-lookup"><span data-stu-id="a0a1f-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a1f-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a0a1f-109">See Also</span></span>  
 [<span data-ttu-id="a0a1f-110">İzleme</span><span class="sxs-lookup"><span data-stu-id="a0a1f-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="a0a1f-111">Uygulamanızda sorun giderme için izlemeyi kullanma</span><span class="sxs-lookup"><span data-stu-id="a0a1f-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="a0a1f-112">Yönetim ve tanılama</span><span class="sxs-lookup"><span data-stu-id="a0a1f-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)