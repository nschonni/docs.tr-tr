---
title: '&lt;defaultHttpCachePolicy&gt; öğesi (ağ ayarları)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 1e1b27cb8c0df4450c1a08151af19913b65fc2b3
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48782148"
---
# <a name="ltdefaulthttpcachepolicygt-element-network-settings"></a>&lt;defaultHttpCachePolicy&gt; öğesi (ağ ayarları)
HTTP önbelleğe alma etkindir ve önbelleğe alma ilkesi varsayılan tanımlar olup olmadığını açıklar.  
  
 \<Yapılandırma >  
\<system.net>  
\<requestCaching >  
\<defaultHttpCachePolicy >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`maximumAge`|Önbelleğe alınmış nesnenin süresi dolmuş olarak işaretlenmeden önce maksimum zaman aralığını belirtir.|  
|`maximumStale`|Önbelleğe alınmış nesnenin süresi dolmuş olarak işaretlenmeden önce hesaplanan güncellik süresini geçen en uzun süreyi belirtir.|  
|`minimumFresh`|Yeni olarak değerlendirilmesi önbelleğe alınmış bir nesne için minimum süre belirtir.|  
|`policyLevel`|Önbellek ilkesi otomatik olup veya önbellek olup atlanır belirtir. Varsayılan değer `BypassCache` şeklindedir.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Ağ istekleri için önbelleğe alma mekanizması denetler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Değeri `policyLevel` özniteliği, ya da `BypassCache` veya `Default`.  
  
 Değerleri `maximumAge`, `maximumStale`, ve `minimumFresh` öğeleri olan bir ya da açık bir zaman aralığı bir biçimi ile *d*. *hh*:*mm*:*ss* (gün, saat, dakika ve saniye) veya sabitler `minValue` veya `maxValue`uygun şekilde.  
  
## <a name="configuration-files"></a>Yapılandırma Dosyaları  
 Bu öğe, uygulama yapılandırma dosyası veya makine yapılandırma dosyası (Machine.config) kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, en düşük yeni birer birer en uzun geçerlilik süresi iki gün ve dört saatlik süre üst sınırını eski altı saat belirtin gösterilmektedir.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [Ağ Ayarları Şeması](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
