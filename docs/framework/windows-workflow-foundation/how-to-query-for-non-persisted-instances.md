---
title: 'Nasıl yapılır: Sorgu kalıcı olmayan örnekleri için'
ms.date: 03/30/2017
ms.assetid: 294019b1-c1a7-4b81-a14f-b47c106cd723
ms.openlocfilehash: 000342013be4380e1a038fb8233050523f6bc758
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516168"
---
# <a name="how-to-query-for-non-persisted-instances"></a>Nasıl yapılır: Sorgu kalıcı olmayan örnekleri için
Bir hizmetin yeni bir örneğini oluşturulur ve hizmet tanımlı SQL iş akışı örneği deposuna davranışı vardır, hizmet ana bilgisayarı ilk giriş o hizmet örneği için örnek deposunda oluşturur. Hizmet örneği ilk kez ediyorsa, daha sonra etkinleştirme, kurtarma ve denetim için gerekli olan ek veri birlikte geçerli örneğin durumu SQL iş akışı örneği deposuna davranışı depolar.  
  
 İlk giriş örneği oluşturulduktan sonra bir örneği kalıcı yapılmaz, hizmet örneği kalıcı olmayan durumda olarak kabul edilir. Tüm kalıcı hizmet örnekleri sorgulanan ve denetlenir. Kalıcı olmayan hizmet örnekleri sorgulanan denetlenen ne. Kalıcı olmayan bir örnek işlenmeyen bir özel durum nedeniyle askıya alınırsa sorgulanabilir ancak değil denetlenir.  
  
 Kalıcı olmayan bir durumda aşağıdaki senaryolarda henüz kalıcı dayanıklı hizmet örnekleri kalır:  
  
-   Örneği ilk kez kalıcı önce Hizmet Konağı çöküyor. İlk giriş örneği için örnek deposunda kalır. Örnek, kurtarılabilir değil. Bağlantılı bir ileti alınırsa örneği yeniden etkin hale gelir.  
  
-   İlk kez kalıcı önce örneği işlenmeyen bir özel durum karşılaşır. Aşağıdaki senaryolar ortaya  
  
    -   Varsa değerini **UnhandledExceptionAction** özelliği ayarlanmış **Abandon**, hizmet dağıtım bilgileri için örnek deposuna yazılır ve bellekten bir örneğidir. Örnek Kalıcılık veritabanında kalıcı olmayan durumda kalır.  
  
    -   Varsa değerini **UnhandledExceptionAction** özelliği ayarlanmış **AbandonAndSuspsend**, hizmet dağıtım bilgileri Kalıcılık veritabanına yazılır ve örnek durumu içinayarlandı **Askıya**. Örnek, iptal, sona erdi veya sürdürülemez. Hizmet ana bilgisayarı örneği henüz kalıcı kurmadı ve bu nedenle veritabanı girişi örneği için tam değil çünkü yüklenemez.  
  
    -   Varsa değerini **UnhandledExceptionAction** özelliği ayarlanmış **iptal** veya **Sonlandır**, hizmet dağıtım bilgileri için örnek deposuna yazılır ve Örnek durumu ayarlanmış **tamamlandı**.  
  
 Aşağıdaki bölümler SQL Kalıcılık veritabanında kalıcı olmayan örneklerini bulmak ve bu örnekler veritabanından silmek için örnek sorgular sağlar.  
  
## <a name="to-find-all-instances-not-persisted-yet"></a>Değil tüm örneklerini bulmak için henüz kalıcı  
 Aşağıdaki SQL sorgusunu kimliği ve oluşturulması zaman içinde kalıcı olmayan tüm örnekleri için henüz Kalıcılık veritabanına döndürür.  
  
```  
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0;  
```  
  
## <a name="to-find-all-instances-not-persisted-yet-and-also-not-loaded"></a>Tüm örneklerini henüz kalıcı değildir ve ayrıca yüklenmedi bulmak için  
 Aşağıdaki SQL sorgusunu kalıcı değildir ve ayrıca yüklü olmayan tüm örnekleri için kimliği ve oluşturma saati döndürür.  
  
```  
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and CurrentMachine is NULL;  
```  
  
## <a name="to-find-all-suspended-instances-not-persisted-yet"></a>Askıya alınmış tüm örneklerini bulamaz için henüz kalıcı  
 Aşağıdaki SQL sorgusunu kimliği, oluşturulma zamanı, askıya neden ve askıya özel durum adı kalıcı değildir tüm örnekleri için ve ayrıca askıya alınmış durumda döndürür.  
  
```  
select InstanceId, CreationTime, SuspensionReason, SuspensionExceptionName from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and IsSuspended = 1;  
```  
  
## <a name="to-delete-non-persisted-instances-from-the-persistence-database"></a>Kalıcı olmayan örnekleri Kalıcılık veritabanından silmek için  
 Düzenli aralıklarla kalıcı olmayan örnekleri için örnek deposuna denetleyin ve örnek bir bağıntılı iletisi almaz eminseniz örnekleri örneği Mağazası'ndan kaldırın gerekir. Örneğin, örnek veritabanında birkaç ay olmuştur ve iş akışı genellikle birkaç gün ömrü olduğunu biliyorsanız, bunun çöken başlatılmamış bir örneği olduğunu varsaymak güvenli olacaktır.  
  
 Genel olarak, askıya değil ya da yüklenemeyen kalıcı olmayan örneklerini silmek güvenlidir. Değil silmelisiniz **tüm** Bu örnek kümesi yalnızca oluşturulur ancak olmayan örnekleri içerdiğinden kalıcı olmayan örnekleri henüz kalıcı. Yalnızca bir özel durum örneği yüklenmiş olan iş akışı hizmeti ana bilgisayarı neden olduğundan kalmış kalıcı olmayan örnekleri veya örneğin kendisini bir özel duruma neden silmeniz gerekir.  
  
> [!WARNING]
>  Kalıcı olmayan örneklerini örneği Mağazası'ndan silme deposunun boyutunu azaltır ve depolama işlemlerinin performansını artırabilir.
