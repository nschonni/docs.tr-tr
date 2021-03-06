---
title: Değişken ve bağımsız değişken izleme
ms.date: 03/30/2017
ms.assetid: 8f3d9d30-d899-49aa-b7ce-a8d0d32c4ff0
ms.openlocfilehash: 45ed3761cd7ead82650023b93a2f32a43e847339
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47195881"
---
# <a name="variable-and-argument-tracking"></a>Değişken ve bağımsız değişken izleme
Bir iş akışı yürütülmesini izlerken, genellikle verileri ayıklamak kullanışlıdır. Bu izleme kayıt sonrası yürütme erişirken ek bağlam sağlar. İçinde [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], herhangi bir görünür bir değişken veya bağımsız değişken izleme kullanarak iş akışı herhangi bir etkinliği kapsamında ayıklayabilirsiniz. İzleme profilleri verileri ayıklamak kolaylaştırır.  
  
## <a name="variables-and-arguments"></a>Değişkenler ve bağımsız değişkenler  
 Bir etkinlik bir ActivityStateRecord içerilip değişkenleri ve bağımsız değişkenler ayıklanır.  Yalnızca etkinlik kapsamında olduğunda, bir değişken için ayıklama kullanılabilir. Bir etkinlik içinde ayıklanacak bir değişken, aşağıdaki şekilde belirlenir:  
  
-   Bir değişken değişken adıyla belirtilirse, izlenmekte olan geçerli etkinliği içinde ve üst etkinliklerde değişkeni İzleme arar. Değişken, geçerli etkinlik kapsamda ve üst kapsam aranır.  
  
-   Ayıklanacak değişkenleri adıyla belirtilmişse = "*", geçerli etkinliği izlenmekte olan tüm değişkenler ayıklandıktan sonra. Bu durumda değişkenleri, kapsamındaki ancak etkinlikleri ayıklanmadı üst öğede tanımlı.  
  
 Bağımsız değişkenler ayıklanırken, ayıklanan bağımsız değişkenleri etkinliğin durumuna bağlıdır. Bir etkinlik durumunu olduğunda Executing, ardından yalnızca `InArguments` ayıklama için kullanılabilir. Herhangi diğer etkinlik için durumu (kapalı, hatalı, iptal edildi), tüm bağımsız değişkenler, InArguments hem OutArguments, ayıklama için kullanılabilir.  
  
 Aşağıdaki örnek, değişkenler ve bağımsız değişkenler ayıklar bir etkinlik durumu sorgusu gösterir, etkinliğin `Closed` izleme kaydını yayılan. Değişkenler ve bağımsız değişkenler ayıklanan yalnızca bir <xref:System.Activities.Tracking.ActivityStateRecord> ve bu nedenle içinde bir izleme abone olduğunuz kullanarak profil <xref:System.Activities.Tracking.ActivityStateQuery>.  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="protecting-information-stored-within-variables-and-arguments"></a>Değişkenler ve bağımsız değişkenler içinde depolanan bilgi koruma  
 Varsayılan WF çalışma zamanı tarafından görünür hale izlenen bir değişken veya bağımsız değişken olarak. Bir iş akışı Geliştirici aşağıdaki adımları izleyerek erişmesini koruyabilir:  
  
1.  Bir değişkenin değeri olarak şifreleyin.  
  
2.  Bir değişkenin veya bağımsız değişken ayıklama önlemek için bir izleme profili yazma denetimi.  
  
3.  Özel İzleme katılımcıları WF kod emin olmak için değişken veya bağımsız değişkenleri depolanan hassas bilgileri açıklamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Server App Fabric izleme](https://go.microsoft.com/fwlink/?LinkId=201273)  
 [App Fabric ile uygulamaları izleme](https://go.microsoft.com/fwlink/?LinkId=201275)
