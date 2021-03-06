---
title: Eş adları ve PNRP kimlikleri
ms.date: 03/30/2017
ms.assetid: afa538e8-948f-4a98-aa9f-305134004115
author: mcleblanc
ms.author: markl
ms.openlocfilehash: cab8bb848596d4d6dc7f810d454b875f4fd58e47
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216508"
---
# <a name="peer-names-and-pnrp-ids"></a>Eş adları ve PNRP kimlikleri
Bir eş ad, bir bilgisayar, bir kullanıcı, Grup, bir hizmet veya bir IPv6 adresine çözülebilir bir eş ile ilişkili herhangi bir şey olabilir, iletişim için bir uç nokta temsil eder. Eş Adı Çözümleme Protokolü (PNRP), bulut üyelerini tanımlamak için kullanılan bir PNRP kimliği, oluşturulması için istatistiksel olarak benzersiz eş adını alır.  
  
## <a name="peer-names"></a>Eş adları  
 Eş adları olarak kaydedilebilir güvenli veya güvenli. Herhangi bir yinelenen güvenli olmayan ad kaydedebilecekleri güvenli olmayan yanıltma tabidir, yalnızca metin dizelerini adlarıdır. Güvenli olmayan adlar, özel veya başka korumalı ağlarda en iyi şekilde kullanılır. Güvenli adları, sertifika ve dijital imza ile korunur. Yalnızca özgün yayımcısı, güvenli bir ad sahipliğini kanıtlamak mümkün olacaktır.  
  
 Bulut ve kapsamın birleşimi, PNRP etkinliğinde katılan eşleri için makul güvenli bir ortam sağlar. Ancak, güvenli eş adını kullanarak Ağ uygulamasının genel güvenlik emin olunmasını sağlamamasıdır. Uygulama güvenlik uygulamaya bağlıdır.  
  
 Güvenli eş adları, yalnızca bunların sahibi tarafından kaydedilir ve ortak anahtar şifrelemesi ile korunur. Güvenli eş adları karşılık gelen özel anahtarın eş varlığa ait olarak kabul edilir. Sahiplik özel anahtarla imzalanır sertifikalı eş adresi (CPA) kanıtladılar. Kötü niyetli bir kullanıcı bir eş ad karşılık gelen özel anahtar olmadan sahipliğini taklit edilemez.  
  
## <a name="pnrp-ids"></a>PNRP kimlikleri  
 ![PNRP kimliği](../../../docs/framework/network-programming/media/fdc9e8a0-4a1c-488d-a019-bc3a1973220c.gif "fdc9e8a0-4a1c-488d-a019-bc3a1973220c")  
  
 PNRP kimlikleri aşağıdakilerden oluşur:  
  
-   Yüksek düzeyli 128 bit eşler arası (P2P) kimliği olarak da bilinen bir karmasını uç noktasına atanan bir eş adı var. Eş adı şu biçimdedir: *Authority.Classifier*. Güvenli adları için *yetkilisi* on altılık karakterler eş ad ortak anahtarı Güvenli Karma Algoritması 1 (SHA1) karmasıdır. Güvenli olmayan adları için *yetkilisi* tek karakteri "0". *Sınıflandırıcı* uygulamayı tanımlayan bir dizedir. Hiçbir eş adı sınıflandırıcı 149 karakterden uzun dahil olmak üzere `null` Sonlandırıcı.  
  
-   Düşük düzey 128 bit tanımlayan farklı örnekleri aynı P2P kimliğinin aynı bulutta oluşturulan bir sayıdır hizmet konumu için kullanılır.  
  
 Tek bir bilgisayardan kaydedilmesi birden çok PNRP kimlikleri bu P2P kimliği ve hizmet konumu birleşimini sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Net.PeerToPeer.PeerName>  
 <xref:System.Net.PeerToPeer>
