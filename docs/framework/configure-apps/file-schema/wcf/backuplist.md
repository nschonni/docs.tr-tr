---
title: '&lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 6684dcc485ef1ee2c3e5501f2fbc43898e172958
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747300"
---
# <a name="ltbackuplistgt"></a>&lt;backupList&gt;
Birincil endpoint ulaşılamıyor durumunda kullanmak için yönlendirme hizmeti istediğiniz uç noktalar kümesi numaralandırır yedekleme listesini tanımlamak için yapılandırma bölümünü temsil eder. Listedeki ilk uç noktası kapalı ise, yönlendirme hizmeti otomatik olarak yük için listedeki bir sonraki devretme.  Bu karmaşık desenleri nasıl ele alınacağını veya hizmetlerinizin tümünün dağıtıldığı istemci uygulamanızı öğretmek gerekmeden güvenilirlik uygulamanıza eklemek için hızlı bir yol sağlar.  
  
 \<system.serviceModel>  
\<Yönlendirme >  
\<backupLists >  
\<backupList >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml 
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|name|Bu uç nokta listesi tanımlamak için kullanılan adını belirten dize.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<Filtre >](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<Yönlendirme >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Yedekleme uç noktaları listesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu bölüm bir ileti için bir iletişim özel durumunda birincil uç noktasına gönderirken aktarılmaz uç noktaları sıralı bir koleksiyonunu içerir.  
  
 Birincil uç gönderme listelenen `endpointName` özniteliği [ \<Ekle >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) iletişimleri özel durum ile başarısız oluyor, yönlendirme hizmeti ilk uç noktası bu iletiyi göndermeyi deneyecek yapılandırma bölümü. Bu da bir iletişim özel durumuyla başarısız olursa, yönlendirme hizmeti iletişim özel durumu veya tüm uç noktalar olarak başka bir hata döndürür gönderme girişimi başarılı olana kadar bu bölümde yer alan sonraki iletiye iletiyi göndermeyi deneyecek Koleksiyon bir hata döndürdü.  
  
 Bir iletişim özel Gönder "Hedef" adlı birincil uç döndürürse, aşağıdaki örnekte, "alternateServiceQueue" iletisi göndermek hizmeti çalışacak. Bu deneme ayrıca bir iletişim özel döndürürse, yönlendirme hizmeti koleksiyonda sonraki uç nokta ileti göndermeye çalışacak.  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
