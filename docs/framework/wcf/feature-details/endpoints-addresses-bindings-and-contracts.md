---
title: 'Uç Noktalar: Adresler, Bağlamalar ve Sözleşmeler'
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: 0909d1d10ab8932f27f7ca6cba6207d57fa4f4cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493754"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a>Uç Noktalar: Adresler, Bağlamalar ve Sözleşmeler
Tüm Windows Communication Foundation (WCF) hizmetiyle aracılığıyla iletişimin *uç noktaları* hizmetinin. Uç noktaları, istemcilerin bir WCF hizmeti tarafından sunulan işlevselliği erişim sağlar.  
  
 Her uç nokta dört özelliklerini oluşur:  
  
-   Uç nokta bulunabileceği gösteren bir adres.  
  
-   Bir bağlama istemci uç noktasıyla nasıl iletişim kurabilir belirtir.  
  
-   Kullanılabilir işlemleri tanımlayan bir sözleşme.  
  
-   Yerel uygulama uç nokta ayrıntılarını belirtin davranışları kümesi.  
  
 Bu konu, bu uç nokta yapı açıklar ve nasıl WCF nesne modelinde temsil açıklar.  
  
## <a name="the-structure-of-an-endpoint"></a>Bir uç nokta yapısı  
 Her uç nokta aşağıdakilerden oluşur:  
  
-   Adresi: Adresi benzersiz olarak uç noktayı tanımlar ve olası söyler bulunduğu olduğu hizmet tüketicileri. WCF nesne modeli tarafından temsil edilen <xref:System.ServiceModel.EndpointAddress> sınıfı. Bir <xref:System.ServiceModel.EndpointAddress> sınıfı içerir:  
  
    -   A <xref:System.ServiceModel.EndpointAddress.Uri%2A> hizmetinin adresini gösteren özelliği.  
  
    -   Bir <xref:System.ServiceModel.EndpointAddress.Identity%2A> özelliği hizmet güvenlik kimliğini ve isteğe bağlı bir ileti üstbilgileri koleksiyonunu temsil eder. Daha ayrıntılı tanımlamak veya uç noktasıyla etkileşim için adresleme bilgi ve isteğe bağlı ileti üstbilgilerini ek sağlamak için kullanılır.  
  
     Daha fazla bilgi için bkz: [bir uç noktası adresi belirtme](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
-   Bağlama: Bağlama bitiş noktası ile iletişim kurmak nasıl belirtir. Şunları içerir:  
  
    -   (Örneğin, TCP veya HTTP) kullanmak için Aktarım Protokolü.  
  
    -   (Örneğin, metin veya ikili) iletileri için kullanılacak kodlama.  
  
    -   Gerekli güvenlik gereksinimleri (örneğin, SSL veya SOAP iletisi güvenlik).  
  
     Daha fazla bilgi için bkz: [WCF bağlamaları genel bakış](../../../../docs/framework/wcf/bindings-overview.md). Bir bağlama WCF nesne modelinde Özet temel sınıf tarafından temsil edilen <xref:System.ServiceModel.Channels.Binding>. Çoğu senaryoda, kullanıcılar sistem tarafından sağlanan bağlamalar birini kullanabilirsiniz. Daha fazla bilgi için bkz: [System-Provided bağlamaları](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
-   Sözleşmeleri: Sözleşme istemciye uç noktasını kullanıma sunar hangi işlevsellikler özetlenmektedir. Bir sözleşme belirtir:  
  
    -   Hangi işlemlerin bir istemci tarafından çağrılabilir.  
  
    -   İleti biçimi.  
  
    -   Giriş parametreleri veya çağrı işlemi için gereken veri türü.  
  
    -   Ne tür bir işlem veya yanıt iletisi istemci bekleyebilirsiniz.  
  
     Bir sözleşme tanımlama hakkında daha fazla bilgi için bkz: [Hizmet sözleşmeleri tasarlama](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
-   Davranışları: Hizmet uç noktası yerel davranışını özelleştirmek için uç nokta davranışları kullanabilirsiniz. Uç nokta davranışları bir WCFruntime oluşturma sürecinde katılarak elde edin. Bir uç noktası davranışı örneği <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> SOAP ve Web Hizmetleri Açıklama Dili (WSDL) adresinden farklı bir dinleme adresi belirtmenize olanak tanır özelliği. Daha fazla bilgi için bkz: [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).  
  
## <a name="defining-endpoints"></a>Uç noktaları tanımlama  
 Uç nokta ya da imperatively kod kullanarak bir hizmet için veya yapılandırma yoluyla bildirimli olarak belirtebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: yapılandırmada hizmet uç noktası oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) ve [nasıl yapılır: kod içinde hizmet uç noktası oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 Bu bölümde bağlamaları, uç noktaları ve adresleri amacını açıklayan; bağlama ve bir uç nokta nasıl yapılandırılacağını gösterir; ve nasıl kullanılacağını göstermektedir `ClientVia` davranışı ve `ListenUri` özelliği.  
  
 [Adresler](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 Uç noktaları WCF'de nasıl ele alınan açıklar.  
  
 [Bağlamalar](../../../../docs/framework/wcf/feature-details/bindings.md)  
 Taşıma, kodlama ve istemcileri ve Hizmetleri birbirleri ile iletişim kurması gereken protokol ayrıntılarını belirtmek için bağlamaları nasıl kullanıldığını açıklar.  
  
 [Anlaşmalar](../../../../docs/framework/wcf/feature-details/contracts.md)  
 Sözleşmeler yöntemleri bir hizmetin nasıl tanımlar açıklar.  
  
 [Nasıl yapılır: Yapılandırma İçinde Hizmet Uç Noktası Oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 Hizmet uç noktası yapılandırmasında oluşturmayı açıklar.  
  
 [Nasıl yapılır: Kod İçinde Hizmet Uç Noktası Oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 Kod içinde hizmet uç noktası oluşturmayı açıklar.  
  
 [Nasıl yapılır: Derlenmiş Hizmet Kodunu Doğrulamak için Svcutil.exe Kullanma](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 Hata hizmet uygulamaları ve yapılandırmaları kullanarak hizmet barındırma olmadan algılamaya açıklar [ServiceModel meta veri yardımcı Programracı (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmetleri Yapılandırma](../../../../docs/framework/wcf/configuring-services.md)  
 [Bağlamaları Genişletme](../../../../docs/framework/wcf/extending/extending-bindings.md)
